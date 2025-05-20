
# 🌐 API Gateway – Airline Ticketing System

This project is an API Gateway implemented using **Ocelot** for routing requests to backend airline APIs. It serves as the central entry point for client applications and securely forwards requests to the appropriate downstream services.

## 📌 Features

- Built using **.NET 8** and **Ocelot**
- Reverse proxy for the following services:
  - Flight Search (`GET /flights`)
  - Ticket Purchase (`POST /tickets/buy`)
  - Check-in (`POST /tickets/checkin`)
- Easy-to-configure via `ocelot.json`
- HTTPS support and environment-based configuration

## ⚙️ Routes Configuration (`ocelot.json`)

```json
{
  "Routes": [
    {
      "DownstreamPathTemplate": "/api/v1/flights",
      "UpstreamPathTemplate": "/flights",
      "UpstreamHttpMethod": [ "GET" ],
      "DownstreamHostAndPorts": [
        { "Host": "gd-airline-ticket-api.azurewebsites.net", "Port": 443 }
      ],
      "DownstreamScheme": "https"
    },
    {
      "DownstreamPathTemplate": "/api/v1/tickets/buy",
      "UpstreamPathTemplate": "/tickets/buy",
      "UpstreamHttpMethod": [ "POST" ],
      "DownstreamHostAndPorts": [
        { "Host": "gd-airline-ticket-api.azurewebsites.net", "Port": 443 }
      ],
      "DownstreamScheme": "https"
    },
    {
      "DownstreamPathTemplate": "/api/v1/tickets/checkin",
      "UpstreamPathTemplate": "/tickets/checkin",
      "UpstreamHttpMethod": [ "POST" ],
      "DownstreamHostAndPorts": [
        { "Host": "gd-airline-ticket-api.azurewebsites.net", "Port": 443 }
      ],
      "DownstreamScheme": "https"
    }
  ],
  "GlobalConfiguration": {
    "BaseUrl": "http://localhost:5173"
  }
}
```

## 🧱 Project Structure

| File              | Description                                      |
|-------------------|--------------------------------------------------|
| `Program.cs`      | Entry point that sets up Ocelot and starts app   |
| `ocelot.json`     | Main configuration file for Ocelot routing       |
| `launchSettings.json` | Environment and port setup for development |

## 🚀 Running the Gateway Locally

### Requirements
- [.NET 8 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)


### Video Link
https://youtu.be/j5mACjZvCzA







## 👨‍💻 Authors

Developed by **Gulce DOGRUOZ** – SE4458 Assignment 2
