# Vision Council Community Platform

A comprehensive FastAPI-based community management platform designed for volunteer organizations, featuring user onboarding, career connections, skill sharing, donations, safety profiles, and administrative tools.

## 🚀 Features

### Core Modules
- **User Management & Authentication** - Secure JWT-based authentication with OAuth integration
- **Onboarding System** - Streamlined user registration and verification process
- **Career Connect** - Professional networking and career development tools
- **Skill Share** - Platform for sharing and discovering skills within the community
- **Marshal System** - Community leadership and coordination tools
- **Honor Board** - Recognition and achievement tracking
- **Donation Management** - Integrated payment processing for community fundraising
- **Safety Profile** - Comprehensive safety and background verification
- **Certificate System** - Digital certification and credential management
- **Success Tracker** - Progress monitoring and milestone tracking
- **FAQ Management** - Dynamic frequently asked questions system
- **Media Management** - File upload and multimedia content handling

### Administrative Features
- **Admin Dashboard** - Comprehensive administrative control panel
- **User Management** - Advanced user administration and moderation
- **Content Moderation** - Tools for managing community content
- **Analytics & Reporting** - Insights into platform usage and engagement

## 🏗️ Architecture

### Tech Stack
- **Backend**: FastAPI (Python)
- **Database**: MongoDB with Motor (async driver)
- **Authentication**: JWT with OAuth2
- **File Storage**: Local file system with static file serving
- **Email**: SMTP integration for notifications
- **QR Codes**: Dynamic QR code generation for ID cards
- **Image Processing**: PIL for image manipulation

### Project Structure
```
app/
├── __init__.py              # FastAPI application setup
├── __main__.py             # Application entry point
├── auth/                   # Authentication & authorization
│   ├── deps.py            # Authentication dependencies
│   ├── jwt_handler.py     # JWT token management
│   └── routes.py          # Auth-related routes
├── database/              # Data layer
│   ├── crud/              # CRUD operations for all modules
│   ├── models/            # Database models
│   └── schemas/           # Pydantic schemas for validation
├── routes/                # API endpoints
│   ├── admin.py           # Administrative routes
│   ├── auth.py            # Authentication routes
│   ├── career.py          # Career connection endpoints
│   ├── donation.py        # Donation management
│   ├── marshal.py         # Marshal system
│   └── [other modules]    # Additional feature endpoints
└── utils/                 # Utility functions
    ├── auth_utils.py      # Authentication helpers
    ├── payment_gateway.py # Payment processing
    ├── qr_generator.py    # QR code generation
    └── [other utils]      # Additional utilities
```

## 🚦 Getting Started

### Prerequisites
- Python 3.8+
- MongoDB
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/vision-council-platform.git
   cd vision-council-platform
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

4. **Environment Configuration**
   Create a `.env` file in the root directory:
   ```env
   # Database
   MONGODB_URL=mongodb://localhost:27017/vision_council

   # JWT Configuration
   SECRET_KEY=your-secret-key-here
   ALGORITHM=HS256
   ACCESS_TOKEN_EXPIRE_MINUTES=30

   # Email Configuration
   SMTP_HOST=smtp.gmail.com
   SMTP_PORT=587
   SMTP_USERNAME=your-email@gmail.com
   SMTP_PASSWORD=your-app-password

   # OAuth (if using Google OAuth)
   GOOGLE_CLIENT_ID=your-google-client-id
   GOOGLE_CLIENT_SECRET=your-google-client-secret

   # File Upload
   UPLOAD_DIRECTORY=./uploads
   MAX_FILE_SIZE=10485760  # 10MB
   ```

5. **Setup MongoDB**
   - Install and start MongoDB
   - Create a database named `vision_council`

6. **Initialize directories**
   ```bash
   mkdir -p uploads/campaigns uploads/videos static/profile_images
   ```

### Running the Application

**Development Mode**
```bash
python -m app
```
The application will be available at `http://localhost:8000`

**Production Mode**
```bash
uvicorn app:app --host 0.0.0.0 --port 8000
```

### API Documentation
Once running, access the interactive API documentation:
- **Swagger UI**: `http://localhost:8000/docs`
- **ReDoc**: `http://localhost:8000/redoc`

## 📡 API Endpoints

### Authentication
- `POST /auth/register` - User registration
- `POST /auth/login` - User login
- `POST /auth/refresh` - Refresh access token
- `POST /auth/forgot-password` - Password reset request
- `POST /auth/reset-password` - Password reset confirmation

### User Management
- `GET /users/profile` - Get user profile
- `PUT /users/profile` - Update user profile
- `POST /users/upload-avatar` - Upload profile picture

### Career Connect
- `GET /career/opportunities` - List career opportunities
- `POST /career/opportunities` - Create new opportunity
- `POST /career/apply` - Apply for opportunity

### Skill Share
- `GET /skill-share/skills` - List available skills
- `POST /skill-share/offer` - Offer a skill
- `POST /skill-share/request` - Request a skill

### Donations
- `GET /donations/campaigns` - List donation campaigns
- `POST /donations/donate` - Process donation
- `GET /donations/history` - Donation history

### Marshal System
- `GET /marshal/assignments` - List marshal assignments
- `POST /marshal/report` - Submit marshal report
- `GET /marshal/qr-code` - Generate marshal QR code

## 🔧 Configuration

### Database Models
The platform uses MongoDB with the following key collections:
- `users` - User accounts and profiles
- `careers` - Career opportunities and applications
- `skills` - Skill sharing requests and offerings
- `donations` - Donation campaigns and transactions
- `marshals` - Marshal assignments and reports
- `certificates` - Digital certificates and credentials

### File Upload Configuration
- **Profile Images**: `static/profile_images/`
- **Campaign Media**: `uploads/campaigns/`
- **Video Content**: `uploads/videos/`
- **Maximum File Size**: 10MB (configurable)

### Security Features
- JWT-based authentication with refresh tokens
- Password hashing with bcrypt
- CORS middleware for cross-origin requests
- Session middleware for web sessions
- Input validation with Pydantic schemas

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow PEP 8 style guide
- Write comprehensive docstrings
- Include unit tests for new features
- Update API documentation for endpoint changes

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📧 Support

For support and questions:
- Create an issue on GitHub
- Contact the development team
- Check the [API documentation](http://localhost:8000/docs) for endpoint details

## 🙏 Acknowledgments

- FastAPI framework for the robust web API foundation
- MongoDB for flexible data storage
- The open-source community for various utility libraries

---

**Built with ❤️ for community empowerment**
