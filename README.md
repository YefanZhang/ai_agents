# AI Agents - Intensive Agent Course

A collection of AI agent examples using Google's Agent Development Kit (ADK). This repository contains practical examples demonstrating different agent architectures and patterns.

## Prerequisites

- Python 3.12 or higher
- [UV](https://github.com/astral-sh/uv) package manager
- Google API Key with access to Gemini models

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/YefanZhang/ai_agents.git
cd ai_agents
```

### 2. Install UV (if not already installed)

```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### 3. Set Up the Environment

```bash
# Create and activate virtual environment
uv venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
uv sync
```

### 4. Configure API Keys

Create a `.env` file in each agent directory (or set as environment variable):

```bash
# Option 1: Create .env files
echo 'GOOGLE_API_KEY="your-google-api-key-here"' > day1/simple_agent/.env
echo 'GOOGLE_API_KEY="your-google-api-key-here"' > day1/multi_agent/.env
echo 'GOOGLE_API_KEY="your-google-api-key-here"' > day1/parallel_agents/.env
echo 'GOOGLE_API_KEY="your-google-api-key-here"' > day1/assembly_line_agent/.env

# Option 2: Set as environment variable (recommended)
export GOOGLE_API_KEY="your-google-api-key-here"
```

**To make the environment variable permanent (macOS/Linux):**

Add to your `~/.zshrc` or `~/.bashrc`:
```bash
export GOOGLE_API_KEY="your-google-api-key-here"
```

Then reload:
```bash
source ~/.zshrc  # or source ~/.bashrc
```

### 5. Run the Agents

There are two ways to run ADK agents:

**Option A: Web UI (Recommended)**

Run the ADK web interface from the repository root:

```bash
# From the repository root directory
adk web --port 8080
```

Then open your browser to `http://localhost:8080` and select the agent you want to interact with.

**Option B: Command Line**

Run a specific agent directly:

```bash
# From the repository root directory
adk run day1/simple_agent

# Or specify a different agent
adk run day1/multi_agent
adk run day1/parallel_agents
adk run day1/assembly_line_agent
```

## Project Structure

```
.
├── day1/
│   ├── simple_agent/          # Basic agent example
│   │   ├── agent.py
│   │   ├── .env
│   │   └── __init__.py
│   ├── multi_agent/           # Multi-agent system example
│   │   ├── agent.py
│   │   ├── .env
│   │   └── __init__.py
│   ├── parallel_agents/       # Parallel agent execution
│   │   ├── agent.py
│   │   ├── .env
│   │   └── __init__.py
│   └── assembly_line_agent/   # Sequential agent pipeline
│       ├── agent.py
│       ├── .env
│       └── __init__.py
├── pyproject.toml             # Project dependencies
├── uv.lock                    # Dependency lock file
└── README.md
```

## Agent Examples

### Simple Agent
A basic agent that demonstrates core ADK functionality with Google Search integration.

**Features:**
- Uses Gemini 2.5 Flash model
- Integrated Google Search tool
- HTTP retry configuration

**Run:**
```bash
# From repository root
adk run day1/simple_agent
```

### Multi-Agent System
Demonstrates coordination between multiple specialized agents.

**Run:**
```bash
# From repository root
adk run day1/multi_agent
```

### Parallel Agents
Shows how to run multiple agents concurrently for improved performance.

**Run:**
```bash
# From repository root
adk run day1/parallel_agents
```

### Assembly Line Agent
Implements a sequential pipeline where agents process information in stages.

**Run:**
```bash
# From repository root
adk run day1/assembly_line_agent
```

## Dependencies

Main dependencies (managed in `pyproject.toml`):
- `google-adk>=1.18.0` - Google Agent Development Kit
- `google-genai` - Google Generative AI SDK
- Additional dependencies auto-installed via UV

## Development

### Adding New Dependencies

```bash
# Add a new package
uv add package-name

# Add a development dependency
uv add --dev package-name
```

### Updating Dependencies

```bash
# Update all dependencies
uv sync --upgrade
```

## Troubleshooting

### Import Errors in IDE

If you see import errors for `google.adk` or `google.genai`:

1. Ensure the virtual environment is activated
2. In VSCode: `Cmd+Shift+P` → "Python: Select Interpreter" → Select `.venv/bin/python`
3. Reload the IDE window

### API Key Issues

- Verify your Google API key is valid
- Ensure the key has access to Gemini models
- Check that the environment variable is properly set: `echo $GOOGLE_API_KEY`

### UV Command Not Found

Ensure UV is in your PATH:
```bash
# Add to ~/.zshrc or ~/.bashrc
export PATH="$HOME/.local/bin:$PATH"
```

## Getting a Google API Key

1. Visit [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Create a new API key or use an existing one
3. Ensure billing is enabled if required for your usage tier

## Resources

- [Google ADK Documentation](https://ai.google.dev/adk)
- [UV Package Manager](https://github.com/astral-sh/uv)
- [Gemini API Documentation](https://ai.google.dev/docs)

## License

This project is for educational purposes.

## Contributing

Feel free to submit issues or pull requests for improvements.
