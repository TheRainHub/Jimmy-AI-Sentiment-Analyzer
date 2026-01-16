# Jimmy-AI-Sentiment-Analyzer

A financial intelligence system that monitors real-time news streams to detect market sentiment (Bullish 🚀 vs. Bearish 📉) before it reflects in stock prices. Jimmy combines the concurrency and stability of Java with the NLP capabilities of Python through a polyglot microservices architecture.

## The Muscle: Data Ingestion Service

**Technology**: Java 17, Spring Boot, ROME, CompletableFuture

The backbone of the system, handling high-throughput data collection with:

- **Multithreading**: Uses CompletableFuture to scrape multiple RSS feeds (CoinDesk, Yahoo Finance, TechCrunch) in parallel without blocking the main thread
- **Resilience**: Implements scheduled tasks and error handling to ensure continuous uptime

## The Brain: NLP Analysis Service 🧠

**Technology**: Python, FastAPI, VADER Sentiment, NLTK

The intelligence layer that processes and analyzes financial content:

- **NLP**: Utilizes VADER (Valence Aware Dictionary and sEntiment Reasoner) specifically tuned for social media and financial contexts
- **Performance**: Exposes a lightweight REST API optimized for fast inference times

## Key Features

- **Real-Time Monitoring**: Scans financial news sources every 10 seconds
- **Semantic Analysis**: Detects nuance (e.g., distinguishing between "Market crash" 🔴 and "Buying the dip" 🟢)
- **Microservices Orchestration**: Fully Dockerized environment
- **Event-Driven Communication**: HTTP REST communication between the Collector and the Analyzer