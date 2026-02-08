# 🎯 AI Auction Game with LangGraph & OpenAI

AI Auction Game is a **Node.js-based interactive web application** that simulates a **repeated sealed-bid all-pay auction** with rising maintenance costs, powered by an **LLM-driven adaptive agent** built using **LangGraph and OpenAI**.

The system allows human players to compete against an AI that dynamically adjusts its bidding strategy based on game history, capital constraints, and opponent behavior.

We adopted an elevator-themed setting inspired by a teammate’s original idea: designing a bidding system for lift usage. Living on the 38th floor, he often experiences overcrowded lifts in the mornings, motivating a playful yet realistic application of competitive resource allocation.

------------------------------------------------------------------------

## 📊 Project Overview

This project was built by my team and me in 24hrs during the **NUS Hack&Roll 2026 Hackathon** to explore how large language models can be integrated into strategic decision-making systems under financial and game-theoretic constraints.

Key motivations include:

- ❌ Traditional game bots rely on fixed heuristics.
- ❌ Static strategies fail under changing capital conditions.
- ❌ Most examples of LLM agents are not embedded in real-time systems.
- ❌ Players rarely receive meaningful feedback on their strategic behavior.
- ❌ Post-game analysis is often limited to raw scores and outcomes.

Thus, we aim to:

- ✅ Provide players with structured, AI-generated performance reports.
- ✅ Help players understand their risk posture and capital management.
- ✅ Encourage strategic reflection through personalized feedback.
- ✅ Bridge gameplay and learning via financial-style analytics.

This project demonstrates how LLMs can:

-   Reason over structured game state.
-   Forecast opponent behavior.
-   Adapt strategies across rounds.
-   Balance risk, liquidity, and scoring objectives.

All within a live, interactive web environment.

------------------------------------------------------------------------

## ✨ Key Features

-   🤖 LLM-powered adaptive bidding agent (LangGraph + OpenAI)
-   💰 All-pay auction with rising maintenance fees
-   📈 Dynamic opponent modeling and bid forecasting
-   🧠 Multi-step reasoning pipeline with guardrails
-   🌐 Browser-based interface with REST API backend
-   🔄 Safe game restarts and state management
-   📊 Automatic post-game performance reports

------------------------------------------------------------------------

## 🧠 What This Project Explores

-   LangGraph agent orchestration
-   Structured LLM outputs with Zod validation
-   Game-theoretic strategy
-   Liquidity management
-   Human--AI interaction
-   Real-time AI systems

------------------------------------------------------------------------

## 🧰 Tech Stack

### Language

    - JavaScript (Node.js, ES Modules)

### Libraries

    - @langchain/langgraph
    - @langchain/openai
    - zod
    - dotenv
    - readline-sync

------------------------------------------------------------------------

## 📁 Project Structure

    AI-Auction-Game/
    ├── public/
    │ ├── app.js
    │ ├── index.html
    │ ├── style.css
    │ ├── sprite.png
    │ ├── background.jpg
    │ └── start_img.jpg
    ├── agent_pipeline.mjs      # LLM logic & reasoning graph
    ├── game_core.mjs           # Game engine and rules
    ├── server.mjs              # HTTP server and API routes
    ├── package.json            # Dependencies and scripts
    ├── package-lock.json       # Dependency lock file
    ├── .env                    # OpenAI API key (NOT COMMITTED)
    └── README.md               # Documentation

------------------------------------------------------------------------

## ⚠️ Disclaimer

This project is intended for **educational and experimental purposes only**.

It is not designed for real-world financial use and does not represent investment or economic advice.

All gameplay mechanics are simulated.

------------------------------------------------------------------------

## ▶️ How to Use

### 1. Clone

``` bash
git clone https://github.com/your-username/AI-Auction-Game.git
cd AI-Auction-Game
```

### 2. Install

``` bash
npm install
```

### 3. Configure

Create `.env`:

    OPENAI_API_KEY=your_api_key_here

### 4. Run

``` bash
npm start
```

### 5. Open

    http://localhost:3000

------------------------------------------------------------------------

## 🎮 Gameplay

1. Click Start Game.
2. Enter your bid for each round.
3. Both player and AI pay their bids (all-pay rule).
4. Higher bid wins the round (gain 1 point).
5. Maintenance fees increase over time.
    - $0 for rounds 1 and 2.
    - $5 for rounds 3 and 4.
    - $10 for rounds 5 and 6.
    - ...
6. Game ends when a player cannot continue.
7. A walkover will then occur for the remaining player.
    - Assumes bet of 0 from the bankrupt player.
    - Other player gets a point as long as he can pay the maintenance fee of that round.
8. An AI-powered performance report will then be generated based on the player's performance.

------------------------------------------------------------------------

## 📊 Post-Game Report

After the game ends, the system generates an AI-powered performance report including:

- Risk posture
- Capital efficiency
- Liquidity management
- Emotional discipline
- Strategic adaptability

These insights are produced using a separate LLM-based analysis pipeline and are designed to help players reflect on and improve their long-term decision-making strategies.

------------------------------------------------------------------------


## 🔌 API

  Method   Endpoint       Description
  -------- -------------- -------------
  GET      /api/state     Get current game state
  POST     /api/bid       Submit player bid
  POST     /api/start     Start new game
  POST     /api/restart   Restart game

------------------------------------------------------------------------

## 🔒 Security

-   API keys stored locally
-   Do not commit `.env`
-   No personal data stored

------------------------------------------------------------------------

## 📬 Contact

Open an issue or contact via LinkedIn.
