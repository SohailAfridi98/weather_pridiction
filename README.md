Project Summary: Weather Prediction and Conversational Chatbot using DialoGPT and RandomForestRegressor
Objective:
The goal of this project is to create a conversational chatbot that can answer general user queries and provide weather predictions. The chatbot combines generative conversational responses (using DialoGPT) and weather-related predictions (using RandomForestRegressor). 
The system is designed to:

1. Answer conversational questions using a pre-trained DialoGPT model.
2. Provide weather data based on a dataset of historical weather information.
3. Predict future weather (next-day average temperature) using a trained RandomForestRegressor model based on the historical data.
Implementation Overview:
1. Conversational Chatbot using DialoGPT:
Model: The chatbot uses DialoGPT (medium), a pre-trained language model fine-tuned for conversational purposes.
Functionality: It can handle general conversations with users (e.g., "How are you?" or "Tell me a joke") and provides coherent responses.
Improvements: We configured nucleus sampling (top_p) and temperature to make the responses more varied and natural.
2. Weather Data Querying:
Dataset: A historical weather dataset (stored in CSV format) with features such as temperature, humidity, wind speed, and precipitation for multiple cities over different dates.
Functionality: The chatbot allows users to query historical weather data for a specific city on a particular date or for a range of dates. Example queries include:
"What is the weather in Islamabad on 2023-09-29?"
"Show me the weather in Lahore from 2023-09-28 to 2023-10-02."
3. Weather Prediction using RandomForestRegressor:
Model: A RandomForestRegressor model is trained to predict the next day's average temperature (avgtemp_c) based on features like max temperature, min temperature, wind speed, and humidity.
Features Used for Prediction:
'maxtemp_c', 'mintemp_c', 'maxwind_kph', 'totalprecip_mm', and 'avghumidity'
Prediction Functionality: The chatbot predicts the average temperature for the next day based on historical trends. This feature is triggered when the user requests a date range with a prediction, such as:
"Show me the weather in Islamabad from 2023-09-28 to 2023-10-02 and predict."
