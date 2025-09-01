# Flowise AI Application

A low-code LLM application built with Flowise, Pinecode, Groq and Ollama, containerized with Docker for easy deployment and testing.

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- [Docker](https://www.docker.com/get-started/) (version 20.10 or higher)
- [Docker Compose](https://docs.docker.com/compose/install/) (usually included with Docker Desktop)
- [Git](https://git-scm.com/downloads)

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/Rafacv23/ai-course
cd ai-course/01_01_flowise
```

### 2. Environment Configuration

Copy the environment template and configure it:

```bash
cp .env.example .env
```

Edit the `.env` file with your preferred settings:

- Add your API keys (OpenAI, Anthropic, etc.) if needed
- Modify other settings as required

### 3. Start the Application

Run the application using Docker Compose:

```bash
# Start in detached mode
docker-compose up -d

# Or start with logs visible
docker-compose up
```

### 4. Access the Application

Once the containers are running, access Flowise at:

**URL:** http://localhost:3000

**Default Credentials:**

- Username: `admin`
- Password: `1234`

_(Change these in your `.env` file for security)_

### API Keys

To use external LLM services, add your API keys to the `.env` file:

```bash
OPENAI_API_KEY=your_openai_api_key_here
GROQ_API_KEY=your_groq_api_key_here
PINECODE_API_KEY=your_pinecode_api_key_here
FLOWISE_API_KEY=your_flowise_api_key_here
```

## 📖 Additional Resources

- [Flowise Documentation](https://docs.flowiseai.com/)
- [Groq Documentation](https://groq.dev/)
- [Pinecode Documentation](https://pinecode.com/)
- [Ollama Documentation](https://ollama.ai/)

**Happy Hacking! 🚀**
