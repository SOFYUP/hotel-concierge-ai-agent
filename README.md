# 🏨 Hotel Alvear AI Concierge Agent

> AI Concierge Agent for Hotel Alvear Palace - Kaggle AI Agents Intensive Capstone 2026

## 🎯 What it does

Intelligent digital concierge for Hotel Alvear Palace (Buenos Aires) that combines:
- 🌤️ Real-time weather via OpenWeatherMap
- 🍽️ Health-aware restaurant analysis (celiac, vegan, vegetarian, diabetic, allergies)
- 🗺️ Real distances and Google Maps routes from the hotel
- 🏨 Hotel services information (spa, restaurant, gym, pool)
- 🔍 Places search with reviews analysis powered by Gemini AI

## ✨ Key Innovation

Instead of showing restaurants by star rating, the agent analyzes **real user reviews** to detect safety mentions specific to each health profile (cross-contamination, hidden gluten, etc.)

## 🛠️ Tech Stack

- Google ADK 2.0 + Gemini 2.5 Flash
- Google Places API (New) + Routes API
- OpenWeatherMap API
- Python + pytest (13 security tests)

## 🚀 Setup

### Requirements
- Python 3.11+
- uv package manager
- API keys: Gemini, Google Places, OpenWeatherMap

### Installation

```bash
git clone https://github.com/SOFYUP/hotel-concierge-ai-agent
cd hotel-concierge-ai-agent
uv sync
```

### Configure API keys

```bash
export GEMINI_API_KEY="your-key"
export PLACES_API_KEY="your-key"
export OPENWEATHER_API_KEY="your-key"
```

### Run

```bash
uv run adk web --host 127.0.0.1 --port 8080
```

Open http://127.0.0.1:8080 in Chrome.

### Run tests

```bash
uv run pytest tests/test_security.py -v
```

## 🔒 Security

- Prompt injection protection (11 patterns)
- Guardrails in agent instruction
- Full execution logging
- 13 automated security tests

## 📊 Agent Architecture
User → Orchestrator Agent (Gemini 2.5 Flash)
├── get_clima() → OpenWeatherMap API
├── analizar_restaurantes_por_perfil() → Places API + Gemini
├── buscar_lugares() → Places API + Routes API
└── get_servicios_hotel() → Hotel data

## 🏆 Kaggle Capstone

Built for the AI Agents Intensive Vibe Coding Capstone - Google & Kaggle 2026
Category: Concierge Agents