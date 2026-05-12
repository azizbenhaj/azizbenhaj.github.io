---
title: "My Car Assistant 2.0 — LLM Agent Car Search"
excerpt: "A web application that acts as a car assistant: describe a buy or sell goal in chat, an LLM agent workflow (LangGraph + LangChain, backed by Ollama) turns it into a structured vehicle profile, queries a PostgreSQL table of real listings, ranks matches, and shows cards, charts, maps, and downloadable PDFs."
collection: course_projects
share: false
related: false
---

**What it is.** A small web application that acts as a **car assistant**: you describe a buy or sell goal in chat, an **LLM agent workflow** (LangGraph + LangChain, backed by **Ollama**) turns that into a **structured vehicle profile**, then the app **queries a PostgreSQL table of real listings**, **ranks** matches, and shows **cards, charts, maps**, and **downloadable PDFs**. Everything runs against **data you host yourself** (not a third-party search API).

**Why it exists.** Ordinary classified sites make you guess filters and scroll long, flat lists. This tool keeps one **consistent profile** across follow-up messages, then returns a **short ranked shortlist** with **match percentages** and visual summaries instead of raw tables only.

---

## What you can do (features)

- **Chat-driven profile** — Describe the car in natural language; the assistant fills **intent** (buy/sell), **maker**, **model**, **year**, **kilometrage**, and optional details, and asks only for what is still missing.
- **LLM agent pipeline** — **Extract** draft fields from the message, then **evaluate / normalize** them in a second pass so downstream SQL sees stable JSON.
- **PostgreSQL search** — Parameterized listing queries with tolerances on year and mileage, plus text matching on brand and model.
- **Ranked results** — Up to **20 listing cards** with scores, links, and supporting metrics—not an unprioritized dump.
- **Analytics** — **Plotly** and **Matplotlib** charts (price vs km, distributions, etc.) and **maps** where geographic fields support them.
- **PDF exports** — **ReportLab** dossiers: listing blocks with thumbnails and hyperlinks, combined chart pages; exports from the main flow, from **sidebar saves**, and from **compare mode**.
- **Session saves** — Completed runs **autosave** to the sidebar; **Load** restores a profile and listings slice, **PDF** re-exports, **Del** removes a save.
- **Chat lock after success** — After a full search, the chat **locks** until **Start over** or **Load** so the UI state stays clear.
- **Compare two or three cars** — Pick **2 or 3** saved profiles, run **Compare** for overlaid charts (color order matches selection), tables, map, and a **comparison PDF** (browser download name `car_listings_compare.pdf`). No chat in this mode.
- **Fuzzy and numeric helpers** — **RapidFuzz** for string alignment, **pandas** / **NumPy** for aggregates and simple regressions on listing fields where relevant.

---

## Interface in pictures

The home screen starts either a **single-car** chat flow or **Compare** (once you have enough saves).

![Home — choose Buy or sell a car or Compare cars](/files/Screenshot%202026-05-12%20at%2016.32.43.png)

In **Buy or sell a car**, you describe the vehicle at the bottom; the assistant completes required fields before it searches.

![Buy or sell — chat and extraction flow](/files/Screenshot%202026-05-12%20at%2016.32.58.png)

**Compare cars** uses sidebar saves: multiselect **2 or 3** profiles and open the comparison workspace.

![Compare cars — multiselect and comparison workspace](/files/Screenshot%202026-05-12%20at%2016.34.26.png)

After a search you see **ranked cards**, metrics, charts/maps when data allows, and actions to **download** reports.

![Listings, analytics, and export actions](/files/Screenshot%202026-05-12%20at%2016.33.20.png)

---

## Example PDFs

Sample exports (same paths as in the repo—adjust URLs when you host the files on your portfolio site).

- **[Quick listing PDF](/files/car_listings_quick.pdf)** — From a completed **Buy or sell** run (or the main **Download PDF**): top listings with photos and links plus the combined chart page.
- **[Sidebar listing PDF](/files/Porsche_911_2026_6d70881e_listings.pdf)** — From **Sidebar → PDF** on a saved profile; filename reflects the save label and session id.

*A dedicated multi-car compare export is typically saved as **`car_listings_compare.pdf`** when you use **Compare** → **Download comparison PDF**.*

---

## Stack (libraries)

`langgraph`, `langchain-core`, `langchain-ollama`, `streamlit`, `psycopg`, `pandas`, `numpy`, `rapidfuzz`, `matplotlib`, `plotly`, `kaleido`, `reportlab`, `pillow`, `geonamescache` — plus **PostgreSQL**, **Ollama**, and **Python 3**.

---

*This page summarizes behavior and UI for portfolio visitors who are not browsing the source tree.*
