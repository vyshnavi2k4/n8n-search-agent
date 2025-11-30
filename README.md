#🧠 n8n Google Search AI Agent 
    A fully automated AI Search Agent built using n8n, Gemini AI, and SerpAPI, capable of answering user messages, performing live Google searches, and returning intelligent,
    summarized results. 
🚀 Features:
    ✔ Receives messages from n8n Chat Trigger
    ✔ Uses Gemini 2.0 Flash for reasoning 
    ✔ Uses SerpAPI (Google Search) for real-time web search 
    ✔ Summarizes places, restaurants, locations, facts, etc. 
    ✔ Works like a mini ChatGPT + Google Search agent 
    ✔ Supports memory (Simple Memory node) 
    ✔ Fully customizable & extendable 
📂 Project Structure:
    n8n-search-agent/ 
    │ 
    ├── workflows/ 
    │ 
    └── search-agent-workflow.json # Entire n8n workflow (importable) 
    │ 
    └── README.md # Documentation 
🛠 Requirements:
    Before configuring the workflow inside n8n, you need: 
    1️⃣ n8n Cloud or Self-Hosted Instance https://app.n8n.cloud 
    2️⃣ Google Gemini API Key Free — no credit card required Create here: https://aistudio.google.com/apikey 
    3️⃣ SerpAPI Key Free trial available Create here: https://serpapi.com/manage-api-key 
    📥 Import Workflow into n8n 
  Download workflows/search-agent-workflow.json 
  Open your n8n instance 
  Go to Workflows → Import from File 
  Select the JSON file 
  Click Activate 
    ⚙️ Configure Credentials 
    🔹 Gemini API Credential 
        Go to Credentials 
        Add new credential 
        Choose Google AI Studio API 
        Paste your Gemini API Key 
    🔹 SerpAPI Credential 
        Go to Credentials 
        Choose SerpAPI 
        Paste your API key 
🧩 Workflow 
    Nodes Explained Node Purpose 
    Chat Trigger Receives incoming user messages 
    AI Agent Thinks, decides, routes queries to tools 
    Gemini Chat Model Generates responses & reasoning 
    Search Google Tool (HTTP Request Tool) Runs SerpAPI search 
    Simple Memory Stores conversation history 
🔍 How It Works 
    User sends a message (e.g., “Best places in Nellore”) 
    AI Agent analyzes it 
    If the question needs internet → AI automatically calls Search Google tool 
    SerpAPI fetches real Google results 
    Gemini summarizes into clean natural output 
    Response delivered back to chat 
🖼 Screenshots  
<img width="887" height="393" alt="image" src="https://github.com/user-attachments/assets/f99755e5-f44f-4472-bfe4-1d0837b79da3" />
<img width="506" height="702" alt="image" src="https://github.com/user-attachments/assets/8a7dca3d-0ad7-4e1e-95a2-50d054ae8db6" />
🧪 Example Prompts 
      Try: Best places in Vijayawada 
           Restaurants near me 
           Famous temples in Andhra Pradesh 
           Tell me latest news headlines 
📌 Troubleshooting 
    ❗Model says “I cannot browse the internet” 
       Fix: Use model: gemini-2.0-flash-lite (supports tool calling)
    ❗ Missing q parameter Ensure HTTP Request 
      Tool has: q = {{ $json.chatInput }} engine = google api_key = YOUR_KEY 
    ❗ Tool not running Ensure AI Agent → Tools → Search Google is connected.
❤️ Author 
Created by Vyshnavi 
Automated Search Agent using n8n, Gemini, and SerpAPI.
