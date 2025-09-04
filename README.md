# Weather Forecast MCP Server

A Model Context Protocol (MCP) server that provides weather forecasting capabilities using the National Weather Service (NWS) API. This server enables AI assistants to fetch weather forecasts and alerts for locations within the United States.

## Features

- **Weather Forecasts**: Get detailed real-time weather forecasts for any US location using latitude and longitude coordinates
- **Weather Alerts**: Retrieve active weather alerts and warnings for any US state
- **NWS Integration**: Direct integration with the official National Weather Service API

## Tools Available

### `get_forecast`
Retrieves weather forecast data for a specific location.

**Parameters:**
- `latitude` (number): Latitude of the location (-90 to 90)
- `longitude` (number): Longitude of the location (-180 to 180)

**Returns:** Detailed forecast periods including temperature, wind conditions, and weather descriptions.

### `get_alerts`
Gets active weather alerts for a specified state.

**Parameters:**
- `state` (string): Two-letter state code (e.g., "CA", "NY", "TX")

**Returns:** List of active weather alerts including severity, status, and descriptions.

## Prerequisites

- Node.js 18
- npm or pnpm package manager

## Installation

1. Clone or download this repository
2. Install dependencies:
   ```bash
   npm install
   # or
   pnpm install
   ```

3. Build the project:
   ```bash
   npm run build
   # or
   pnpm run build
   ```

## Running Locally

### Development Mode
To run the server in development mode with auto-rebuild:

```bash
npm run dev
# or
pnpm run dev
```

### Production Mode
To run the built server:

```bash
npm start
# or
node build/index.js
```

## Adding to MCP Clients

```json
{
  "mcpServers": {
    "weather-forecast": {
      "command": "node",
      "args": ["/ABSOLUTE/PATH/TO/PARENT/FOLDER/weather/build/index.js"],
      "env": {}
    }
  }
}
```

## Usage Examples

Once connected to an MCP client, you can use natural language to request weather information:

- "What's the weather forecast for San Francisco?" (Assistant will ask for coordinates)
- "Get weather alerts for California"
- "Show me the forecast for latitude 37.7749, longitude -122.4194"
- "Are there any weather warnings in Texas?"

## API Limitations

- **Geographic Coverage**: Only supports locations within the United States
- **Data Source**: Uses the National Weather Service API, which may have rate limits
- **Coordinate Precision**: Coordinates are rounded to 4 decimal places for API compatibility

---

For more information about the Model Context Protocol, visit [https://modelcontextprotocol.io](https://modelcontextprotocol.io)
