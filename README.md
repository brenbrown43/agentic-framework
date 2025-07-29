# 🤖 JeweledTech Agentic Framework

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?logo=docker&logoColor=white)](https://www.docker.com/)

An open-source framework for building powerful multi-agent AI systems. Create autonomous agents that can research, write, analyze, and collaborate to solve complex tasks.

## 🚀 Quick Start

Get up and running in less than 5 minutes:

```bash
# Clone the repository
git clone https://github.com/jeweledtech/agentic-framework.git
cd agentic-framework

# Copy environment variables
cp .env.example .env

# Start the framework
docker-compose up

# Access the API
curl http://localhost:8000
```

Visit `http://localhost:8000/docs` for interactive API documentation.

## 🎯 Why JeweledTech Agentic Framework?

- **Multi-Agent Orchestration**: Create crews of specialized agents that work together
- **Extensible Architecture**: Easy to add custom agents and tools
- **Production-Ready Core**: Built on proven technologies (CrewAI, LangChain, FastAPI)
- **Local-First**: Runs entirely on your infrastructure with Ollama
- **Developer-Friendly**: Clear APIs, comprehensive documentation, and examples

## 📚 Core Concepts

### Agents
Autonomous AI entities with specific roles and capabilities:
```python
from agents.examples import ResearchAgent

agent = ResearchAgent()
result = agent.research_topic("quantum computing", depth="comprehensive")
```

### Crews
Multiple agents working together:
```python
# Research agent gathers information
# Writer agent creates content based on research
# Agents collaborate automatically
```

### Tools
Extend agent capabilities with custom tools:
- Web search
- Knowledge base queries
- File operations
- API integrations

### Knowledge Bases
Structured information repositories with RAG support for enhanced agent intelligence.

## 🛠️ Example Usage

### Research a Topic
```bash
curl -X POST http://localhost:8000/research \
  -H "Content-Type: application/json" \
  -d '{"topic": "AI in healthcare", "depth": "comprehensive"}'
```

### Generate Content
```bash
curl -X POST http://localhost:8000/write \
  -H "Content-Type: application/json" \
  -d '{"topic": "Future of remote work", "tone": "professional", "word_count": 800}'
```

### Multi-Agent Collaboration
```bash
curl -X POST http://localhost:8000/collaborate \
  -H "Content-Type: application/json" \
  -d '{"topic": "Blockchain technology", "output_type": "blog_post"}'
```

## 📖 Documentation

- [Getting Started Guide](docs/getting-started.md)
- [Agent Development Guide](knowledge_bases/examples/agent_development_guide.md)
- [API Reference](http://localhost:8000/docs)
- [Examples](agents/examples/)

## 🏗️ Architecture

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   FastAPI       │────▶│   Agent         │────▶│    Ollama       │
│   Server        │     │   Orchestrator  │     │    (LLM)        │
└─────────────────┘     └─────────────────┘     └─────────────────┘
         │                       │                        │
         ▼                       ▼                        ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   Custom        │     │   Knowledge     │     │    Tools &      │
│   Agents        │     │   Base          │     │    Extensions   │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

## 🔧 Creating Custom Agents

```python
from core.agent import BaseAgent, AgentConfig, AgentRole, AgentTools

class DataAnalystAgent(BaseAgent):
    def __init__(self):
        config = AgentConfig(
            id="data_analyst",
            role=AgentRole(
                name="Data Analyst",
                description="Analyzes data and provides insights",
                goal="Transform raw data into actionable insights",
                backstory="Expert in statistical analysis and data visualization"
            ),
            tools=AgentTools(tool_names=["data_query", "chart_generator"])
        )
        super().__init__(config)
    
    def analyze_data(self, dataset, analysis_type):
        # Your analysis logic here
        pass
```

## 🏢 Enterprise Features

This open-source framework provides the foundation. For production deployments, JeweledTech offers:

- **20+ Pre-built Specialized Agents**: Sales, Marketing, Engineering, Customer Success, and more
- **Advanced Orchestration**: Complex multi-agent workflows and decision trees
- **Production Infrastructure**: Kubernetes deployments, monitoring, and scaling
- **Integration Suite**: CRM, communication platforms, and enterprise tools
- **Professional Support**: Training, customization, and dedicated assistance

[Learn more about JeweledTech Enterprise →](https://jeweledtech.com/enterprise)

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Ways to Contribute
- 🐛 Report bugs and issues
- 💡 Suggest new features
- 📝 Improve documentation
- 🔧 Submit pull requests

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🌟 Community

- [GitHub Discussions](https://github.com/jeweledtech/agentic-framework/discussions)
- [Discord Community](https://discord.gg/jeweledtech)
- [Blog](https://jeweledtech.com/blog)

## 🙏 Acknowledgments

Built with amazing open-source projects:
- [CrewAI](https://github.com/joaomdmoura/crewAI)
- [LangChain](https://github.com/langchain-ai/langchain)
- [FastAPI](https://github.com/tiangolo/fastapi)
- [Ollama](https://github.com/ollama/ollama)

---

<p align="center">
  Made with ❤️ by <a href="https://jeweledtech.com">JeweledTech</a>
</p>

<p align="center">
  <a href="https://jeweledtech.com/enterprise">
    <img src="https://img.shields.io/badge/Need%20Enterprise%20Features%3F-Contact%20Us-brightgreen?style=for-the-badge" alt="Enterprise">
  </a>
</p>