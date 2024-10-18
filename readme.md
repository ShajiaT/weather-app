# Weather Dashboard and Chatbot

This project integrates weather forecast data and chatbot capabilities to help users get real-time weather information and chat responses using OpenWeather API and Google Gemini AI API.

## Features
- **Weather Dashboard**: Provides weather forecasts for a selected city. You can view temperatures, wind speed, humidity, and weather conditions with sorting and filtering options.
- **Weather Chatbot**: Responds to natural language queries about the weather using the Google Gemini API for general responses and OpenWeather API for weather-related queries.

## Project Structure

### Files
1. **index.html**
    - This file contains the HTML structure for the Weather Dashboard and the chatbot.
    - It includes input fields to enter a city name and buttons for sorting, filtering, and converting units between metric and imperial.

2. **styles.css**
    - Contains the styles for the Weather Dashboard and chatbot, ensuring a responsive layout with a clean and modern design.

3. **script.js**
    - Contains the JavaScript logic for interacting with the OpenWeather API, the chatbot's natural language processing, and the chatbot UI.
    - Key functions:
        - **fetchWeatherData(city)**: Fetches weather data for the specified city.
        - **handleUserMessage()**: Handles the chatbot queries and responses.
        - **getForecast()**: Retrieves the weather forecast for the entered city.
        - **updateTable()**: Populates the forecast table with weather data.
        - **convertUnits()**: Switches between metric and imperial units.
        - **filterRain(), sortTemperature(direction), resetFilters()**: Sorts and filters forecast data.

4. **README.md**
    - Explains the project and provides instructions on running it locally.

## APIs Used
1. **OpenWeather API**: Retrieves weather data and forecasts based on the city.
   - API Endpoint: `https://api.openweathermap.org/data/2.5/weather` for current weather data.
   - API Endpoint: `https://api.openweathermap.org/data/2.5/forecast` for 5-day weather forecasts.
   - API Key: You need an OpenWeather API key to fetch weather data. 

2. **Google Gemini API**: Processes natural language queries for the chatbot.
   - API Key: Google Gemini API key is used to interact with the AI for general responses.

## Setup and Installation

### Prerequisites
- A modern web browser (Chrome, Firefox, etc.)
- Internet connection (for fetching weather data and chatbot responses)
- Node.js (for local development)

### Running the Project Locally
1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-repo-url.git
   ```
   
2. **Navigate to the Project Directory**
   ```bash
   cd your-project-directory
   ```

3. **Install Required Dependencies (Optional)**
   - If you're using Node.js and want to install any additional dependencies (e.g., for a local server), run:
   ```bash
   npm install
   ```

4. **Configure API Keys**
   - Inside the `script.js`, replace the placeholders for API keys with your actual keys:
   ```js
   const OPENWEATHER_API_KEY = 'YOUR_OPENWEATHER_API_KEY';
   const GEMINI_API_KEY = 'YOUR_GOOGLE_GEMINI_API_KEY';
   ```

5. **Open `index.html`**
   - Double-click `index.html` to open it in your browser or use a local server like this:
   ```bash
   npx http-server
   ```

6. **Interacting with the Dashboard**
   - Enter the city in the input field and click "Get Forecast" to fetch weather data.
   - Use the sorting and filtering options to view specific data.
   - You can also chat with the bot by typing your question (e.g., "What's the weather in New York?").

## Customization

### Change Default City
- You can change the default city loaded on page load by modifying the city in the `DOMContentLoaded` event in `script.js`:
```js
document.addEventListener('DOMContentLoaded', () => {
    const defaultCity = 'London'; // Change this to your preferred default city
    document.getElementById('cityInput').value = defaultCity;
    getForecast();
});
```

### Adjust Forecast Data Display
- Modify the number of items displayed per page by changing the `itemsPerPage` constant in `script.js`:
```js
const itemsPerPage = 10; // Adjust this number to change how many rows appear in the table
```

## Contributing
Feel free to fork the project and submit pull requests to improve features or fix bugs.

## License
This project is open-source and licensed under the MIT License.

