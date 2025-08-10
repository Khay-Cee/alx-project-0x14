# alx-project-0x14

## API Overview
The MoviesDatabase API provides access to a wide range of movie-related data, including movie details, search functionality, trending movies, and more. It allows developers to retrieve information about movies, TV shows, actors, and related media, making it ideal for building movie discovery and information apps.

## Version
v1 (as per MoviesDatabase API documentation)

## Available Endpoints
- `/titles/search/title`: Search for movies or TV shows by title.
- `/titles/{id}`: Get detailed information about a specific movie or TV show by its ID.
- `/titles/trending`: Retrieve a list of trending movies or TV shows.
- `/actors/{id}`: Get details about a specific actor.
- `/genres`: List all available genres.

## Request and Response Format
Requests are typically made using HTTP GET with required query parameters. Responses are returned in JSON format. Example request and response:

**Request:**
```
GET /titles/search/title?title=Inception
Headers: { 'X-API-Key': 'YOUR_API_KEY' }
```

**Response:**
```
{
  "results": [
    {
      "id": "tt1375666",
      "title": "Inception",
      "year": 2010,
      "genres": ["Action", "Sci-Fi"],
      ...
    }
  ]
}
```

## Authentication
All requests require an API key, which must be included in the request headers as `X-API-Key`. Without a valid API key, requests will be denied.

## Error Handling
Common error responses include:
- 401 Unauthorized: Missing or invalid API key.
- 404 Not Found: The requested resource does not exist.
- 429 Too Many Requests: Rate limit exceeded.
- 500 Internal Server Error: An error occurred on the server.

Handle errors by checking the HTTP status code and displaying appropriate messages to users.

## Usage Limits and Best Practices
- The API enforces rate limits (e.g., 1000 requests per day per API key).
- Cache responses where possible to reduce API calls.
- Always check for errors in the response and handle them gracefully.
- Do not expose your API key in client-side code.
