# VerifyIt Multiplayer

A real-time multiplayer web game built with Flask, SocketIO, and PostgreSQL.

## Overview

VerifyIt is an interactive multiplayer verification game where players can compete in real-time challenges. The application features real-time communication, user authentication, and a dynamic gaming experience.

## Tech Stack

- **Backend**: Flask 2.2.2
- **Real-time Communication**: Flask-SocketIO 5.3.6
- **Database**: PostgreSQL with SQLAlchemy 2.0.31
- **Authentication**: Flask-Login 0.6.3
- **Forms**: Flask-WTF 1.2.1
- **Deployment**: Heroku (Procfile included)

## Features

- 🎮 Real-time multiplayer gameplay
- 👥 User authentication and session management
- 💾 PostgreSQL database integration
- 🔄 WebSocket-based real-time updates
- 📱 Responsive web interface
- 🚀 Production-ready deployment configuration

## Project Structure

```
Flask/
├── main.py                 # Application entry point
├── game/                   # Main game module
│   ├── __init__.py        # Flask app initialization
│   ├── models.py          # Database models
│   ├── routes.py          # Main application routes
│   ├── forms.py           # WTForms definitions
│   ├── dbModel.py         # Database model utilities
│   ├── static/            # Static assets (CSS, JS, images)
│   └── templates/         # Jinja2 templates
├── requirements.txt        # Python dependencies
├── Procfile              # Heroku deployment configuration
└── runtime.txt           # Python runtime specification
```

## Installation

### Prerequisites

- Python 3.7+
- PostgreSQL database
- Git

### Local Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/krishaygarg/VerifyIt-multiplayer.git
   cd VerifyIt-multiplayer
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up the database**
   - Create a PostgreSQL database
   - Update the database URI in `game/__init__.py`
   - Run database migrations (if applicable)

5. **Configure environment variables**
   - Set the `SECRET_KEY` in `game/__init__.py`
   - Update database connection string

6. **Run the application**
   ```bash
   python main.py
   ```

The application will be available at `http://localhost:5000`.

## Deployment

### Heroku Deployment

1. **Create a Heroku app**
   ```bash
   heroku create your-app-name
   ```

2. **Set environment variables**
   ```bash
   heroku config:set SECRET_KEY=your-secret-key
   heroku config:set DATABASE_URL=your-postgres-url
   ```

3. **Deploy**
   ```bash
   git push heroku master
   ```

## Database Configuration

The application uses PostgreSQL as the primary database. The connection is configured in `game/__init__.py`:

```python
app.config['SQLALCHEMY_DATABASE_URI'] = 'postgresql://username:password@host:port/database'
```

For local development, you can use SQLite by uncommenting the SQLite URI and commenting out the PostgreSQL URI.

## API Endpoints

The application exposes several WebSocket events for real-time communication:

- **Connection**: Client connects to the game server
- **Game Events**: Real-time game state updates
- **User Actions**: Player interactions and moves

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions, please open an issue on the GitHub repository.

## Acknowledgments

- Built with Flask and Flask-SocketIO
- Database powered by PostgreSQL
- Real-time features using WebSockets
