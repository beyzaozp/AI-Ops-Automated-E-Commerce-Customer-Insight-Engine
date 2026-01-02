# AI-Powered Customer Sentiment & Response Engine

An automated pipeline that processes e-commerce customer reviews using **Google Gemini 2.5 Flash**, categorizes feedback, and generates empathetic responses in real-time.

## 🚀 The Architecture
- **Trigger:** Google Sheets (New review entry)
- **Processor:** Google Gemini 2.5 Flash (LLM)
- **Data Handler:** Custom JSON Parser & Mapping logic
- **Output:** Categorized insights and AI-generated drafts back to Google Sheets

## 🛠️ Tech Stack
- **AI Model:** Gemini 2.5 Flash-Lite (Low latency, high reasoning)
- **Automation:** Make.com
- **Database/UI:** Google Sheets API

## 📈 Scalability & Metrics
- Handles up to 5 RPM (Free Tier optimized).
- Automated categorization for: Sizing, Quality, Logistics, Stock.
- Sentiment analysis accuracy: ~95% based on context engineering.

How It Works?
This automation functions as a serverless pipeline that bridges customer feedback with actionable intelligence. The flow is as follows:

Data Ingestion (The Trigger): The system continuously monitors a Google Sheet via a polling mechanism. As soon as a new customer review is detected, the workflow is triggered.

Contextual Analysis (The Brain): The raw text is dispatched to the Gemini 2.5 Flash model with a specific "System Instruction." This prompt engineering ensures the AI acts as an Operations Manager, performing three tasks simultaneously:

Categorization: Identifying the core intent (Sizing, Quality, Logistics, etc.).

Sentiment Analysis: Detecting the emotional tone (Positive/Negative).

Response Generation: Drafting a professional, empathetic reply in Turkish.

Data Structuring: To maintain a clean database, the AI is forced to return a JSON object. This prevents unstructured text from breaking the pipeline.

Schema Transformation: The raw JSON string is parsed into individual variables (Category, Sentiment, Draft_Response) using a dedicated JSON Parser.

Record Update (The Action): The parsed variables are mapped back to the exact row in the Google Sheet where the review originated, completing the cycle without human intervention.
