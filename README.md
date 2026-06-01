# PAGASA Forecast API

![CI](https://github.com/joshuasarmiento/pagasa-forecast-api/actions/workflows/ci.yml/badge.svg)
![Python Version](https://img.shields.io/badge/python-3.9%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)

This project provides a simple Python API to fetch daily weather forecasts from the PAGASA (Philippine Atmospheric, Geophysical and Astronomical Services Administration) website. It scrapes data from the official PAGASA weather forecast page and serves it as a clean JSON API.

## Features

*   **Daily Weather Forecast:** Retrieves comprehensive daily weather information including synopsis, weather conditions, wind and coastal water conditions, temperature, humidity, tides, and astronomical information.
*   **CORS Enabled:** Cross-Origin Resource Sharing is enabled for seamless frontend integrations (currently allows `localhost` origins locally, and `*` in production).
*   **Data Caching:** Implements a basic in-memory caching mechanism to reduce the number of requests to the PAGASA website and improve response times.
*   **Serverless Ready:** Configured to be easily deployed to Vercel via the included `vercel.json`.

## Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/joshuasarmiento/pagasa-forecast-api.git
    cd pagasa-forecast-api
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

## Usage

### Local Development

To start the API server locally for development or testing, run the `local_server.py` script:

```bash
python local_server.py
```

The API will be accessible at `http://localhost:8000`.

### Vercel Deployment

This project is configured for Vercel out of the box. You can deploy it using the Vercel CLI:

```bash
npm i -g vercel
vercel
```

## API Endpoints

### `GET /api/pagasa-forecast` (or `/` locally)

Returns the daily weather forecast data in JSON format.

**Example Response:**

```json
{
    "issued_at": "Issued at 5:00 AM, 23 July 2025",
    "synopsis": "...",
    "forecast_weather_conditions": [
        {
            "place": "Luzon",
            "weather_condition": "...",
            "caused_by": "...",
            "impacts": "..."
        }
    ],
    "forecast_wind_conditions": [
        {
            "place": "Luzon",
            "speed": "...",
            "direction": "...",
            "coastal_water": "..."
        }
    ],
    "temperature_humidity": {
        "Metro Manila": {
            "max": {"value": "32°C", "time": "2:00 PM"},
            "min": {"value": "25°C", "time": "5:00 AM"}
        }
    },
    "astronomical_information": {
        "Sun Rise": "5:30 AM",
        "Sun Set": "6:30 PM",
        "Moon Rise": "...",
        "Moon Set": "...",
        "Illumination": "..."
    },
    "tidal_predictions": [
        {
            "type": "High Tide",
            "value": "1.5m",
            "time": "10:00 AM"
        }
    ]
}

## Security

Please read our [Security Policy](SECURITY.md) for details on our vulnerability disclosure process.

## Technologies Used

*   Python 3.9
*   `http.server` (built-in Python module)
*   `requests`
*   `BeautifulSoup4`
*   Vercel Serverless Functions

## License

This project is licensed under the [MIT License](LICENSE).
