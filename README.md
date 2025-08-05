🚀 # MCP Examples: Beginner-Friendly Model Context Protocol Applications


🎯 Overview
This repository showcases three practical MCP implementations that demonstrate how to integrate AI agents with real-world systems:

📧 Gmail Integration - Email management with SMTP/IMAP
📁 File System Manager - Desktop file operations
🌐 Network Ping Tool - Website reachability testing

Each example is designed for beginners while maintaining professional code standards and architectural best practices.

🔧 Examples

1. 📧 Gmail MCP Server
   
Files: server.js, ui.py
A full-featured email client built with MCP architecture:

Send Emails: SMTP integration with Gmail
Read Inbox: IMAP-based email retrieval
Web Interface: Gradio-powered UI
Security: OAuth 2.0 and App Password support

Key Features:
javascript// Email sending with professional error handling
app.post('/send', async (req, res) => {
    const { to, subject, message } = req.body;
    const info = await transporter.sendMail({
        from: process.env.GMAIL_USER,
        to, subject, message
    });
});

2. 📁 File System MCP

Files: file_app_ui.py, file_appy.py
Desktop file management through AI commands:

File Creation: Dynamic file generation
Content Writing: Text manipulation capabilities
Directory Navigation: Path-based operations
Cross-Platform: Windows/macOS/Linux compatible

Usage Example:
pythonagent = Agent(
    instructions="You are a file system manager with MCP filesystem tools.",
    llm="ollama/llama3.2",
    tools=MCP("npx -y @modelcontextprotocol/server-filesystem C:/Users/slayer/Desktop/mcp")
)

3. 🌐 Ping MCP Tool

Files: ping_app_ui.py, index.js
Network connectivity testing with AI integration:

Website Reachability: ICMP ping implementation
Response Analysis: Latency and packet loss metrics
Cross-Platform: Windows/Unix ping commands
Real-time Results: Live status monitoring

⚡ Quick Start

bash# Clone the repository
git clone https://github.com/MuratKomurcu1/Entry-level-MCP-examples.git
cd Entry-level-MCP-examples

# Install dependencies
npm install
pip install -r requirements.txt

# Run Gmail example
node server.js &
python ui.py

# Run File System example  
python file_app_ui.py

# Run Ping example
python ping_app_ui.py
📋 Prerequisites
Software Requirements

Python 3.8+ with pip
Node.js 18+ with npm
Ollama with llama3.2 model

System Dependencies
bash# Install Ollama
curl -fsSL https://ollama.ai/install.sh | sh
ollama pull llama3.2

# Install Python packages
pip install praisonaiagents gradio requests

# Install Node.js packages
npm install express cors nodemailer imap mailparser dotenv
🛠 Installation
1. Environment Setup
Create .env file for Gmail integration:
envGMAIL_USER=your_email@gmail.com
GMAIL_APP_PASSWORD=your_16_digit_app_password
2. Gmail App Password Setup

Enable 2-Factor Authentication in Google Account
Generate App Password: Google Account Security
Select "Mail" application type
Copy the 16-character password to .env

3. Directory Permissions
Ensure proper file system permissions:
bash# Windows
icacls "C:\Users\slayer\Desktop" /grant:r %USERNAME%:F

# macOS/Linux  
chmod 755 ~/Desktop
🚀 Usage
Gmail Integration
bash# Start backend server
node server.js

# Launch web interface
python ui.py

# Access at http://localhost:7860
File System Manager
bash# Interactive mode
python file_app_ui.py

# Direct command execution
python file_appy.py
Network Ping Tool
bash# Web interface
python ping_app_ui.py

# Direct ping test
node index.js
🏗 Architecture
MCP Design Pattern
mermaidgraph TB
    A[AI Agent] --> B[MCP Client]
    B --> C[MCP Server]
    C --> D[External System]
    
    A1[Ollama LLM] --> B1[PraisonAI Agent]
    B1 --> C1[MCP Tools]
    C1 --> D1[Gmail/Files/Network]
Component Interaction

Agent Layer: AI decision making and natural language processing
MCP Layer: Protocol standardization and tool orchestration
System Layer: Direct integration with external services
UI Layer: User interaction and result presentation

Code Standards

Python: Follow PEP 8, use type hints
JavaScript: ES6+, async/await patterns
Documentation: Comprehensive docstrings and comments
Testing: Unit tests for all new features

📈 Roadmap

 v2.0: Docker containerization
 v2.1: OAuth 2.0 implementation for Gmail
 v2.2: Advanced file operations (copy, move, delete)
 v2.3: Network diagnostics (traceroute, DNS lookup)
 v3.0: Multi-agent orchestration
 v3.1: Web dashboard with analytics

🐛 Troubleshooting
Common Issues
Gmail Authentication Failed
bash# Verify credentials
echo $GMAIL_USER
# Regenerate App Password if needed
File Permission Denied
bash# Check directory permissions
ls -la ~/Desktop
# Adjust permissions if necessary
Ollama Model Not Found
bash# Pull required model
ollama pull llama3.2
# Verify installation
ollama list
📚 Resources

Model Context Protocol Documentation
PraisonAI Agents Guide
Gradio Documentation
Gmail API Reference

📄 License
This project is licensed under the MIT License 

⭐ If this repository helped you, please give it a star!
