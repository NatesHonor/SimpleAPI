# Player API

This is a simple Express-based API for managing player data and information. It allows you to retrieve player information, update player data, and manage player online status. The API uses an API key for authentication and authorization.

## Getting Started

1. Install the required dependencies using npm:

`npm install express body-parser`


2. Run the server:

`node app.js`


3. Access the API endpoints at `http://localhost:3000`.

## API Endpoints

### Get Player Information

Retrieve player information based on their player name.

| Endpoint | Method | Use |
| ----------- | ----------- | ----------- |
| /player/:playerName | GET | Retrieve player information based on their player name. |
| /player/level | POST | Update the level of a player. |
| /player/rank | POST | Update the rank of a player. |
| /player/playtime | POST | Update Player Playtime |
| /player/join | POST | Indicate that a player has joined the server. |
| /player/leave | POST | Indicate that a player has left the server. |
## Request Bodies

### Level

**Request Body:**

```json
{
"playerName": "PlayerName",
"level": 10
}
``` 

### Rank

```json
{
  "playerName": "PlayerName",
  "rank": "VIP"
}
``` 

### Playtime

```json
{
  "playerName": "PlayerName",
  "playtimeMillis": 3600000
}
```

### Player Join

```json

{
  "playerName": "PlayerName"
}
```

### Player Leave

```json

{
  "playerName": "PlayerName"
}
```

## API Key

The API key is required to access the API. The key is automatically generated when the server starts and can be found in the server console logs.
To use the API, include the API key in the request headers:

Header: X-API-Key

Value: <Your API Key>

    403 Forbidden: Invalid API key.
    500 Internal Server Error: Failed to fetch player avatar or other internal errors.