# 🌎 Agentic-Travel

**AI Travel Planner with Live Booking & Autonomous Itinerary Generation**

Agentic-Travel is a sophisticated, multi-agent AI system designed to take a vague trip idea and autonomously transform it into a fully booked reality. It researches destinations, builds customized day-by-day itineraries, checks live prices, and books flights and hotels via real-world APIs.

---

## ✨ Key Features

- **💬 Interactive Clarification**: Gathers context interactively, understanding your dates, budget, and specific travel interests.
- **🗺️ Intelligent Destination Research**: Leverages external APIs to dynamically find and evaluate the best destinations for your criteria.
- **📅 Day-by-Day Itinerary Generation**: Builds highly structured, logical daily schedules complete with Points of Interest (POIs) and local recommendations.
- **💰 Live Pricing & Availability**: Checks real-time flight and hotel data to ensure recommendations fit your exact budget.
- **🎫 Automated Booking**: Handles necessary reservations and automatically generates and emails a PDF itinerary.

---

## 🏗️ How It Works (Agent Architecture)

This system is powered by an orchestrated team of specialized AI agents:

1. **Preference Gathering Agent**: Acts as the initial interface, clarifying user constraints (dates, budgets, interests).
2. **Destination Agent**: Researches and presents viable destination options based on the gathered preferences.
3. **Itinerary Planner**: Constructs the granular, day-by-day schedule, organizing POIs logically to minimize travel time.
4. **Pricing Agent**: Interfaces with live booking APIs to fetch real-time fares, rates, and availability.
5. **Booking Agent**: Confirms the final reservations, handles real-world side effects, and emails the compiled PDF itinerary to the user.

---

## 🛠️ Tech Stack

- **LLM & Orchestration**: [Claude API](https://anthropic.com/claude), [LangGraph](https://python.langchain.com/docs/langgraph/)
- **Integration APIs**: Amadeus API / Skyscanner, Google Places API, Booking.com API
- **Frontend**: [Next.js](https://nextjs.org/)
- **Backend / Workflows**: Python

---

## 📂 Project Structure

```text
agents/                  # Core AI agents (preference, destination, itinerary, etc.)
tools/                   # External API integrations (Amadeus, Google Places, Booking)
workflows/               # LangGraph state machine definitions
app/
  ├── api/               # Backend API routes (e.g., FastAPI)
  └── web/               # Next.js frontend application
data/                    # Mock data, pricing rules, and sample trips
outputs/                 # Generated itineraries and run logs
tests/                   # Unit and integration tests
config/                  # Environment-specific configurations (dev, staging, prod)
```

---

## 🧠 Key Agentic Patterns

This project heavily relies on advanced agentic design patterns:
- **Clarification Loop**: The system knows when to ask follow-up questions rather than hallucinating assumptions.
- **Parallel API Calls**: Agents concurrently fetch pricing and availability to optimize response times.
- **State Machine Workflow**: Robust state management using LangGraph to pass context reliably between agents.
- **Real-World Side Effects**: Safe execution of bookings and email dispatching.

---

## 🎯 Stretch Goals

- **Real-Time Re-planning**: Dynamically adjust itineraries and re-book if a flight gets delayed or a POI closes unexpectedly.
- **Expense Tracking**: Granular budget management and visual breakdowns of spending.
- **Group Travel Consensus**: Allow multiple users to input preferences and vote on generated itineraries.
