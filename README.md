# 🍳 Foodie Finder

> An AI-powered recipe recommendation platform that turns your available ingredients into delicious, ready-to-cook recipes — complete with nutritional info and images.

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-REST%20API-black.svg)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📖 Overview

Foodie Finder is a full-stack AI recipe recommendation platform built with a RESTful Flask backend, LLM-powered recipe generation, and integration with multiple external APIs. Users input the ingredients they have on hand, and the platform generates personalized recipe suggestions with nutritional breakdowns and images — all served through a fast, cached, and rate-limited API.

## ✨ Features

- 🤖 **AI-Powered Recipe Generation** — Dynamic recipe creation for 50+ ingredient combinations using LLM integration
- ⚡ **High Performance** — Sub-200ms average response time across all endpoints
- 🔌 **Multi-API Integration** — Combines 3 external APIs for recipe metadata, nutritional data, and images
- 🚀 **In-Memory Caching** — Reduces response latency by ~35% on repeated requests
- 🏗️ **Modular MVC Architecture** — Clean separation of models, views, and controllers for maintainability
- 🛡️ **Input Preprocessing & Rate Limiting** — Validates requests and protects against abuse
- 📊 **99%+ Uptime** — Reliable performance across all tested deployments

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python, Flask |
| Architecture | RESTful API, MVC pattern |
| AI/LLM | [Add your LLM provider, e.g. OpenAI / Gemini] |
| Caching | In-memory caching layer |
| External APIs | [Add API names: e.g. Spoonacular, Edamam, Unsplash] |
| Frontend | [Add your frontend tech, e.g. HTML/CSS/JS] |

## 🏗️ Architecture
foodie-finder/
├── app.py                 # Application entry point
├── controllers/            # Request handling logic
├── models/                  # Data models & schemas
├── services/                # External API integration & caching
├── utils/                   # Input preprocessing, rate limiting
├── static/                  # CSS, JS, images
├── templates/                # HTML templates
├── requirements.txt
└── README.md
## 🏗️ Architecture

Foodie Finder follows a modular MVC (Model-View-Controller) design to keep concerns cleanly separated and the codebase easy to extend.

**Request Flow:**

1. **Client Request** → A user submits ingredients via the frontend or API client.
2. **Controller Layer** → Routes the request, validates and preprocesses input, and applies rate-limiting checks.
3. **Service Layer** → Coordinates calls to the LLM for recipe generation and to the 3 external APIs (recipe metadata, nutrition data, images). Frequently requested data is served from an in-memory cache to cut latency.
4. **Model Layer** → Structures and validates the data returned from the AI and external APIs into a consistent recipe schema.
5. **Response** → A formatted JSON response is sent back to the client with the recipe, nutritional info, and image — typically in under 200ms.

**Key Design Decisions:**

- **Separation of concerns:** Controllers handle HTTP logic only; business logic and API orchestration live in the service layer, keeping routes thin and testable.
- **Caching strategy:** An in-memory cache sits in front of external API calls, cutting repeated-request latency by ~35% and reducing dependency on third-party rate limits.
- **Resilience:** Input preprocessing and rate-limiting at the controller layer protect the system from malformed requests and abuse, contributing to 99%+ uptime in testing.
## 📡 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/recipes` | Fetch recipe suggestions based on ingredients |
| POST | `/api/recipes/generate` | Generate a new recipe using AI |
| GET | `/api/recipes/<id>` | Get details for a specific recipe |
| GET | `/api/nutrition/<id>` | Fetch nutritional data for a recipe |
| GET | `/api/images/<id>` | Fetch recipe image |
| POST | `/api/ingredients` | Submit ingredient list |
| GET | `/api/health` | Health check endpoint |
| GET | `/api/cache/status` | View caching layer status |

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- pip

### Installation

1. **Clone the repository**
```bash
   git clone https://github.com/asrithachouhan/Foodie-Finder-.git
   cd Foodie-Finder-
```

2. **Create a virtual environment**
```bash
   python -m venv venv
   venv\Scripts\activate
```

3. **Install dependencies**
```bash
   pip install -r requirements.txt
```

4. **Set up environment variables**

   Create a `.env` file in the root directory:
API_KEY_1=your_api_key_here
API_KEY_2=your_api_key_here
API_KEY_3=your_api_key_here
5. **Run the application**
```bash
   python app.py
```

6. Open `http://127.0.0.1:5000` in your browser.

## 📈 Performance Highlights

- Engineered 8+ REST API endpoints handling dynamic recipe generation with **sub-200ms response time**
- Reduced response latency by **~35%** through in-memory caching of external API calls
- Achieved **99%+ uptime** across all tested deployments through robust error handling and modular design

## 🤝 Contributing

This was built as a course project (Feb 2025 – Apr 2025). Contributions, suggestions, and feedback are welcome — feel free to open an issue or submit a pull request.

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Asritha Chouhan**
[GitHub](https://github.com/asrithachouhan)
