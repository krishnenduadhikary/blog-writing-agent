# Blog Writing Agent

## 📌 What is this?
Blog Writing Agent is an AI-powered system built with LangChain + NVIDIA APIs that can:
- **Research** topics automatically using structured queries.
- **Generate** well-organized blogs with evidence and visuals.
- **Review & Rewrite** blogs with specific user feedback for iterative improvement.
- **Handle rate limits** by switching between multiple models (Nemotron, Gemma, DeepSeek, MiniMax).
- **Provide Markdown previews** and logs for transparency.

This project demonstrates how AI can assist in academic research, blogging, and content creation.

---

## 🚀 How to Use
1. **Clone the repository:**
   ```bash
   git clone https://github.com/krishnenduadhikary/blog-writing-agent.git
   cd blog-writing-agent
   ```

2. **Set up your environment:**
   Create a `.env` file with your API keys:
   ```env
   NVIDIA_API_KEY=your_key
   GOOGLE_API_KEY=your_key
   TAVILY_API_KEY=your_key
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the app:**
   ```bash
   streamlit run bwa_frontend.py
   ```

## 🧠 Architecture
The system uses **LangGraph** to coordinate a multi-node workflow:
- **Router:** Decides if web research is needed.
- **Research:** Fetches evidence via Tavily.
- **Orchestrator:** Plans the blog outline.
- **Worker (Fan-out):** Writes each section in parallel.
- **Reducer (Sub-graph):** Merges content, plans images, and generates them using Gemini.
- **Rewriter:** Processes user feedback to refine the final output.
