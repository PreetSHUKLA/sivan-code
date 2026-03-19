Sivan AI: The Multi-Agent Orchestration CLI

Sivan AI is a professional, terminal-based coding assistant designed to bridge the gap between AI prototypes and production-grade software. Unlike standard AI wrappers, Sivan utilizes a sophisticated Planner-Worker-Reviewer architecture to ensure the code you receive is functional, secure, and optimized for performance.

🚀 Key Features

Multi-Agent Orchestration: Every request is processed through a tri-agent loop:

Planner: Architecting the logic and structure.

Worker: Implementing the codebase.

Reviewer: Rigorous SRE-grade auditing before delivery.

Context-Aware Intelligence: Dynamically scales strictness—idiomatic for simple tasks, enterprise-grade for complex systems.

SRE-Grade Reviewing: Automated audits for memory leaks, resource exhaustion, race conditions, and unhandled edge cases.

Automatic Editor Integration: Seamlessly saves output to sivan_output.py and opens your default system editor (VS Code, Vim, etc.) upon approval.

Secure Remote Brain: API keys and heavy LLM computations are handled on a secure FastAPI server, keeping your local environment clean and lightweight.

🛠️ Installation

Sivan is distributed via PyPI. You can install it globally using pip:

pip install sivan-cli

[!IMPORTANT] Upgrading: If you are experiencing timeouts, ensure you are on version v1.0.2 or higher: pip install --upgrade sivan-cli

🔑 Getting Started

Authentication
To begin generating code, link your CLI to the Sivan Brain using your unique beta access code:

sivan auth YOUR_BETA_CODE_HERE

This securely stores your session in a hidden .sivan_config file in your home directory.

Basic Usage
Generate scripts instantly with a natural language prompt:

sivan generate "Write a Python script to scrape news headlines from Reuters"

Engineering Complex Systems
Sivan is built for architectural complexity. Use high-level prompts for systems that require robust logic:

sivan generate "Build an async ETL pipeline that fetches data from 5 APIs, implements retries with exponential backoff/jitter, and streams results into a SQLite DB."

🏗️ Technical Architecture

Sivan operates on a Split-Plane Architecture to ensure high performance without taxing local resources:

The Client (CLI): A lightweight Python tool responsible for user input, local file I/O, and triggering the local editor.

The Brain (API): A high-performance FastAPI server (hosted on Render) that orchestrates high-level LLMs (GPT-4o, Claude 3.5) to execute the Planner-Worker-Reviewer logic.

📖 Troubleshooting

The "Timeout" Fix

Because Sivan's agents (Planner, Worker, and Reviewer) may "debate" the best implementation, complex tasks can take several minutes.

Connection Window: v1.0.2+ extends the connection window to 10 minutes.

Server Cold Start: On the free tier, the API may take ~60 seconds to wake up. If the initial command fails, wait one minute and retry, or visit the API documentation to wake the server manually.

📄 License

Distributed under the MIT License. See LICENSE for more information.

🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated.

Fork the Project

Create your Feature Branch (git checkout -b feature/AmazingFeature)

Commit your Changes (git commit -m 'Add some AmazingFeature')

Push to the Branch (git push origin feature/AmazingFeature)

Open a Pull Request

Developed by Preet Shukla — Building the future of autonomous coding agents.
