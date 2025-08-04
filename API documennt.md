# ☁️ Weather App API Documentation

Welcome to the **Weather App REST API** documentation. This fictional API provides real-time and forecasted weather data for cities around the world.

This guide includes authentication steps, endpoint descriptions, sample requests and responses, error codes, and versioning details.

---

## 📖 Overview

The **Weather API** allows developers to retrieve current weather conditions and 5-day forecasts for specified locations.

Base URL:
https://api.weatherapp.io/v1

---

## 🔐 Authentication

All endpoints require an API key.

**To authenticate**, pass your API key in the `Authorization` header:

```http
GET /weather?city=lagos
Authorization: Bearer YOUR_API_KEY
Note: You can register for an API key at: https://weatherapp.io/signup
 Endpoints
✅ GET /weather
Returns current weather conditions for a city.

Request:

http
Copy
Edit
GET /weather?city=lagos
Authorization: Bearer YOUR_API_KEY
Response:

json
Copy
Edit
{
  "city": "Lagos",
  "temperature": 30,
  "humidity": 78,
  "description": "Partly cloudy",
  "wind_speed": 10
}
⛅ GET /forecast
Returns a 5-day forecast for a city.

Request:

http
Copy
Edit
GET /forecast?city=lagos
Authorization: Bearer YOUR_API_KEY
Response:

json
Copy
Edit
{
  "city": "Lagos",
  "forecast": [
    { "day": "Monday", "temperature": 29, "description": "Sunny" },
    { "day": "Tuesday", "temperature": 28, "description": "Rain showers" },
    { "day": "Wednesday", "temperature": 30, "description": "Cloudy" },
    { "day": "Thursday", "temperature": 27, "description": "Stormy" },
    { "day": "Friday", "temperature": 31, "description": "Sunny" }
  ]
}
⚠️ Error Handling
The API uses standard HTTP status codes. Errors are returned in the following format:

json
Copy
Edit
{
  "error": "Invalid API Key",
  "code": 401
}
Status Code	Description
200	Success
400	Bad Request
401	Unauthorized / Invalid Key
404	City not found
500	Internal Server Error

🗂️ Versioning
Current version: v1

Use the version in the base URL:

arduino
Copy
Edit
https://api.weatherapp.io/v1
Future versions will follow semantic versioning (v1, v2, etc.).
