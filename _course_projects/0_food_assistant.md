---
title: "PlateM8 — AI-Powered Personal Food & Nutrition Assistant"
excerpt: "An AI-powered personal nutrition tracker combining a conversational meal-logging agent, GPT-4o photo analysis, semantic recipe search over 200k+ recipes, live macro rings, and automated email diet summaries — all in a React + Python stack."
collection: course_projects
share: false
related: false
---

**What it is.** PlateM8 is an **AI-powered nutrition assistant** that lets you log meals in natural language, snap a photo of your plate, or search a 200k+ recipe database — all while tracking calories, protein, carbs, and fat in real time. A **ReAct agent** (LangChain + GPT-4o) handles reasoning and tool orchestration; a ChromaDB vector store powers semantic recipe retrieval; and an MCP server exposes email notifications as an agent tool.

**Why it exists.** Calorie tracking apps are either too rigid (manual lookup every entry) or too vague (no macro breakdown). PlateM8 removes friction: describe your meal in plain language or photograph it, and the agent fills in the nutritional details automatically — then sends a diet summary straight to your inbox.

---

## Features

| Feature | Description |
|---|---|
| **AI Chat Agent** | Describe what you ate in natural language — the ReAct agent looks up macros from the recipe database or USDA FoodData Central and logs the meal |
| **Recipe Search** | Finds the 10 closest matching recipes from a 200k+ recipe dataset using semantic search (ChromaDB + SentenceTransformers); shows ingredients, steps, and macros |
| **Analyze My Meal** | Take or upload a photo of your plate — GPT-4o Vision detects each food item, USDA enriches the macros, and you can edit before saving |
| **Macro Rings** | Live dashboard with calorie, protein, carb, and fat progress rings that update on every meal save |
| **Smart Targets** | Auto-calculates daily calorie and macro targets using the **Mifflin–St Jeor equation** based on age, weight, height, activity level, and weight goal |
| **Profile & Activity** | Edit photo, body metrics, per-sport weekly frequency, and weight goal |
| **Monthly Calendar** | Visualises daily intake history for the current month |
| **Email Notifications** | Sends a diet summary email (consumed vs. remaining macros) to the user's registered address on every meal save via an **MCP tool** |

---

## Architecture

### Agent pipeline

The core is a **LangChain ReAct agent** backed by GPT-4o. On each meal description it:

1. **Recalls** the user's profile and daily targets  
2. **Searches** the recipe vector store (ChromaDB) for matching dishes  
3. **Enriches** macros from the USDA FoodData Central API when needed  
4. **Logs** the meal and triggers the MCP email tool  

### Photo analysis

Meal photos go through a **GPT-4o Vision** call that identifies each food item. Detected items are then individually queried against the USDA API to retrieve accurate per-100g macros, which the user can review and adjust before saving.

---

## Tech Stack

**Frontend**
- React 19 + Vite
- Vanilla CSS (no UI framework)

**Backend** (Python 3.11)
- `openai` — GPT-4o for chat reasoning and meal photo vision
- `langchain` + `langchain-openai` — ReAct agent orchestration
- `chromadb` + `sentence-transformers` — semantic recipe retrieval over 200k+ recipes
- `mcp` — MCP server exposing email notifications as an agent tool
- USDA FoodData Central API — accurate per-100g nutritional data

---

## How It Works — End to End

1. **User describes a meal** in the chat (e.g., *"I just had 200g of grilled salmon with rice"*)
2. The **ReAct agent** extracts food items, fetches macros from the vector store or USDA, and writes the meal entry to the user's daily log
3. **Macro rings** on the dashboard update instantly to reflect consumed vs. remaining targets
4. An **email summary** is dispatched via the MCP email tool, listing each food logged and remaining daily budget
5. Alternatively, the user can snap a photo → **GPT-4o Vision** identifies items → macros are fetched and previewed before confirming

---

*This page summarizes the project for portfolio visitors. The full source includes ETL scripts for the recipe dataset, vector ingestion pipeline, and frontend build configuration.*
