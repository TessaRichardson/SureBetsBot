## SureBets Arbitrage Bot 🌐💰

Optimize risk-free betting opportunities with automated odds scanning and Kelly-optimal staking.

SureBets Arbitrage Bot is a Python-based project that finds sports betting arbitrage opportunities (surebets) across different bookmakers and determines the optimal stakes to wager using the Kelly Criterion. It features a modular design with components for fetching odds, calculating arbitrage, sizing bets, and a Streamlit dashboard for visualization. This project showcases ##how a data-driven approach can exploit pricing inefficiencies in betting markets to achieve steady bankroll growth with minimal risk.

Table of Contents
	•	Motivation
	•	Features
	•	Architecture
	•	Installation
	•	Usage
	•	Running the Bot
	•	Using the Dashboard
	•	Example Output
	•	Visualizations
	•	Future Improvements
	•	Project Structure
	•	License

# Motivation

In sports betting, arbitrage betting involves placing bets on all possible outcomes of an event using different odds providers to guarantee a profit, no matter the result. Such opportunities arise due to inconsistencies in bookmakers’ odds. They are risk-free in theory but hard to find manually and often yield small margins (1-5%). This project was motivated by the challenge of automating the detection of these surebets in real-time and maximizing profit through optimal bet sizing. We apply the Kelly Criterion for bankroll management – a strategy known to maximize long-term growth – to decide how much to stake on each arbitrage opportunity. The result is a bot that can potentially turn many small, low-risk profits into meaningful returns over time. Beyond betting, the project was also an exercise in building a robust data pipeline and interactive tool, demonstrating skills in API integration, algorithmic logic, and web app development.

Features
	•	Automated Odds Fetching: Continuously retrieves live odds from multiple bookmakers or an odds API. Supports a mock mode with sample data for testing and development.
	•	Real-Time Arbitrage Detection: Scans the odds for arbitrage opportunities in sports events (two-outcome and three-outcome markets). Flags opportunities where the combined implied probability falls below 100%, indicating a surebet.
	•	Kelly Criterion Bet Sizing: Calculates the optimal stake distribution for each outcome of an arbitrage bet. Uses a configurable fractional Kelly approach to balance aggressive growth with risk management. Ensures that the profit is the same regardless of which outcome wins.
	•	Streamlit Dashboard: Includes an interactive web dashboard for monitoring the bot. Displays current arbitrage opportunities, a running log of bets, and key performance metrics (like current bankroll and total profit). Features charts (with a clean, Yan Holtz–inspired aesthetic) such as a live bankroll growth curve, for visualizing progress. Users can adjust parameters (e.g., Kelly fraction, refresh rate) and even manually input odds to see calculated stakes.
	•	Modular Architecture: The project is organized into self-contained modules – Odds Fetcher, Arbitrage Calculator, Bet Sizer, Strategy Engine, etc. – making the code easy to maintain, test, and extend. Each component can be improved or replaced independently (for example, plugging in a new data source or adding support for a new sport) without breaking the whole system.
	•	CI/CD and Containerization: Equipped with a GitHub Actions workflow for running tests (and potentially scheduling the bot or updating data). A Docker setup is provided, allowing the entire application (bot + dashboard) to be run in a container for consistency across environments. This makes deployment to cloud or running on different machines straightforward.

Architecture

The bot’s architecture follows a clear pipeline from data collection to user interface. Below is a high-level diagram of the system:
