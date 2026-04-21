Multi-Agent LLM Framework for Software Engineering Tasks
📌 Overview

This project implements a Multi-Agent Large Language Model (LLM) framework designed to solve software engineering tasks through collaborative reasoning and iterative refinement.

Inspired by SWE-bench-style problem solving, the system decomposes complex tasks into structured steps using multiple specialized agents. The framework simulates real-world software development workflows such as planning, coding, reviewing, and iterative debugging.

🧠 System Architecture

The system consists of four main agents:

🔹 Planner Agent
Interprets the problem description
Breaks it into structured subtasks
🔹 Code Agent
Generates or modifies code based on the plan
Focuses purely on implementation
🔹 Reviewer Agent
Evaluates generated code
Suggests improvements and identifies issues
🔹 Orchestrator
Controls the workflow between agents
Maintains state and manages iteration cycles
⚙️ Requirements
Python 3.8 or higher
Jupyter Notebook
Install Dependencies
pip install openai tqdm

📂 Project Structure
.
├── Code.ipynb                # Main implementation notebook
├── multi_agent_results.json  # Output results
├── dataset/                  # Input tasks (optional)
└── README.md                 # Documentation

🚀 How to Execute the Code
Step 1: Launch Notebook
jupyter notebook Code.ipynb

Step 2: Set API Key

Inside the notebook, configure your API key:

import os
os.environ["OPENAI_API_KEY"] = "your_api_key_here"

Step 3: Run All Cells

Execute all cells sequentially:

Cell → Run All

Step 4: Execution Flow

For each task, the system performs:

Planning Phase
Problem → structured subtasks
Code Generation Phase
Plan → generated code
Review Phase
Code → feedback and improvements
Iteration Loop
Repeats until:
Solution is correct, OR
Maximum iterations reached
Step 5: Output

Results are stored in:

multi_agent_results.json

Example Output Format
{
  "success": false,
  "iterations": 3,
  "history": [
    {
      "plan": "...",
      "code": "...",
      "review": "..."
    }
  ]
}

📊 Evaluation Metrics
Success Rate
Percentage of correctly solved tasks
Average Iterations
Number of refinement cycles per task
Reasoning Trace
Logs of agent interactions (plan → code → review)
⚠️ Known Limitations
Generated solutions may be syntactically correct but functionally incorrect
Reviewer validation is text-based (no execution)
Iterative feedback may not always lead to convergence
Some outputs may contain placeholder responses (e.g., “LLM RESPONSE FOR”)
✅ Future Improvements
Integrate execution-based validation with test cases
Improve prompt engineering for each agent
Enhance reviewer feedback quality
Add support for multi-file and real-world repositories
📚 Conclusion

This project demonstrates that:

Multi-agent collaboration improves structured reasoning
Iterative refinement enhances solution quality
However, execution-based validation is critical for real correctness

The framework highlights both the potential and limitations of agent-based LLM systems in software engineering tasks.
