# Flowise AI Application

A low-code LLM application built with Flowise, containerized with Docker for easy deployment and testing.

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- [Docker](https://www.docker.com/get-started/) (version 20.10 or higher)
- [Docker Compose](https://docs.docker.com/compose/install/) (usually included with Docker Desktop)
- [Git](https://git-scm.com/downloads)

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd <repository-name>
```

### 2. Environment Configuration

Copy the environment template and configure it:

```bash
cp .env.example .env
```

Edit the `.env` file with your preferred settings:
- Change default username/password for security
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

*(Change these in your `.env` file for security)*

## 🛠️ Available Commands

```bash
# Start the application
docker-compose up -d

# Stop the application
docker-compose down

# View logs
docker-compose logs -f flowise

# Restart the application
docker-compose restart

# Pull latest updates
docker-compose pull
docker-compose up -d

# Remove everything (including volumes)
docker-compose down -v
```

## 📁 Project Structure

```
.
├── docker-compose.yml          # Docker Compose configuration
├── .env.example               # Environment variables template
├── .env                       # Your environment configuration (not in git)
├── .gitignore                 # Git ignore rules
├── README.md                  # This file
├── flowise-data/              # Persistent data directory
│   ├── uploads/               # File uploads
│   └── backups/               # Workflow backups
└── docs/                      # Additional documentation
    └── workflows/             # Example workflow configurations
```

## 🔧 Configuration

### Environment Variables

The application can be configured through environment variables in the `.env` file:

| Variable | Description | Default |
|----------|-------------|---------||
| `FLOWISE_USERNAME` | Admin username | `admin` |
| `FLOWISE_PASSWORD` | Admin password | `1234` |
| `FLOWISE_SECRETKEY_OVERWRITE` | Secret key for encryption | `mySecretKey123` |
| `LOG_LEVEL` | Logging level | `info` |
| `DATABASE_TYPE` | Database type (sqlite/postgres/mysql) | `sqlite` |
| `OPENAI_API_KEY` | OpenAI API key | _(optional)_ |

### API Keys

To use external LLM services, add your API keys to the `.env` file:

```bash
OPENAI_API_KEY=your_openai_api_key_here
ANTHROPIC_API_KEY=your_anthropic_api_key_here
GOOGLE_API_KEY=your_google_api_key_here
```

## 📊 Data Persistence

The application uses Docker volumes to persist data:

- **flowise_data**: Main application data (database, configurations)
- **./flowise-data**: Local directory for uploads and backups

## 🐛 Troubleshooting

### Port Already in Use
If port 3000 is already in use, modify the `docker-compose.yml` file:

```yaml
ports:
  - "3001:3000"  # Use port 3001 instead
```

### Container Won't Start
Check the logs:

```bash
docker-compose logs flowise
```

### Reset Everything
To start fresh:

```bash
docker-compose down -v
docker-compose up -d
```

## 🔒 Security Notes

- **Change default credentials** in production
- **Keep API keys secure** and never commit them to version control
- **Use HTTPS** in production environments
- **Regularly update** the Docker image for security patches

## 📖 Additional Resources

- [Flowise Documentation](https://docs.flowiseai.com/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
- [LangChain Documentation](https://python.langchain.com/)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 💬 Support

If you encounter any issues:

1. Check the troubleshooting section above
2. Review the application logs: `docker-compose logs flowise`
3. Create an issue in this repository
4. Contact the course instructor

---

**Happy Building! 🚀**