# NSE Stock Recommendation Multi-Agent System

## What this project does
This is an AI-powered multi-agent stock recommendation system for the Indian Stock Market (NSE). It uses a **supervisor agent** that coordinates four specialized agents to deliver end-to-end stock analysis and trading recommendations.

### Agent Pipeline:
1. **Stock Finder Agent** — Finds 2 promising NSE-listed stocks for short-term trading
2. **Market Data Agent** — Fetches current price, volume, trends, RSI, moving averages
3. **News Analyst Agent** — Searches recent news and classifies sentiment (positive/negative/neutral)
4. **Price Recommender Agent** — Gives Buy/Sell/Hold recommendation with target price in INR

---

## Project Structure
```
my-project/
  ├── main.py
  ├── .env.example
  ├── requirements.txt
  └── README.md
```

---

## Requirements
- Python 3.10+
- Node.js (required for Bright Data MCP via npx)
- A Bright Data account and API Token
- A Google Gemini API Key

---

## Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

### 2. Install Python dependencies
```bash
pip install -r requirements.txt
```

### 3. Set up environment variables
Create a `.env` file based on `.env.example`:
```bash
cp .env.example .env
```
Then fill in your actual API keys inside `.env`

### 4. Run the project
```bash
python main.py
```

---

## Environment Variables
| Variable | Description |
|---|---|
| `BRIGHT_DATA_API_TOKEN` | Your Bright Data API Token |
| `GOOGLE_API_KEY` | Your Google Gemini API Key |

---

## Example Output
The supervisor agent will coordinate all four agents and print structured output like:
```
Stock 1: RELIANCE (RELIANCE.NS)
  Action: Buy
  Target Price: ₹1,450
  Reason: Strong volume spike, positive news sentiment...

Stock 2: INFY (INFY.NS)
  Action: Hold
  Target Price: ₹1,820
  Reason: Neutral news, RSI approaching overbought...
```

---

## How it works
```
User Query
    ↓
Supervisor Agent
    ↓
Stock Finder Agent → Picks 2 NSE stocks
    ↓
Market Data Agent → Fetches price, volume, indicators
    ↓
News Analyst Agent → Summarizes recent news + sentiment
    ↓
Price Recommender Agent → Buy/Sell/Hold + Target Price
    ↓
Final Recommendation Printed
```
```

---

## requirements.txt
```
python-dotenv
langchain
langgraph
langchain-mcp-adapters
langchain-google-genai
langgraph-supervisor
langchain-core
```

---

## .env.example
```
BRIGHT_DATA_API_TOKEN=your_bright_data_token_here
GOOGLE_API_KEY=your_google_api_key_here
