# Blog Writing Agent

A powerful, AI-driven Blog Writing Agent built with **Streamlit**, **LangGraph**, and **LangChain**. This application automates the process of researching, planning, and drafting high-quality, long-form blog posts. 

By leveraging advanced LLMs (like Google's Gemini) and web search integration (Tavily), the agent intelligently decides whether to perform live web research, breaks the topic into modular sections, processes each section concurrently, and seamlessly merges them into a polished markdown document ready for publication.

---

## Features

- **Intelligent Routing:** Automatically determines whether a topic requires live web research (open book), hybrid research, or if it can be answered using internal knowledge (closed book).
- **Automated Web Research:** Uses the Tavily API to gather up-to-date, high-signal information and evidence for volatile or deeply technical topics.
- **Structured Planning:** Dynamically generates a comprehensive blog outline with specific tasks, word counts, and goals for each section.
- **Concurrent Execution:** Utilizes LangGraph to process and draft individual blog sections in parallel, improving generation speed.
- **Image Integration:** Dynamically plans and integrates contextual images into the final markdown document.
- **Interactive UI:** A clean, easy-to-use Streamlit interface that provides real-time progress updates, node execution logs, and live markdown rendering.
- **Export & Download:** Download the final blog as a single Markdown (`.md`) file, or download a bundled ZIP containing the markdown and all associated local images.
- **History Management:** Seamlessly load, view, and manage past generated blogs directly from the sidebar.

---

## 🛠️ Tech Stack

- **Frontend:** [Streamlit](https://streamlit.io/)
- **Agent Orchestration:** [LangGraph](https://python.langchain.com/docs/langgraph)
- **LLM Framework:** [LangChain](https://python.langchain.com/)
- **Models:** Google Gemini (via `langchain-google-genai`), Groq
- **Web Search:** [Tavily Search API](https://tavily.com/)
- **Data Validation:** Pydantic

---

## ⚙️ Setup and Installation

### 1. Clone the repository
```bash
git clone https://github.com/your-username/blog-writing-agent.git
cd blog-writing-agent
```

### 2. Create a virtual environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### 3. Install dependencies
Ensure you have the required packages installed. *(If a `requirements.txt` is missing, you can install the core packages manually):*
```bash
pip install streamlit langchain langgraph langchain-google-genai pydantic python-dotenv pandas
```

### 4. Configure Environment Variables
Create a `.env` file in the root of the project and add your API keys:

```env
GOOGLE_API_KEY=your_google_gemini_api_key
TAVILY_API_KEY=your_tavily_search_api_key
GEMINI_MODEL=gemini-3.5-flash
# Optional keys if you extend the models
GROQ_API_KEY=your_groq_api_key
GROQ_MODEL=openai/gpt-oss-120b
```

---

## 🎯 Usage

To start the application, run the Streamlit frontend script:

```bash
python -m streamlit run bwa_frontend.py
```

1. **Enter a Topic:** In the sidebar, type the topic you want the agent to write about.
2. **Set As-of Date:** (Optional) Set a specific date for contextual relevance.
3. **Generate:** Click the **🚀 Generate Blog** button.
4. **Monitor Progress:** Watch the agent's progress in real-time across the *Plan*, *Evidence*, *Preview*, and *Logs* tabs.
5. **Download:** Once completed, download your Markdown file or ZIP bundle directly from the UI.

---

## 📂 Project Structure

- `bwa_frontend.py` - The main Streamlit application script containing the UI, Markdown renderer, and zip bundling logic.
- `bwa_backend.py` - The LangGraph orchestration layer containing the state machine, prompts, routing logic, worker nodes, and LLM integrations.
- `.env` - Environment variables configuration (ignored by Git).
- `.gitignore` - Standard gitignore to keep the repository clean from cache, local environments, and temporary generated outputs.

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! 
Feel free to check [issues page](https://github.com/your-username/blog-writing-agent/issues) if you want to contribute.

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.
