# AI Product Ads - Full Stack Application

A modern, enterprise-grade AI-powered product advertisement generator built with Spring Boot and React. This application allows users to create stunning product images and videos using artificial intelligence.

## 🚀 Tech Stack

### Backend
- **Java 17+** - Modern Java with latest features
- **Spring Boot 3+** - Enterprise-grade framework
- **Spring Security** - JWT-based authentication
- **Spring Data JPA** - Database abstraction layer
- **MySQL 8.0** - Reliable relational database
- **AWS S3** - Cloud storage for media files
- **OpenAI API** - AI image generation
- **Replicate API** - AI video generation
- **Swagger/OpenAPI** - API documentation
- **Lombok** - Reduces boilerplate code
- **Docker** - Containerization support

### Frontend
- **React 18** - Modern React with hooks
- **Vite** - Fast build tool and dev server
- **Tailwind CSS** - Utility-first CSS framework
- **Framer Motion** - Smooth animations
- **Axios** - HTTP client for API calls
- **React Router DOM** - Client-side routing
- **React Hot Toast** - Beautiful notifications
- **Lucide React** - Modern icon library

## 📁 Project Structure

```
ai-product-ads/
├── backend/                    # Spring Boot Backend
│   ├── src/main/java/com/aiproductads/
│   │   ├── AiProductAdsApplication.java
│   │   ├── config/             # Configuration classes
│   │   ├── controller/         # REST controllers
│   │   ├── model/             # JPA entities
│   │   ├── repository/        # Data repositories
│   │   ├── service/           # Business logic
│   │   ├── security/          # Security components
│   │   └── exception/         # Exception handling
│   ├── src/main/resources/
│   │   └── application.properties
│   ├── pom.xml
│   └── Dockerfile
│
├── frontend/                   # React Frontend
│   ├── public/
│   ├── src/
│   │   ├── components/        # Reusable components
│   │   ├── pages/             # Page components
│   │   ├── contexts/          # React contexts
│   │   ├── api/               # API services
│   │   └── utils/             # Utility functions
│   ├── package.json
│   └── Dockerfile
│
├── docker-compose.yml          # Docker orchestration
├── env.example                 # Environment variables template
└── README.md
```

## 🛠️ Features

### Core Features
- **User Authentication** - JWT-based secure authentication
- **AI Image Generation** - Create stunning product images using OpenAI
- **AI Video Generation** - Generate engaging product videos using Replicate
- **Avatar Integration** - Add AI avatars to product showcases
- **Media Management** - Upload and manage images/videos with AWS S3
- **Credit System** - Manage user credits for AI generation
- **Real-time Updates** - Live status updates for generation processes

### UI/UX Features
- **Modern Dashboard** - Beautiful glassmorphism design
- **Responsive Layout** - Works on all device sizes
- **Smooth Animations** - Framer Motion powered transitions
- **Dark Theme** - Professional dark color scheme
- **Interactive Components** - Hover effects and micro-interactions
- **Toast Notifications** - User-friendly feedback system

### Enterprise Features
- **Role-based Access** - Admin and user roles
- **API Documentation** - Swagger UI integration
- **Global Exception Handling** - Consistent error responses
- **Logging** - Comprehensive application logging
- **Docker Support** - Easy deployment and scaling
- **Database Migrations** - Automatic schema management

## 🚀 Quick Start

### Prerequisites
- Java 17+
- Node.js 18+
- MySQL 8.0+
- Docker (optional)

### 1. Clone the Repository
```bash
git clone <repository-url>
cd ai-product-ads
```

### 2. Environment Setup
```bash
# Copy environment template
cp env.example .env

# Edit .env with your configuration
nano .env
```

### 3. Database Setup
```bash
# Create MySQL database
mysql -u root -p
CREATE DATABASE ai_ads;
```

### 4. Backend Setup
```bash
cd backend

# Install dependencies and run
./mvnw clean install
./mvnw spring-boot:run

# Or with Docker
docker build -t ai-ads-backend .
docker run -p 8080:8080 ai-ads-backend
```

### 5. Frontend Setup
```bash
cd frontend

# Install dependencies
npm install

# Start development server
npm run dev

# Or with Docker
docker build -t ai-ads-frontend .
docker run -p 5173:5173 ai-ads-frontend
```

### 6. Docker Compose (Recommended)
```bash
# Start all services
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down
```

## 🔧 Configuration

### Backend Configuration
Edit `backend/src/main/resources/application.properties`:

```properties
# Database
spring.datasource.url=jdbc:mysql://localhost:3306/ai_ads
spring.datasource.username=root
spring.datasource.password=yourpassword

# JWT
jwt.secret=YourSuperSecretKey
jwt.expiration=3600000

# AWS S3
aws.s3.bucket-name=your-bucket-name
aws.access-key-id=YOUR_ACCESS_KEY
aws.secret-access-key=YOUR_SECRET_KEY

# OpenAI
openai.api-key=your-openai-key

# Replicate
replicate.api-token=your-replicate-token
```

### Frontend Configuration
Edit `frontend/src/api/authService.js`:

```javascript
const API_BASE_URL = 'http://localhost:8080/api'
```

## 📚 API Documentation

Once the backend is running, visit:
- **Swagger UI**: http://localhost:8080/swagger-ui.html
- **API Docs**: http://localhost:8080/v3/api-docs

### Key Endpoints

#### Authentication
- `POST /api/auth/signup` - User registration
- `POST /api/auth/signin` - User login
- `POST /api/auth/refresh` - Refresh JWT token

#### Products
- `POST /api/product/generate` - Generate AI product image
- `POST /api/product/generate-video/{id}` - Generate product video
- `GET /api/product/my-products` - Get user's products
- `GET /api/product/{id}` - Get specific product
- `DELETE /api/product/{id}` - Delete product

#### User Management
- `GET /api/user/profile` - Get user profile
- `PUT /api/user/profile` - Update user profile
- `GET /api/user/stats` - Get user statistics

#### Media Upload
- `POST /api/media/upload` - Upload file to S3
- `POST /api/media/upload-image` - Upload image
- `POST /api/media/upload-video` - Upload video

## 🎨 UI Components

### Dashboard
- **Stats Cards** - Display key metrics with animations
- **AI Tools Grid** - Showcase available AI tools
- **Recent Ads** - Display latest generated content
- **Quick Actions** - Fast access to common tasks

### Create Ad Page
- **File Upload** - Drag-and-drop image upload
- **Sample Products** - Pre-loaded product images
- **Description Input** - Rich text area for product details
- **Size Selection** - Multiple aspect ratio options
- **Avatar Selection** - AI avatar integration

### My Ads Page
- **Ad Grid** - Visual grid of all user ads
- **Status Indicators** - Real-time generation status
- **Action Buttons** - View, download, delete options
- **Video Generation** - One-click video creation

## 🔒 Security Features

- **JWT Authentication** - Secure token-based auth
- **Password Encryption** - BCrypt password hashing
- **CORS Configuration** - Cross-origin request handling
- **Input Validation** - Server-side validation
- **SQL Injection Protection** - JPA parameterized queries
- **XSS Protection** - Content Security Policy

## 🚀 Deployment

### Production Deployment

1. **Build Backend**
```bash
cd backend
./mvnw clean package -Pproduction
```

2. **Build Frontend**
```bash
cd frontend
npm run build
```

3. **Docker Production**
```bash
docker-compose -f docker-compose.prod.yml up -d
```

### Environment Variables for Production
```bash
# Database
SPRING_DATASOURCE_URL=jdbc:mysql://your-db-host:3306/ai_ads
SPRING_DATASOURCE_USERNAME=your-db-user
SPRING_DATASOURCE_PASSWORD=your-db-password

# JWT (Use strong secret in production)
JWT_SECRET=your-super-secure-jwt-secret-key

# AWS S3
AWS_S3_BUCKET_NAME=your-production-bucket
AWS_ACCESS_KEY_ID=your-production-access-key
AWS_SECRET_ACCESS_KEY=your-production-secret-key

# AI APIs
OPENAI_API_KEY=your-production-openai-key
REPLICATE_API_TOKEN=your-production-replicate-token
```

## 🧪 Testing

### Backend Tests
```bash
cd backend
./mvnw test
```

### Frontend Tests
```bash
cd frontend
npm test
```

### Integration Tests
```bash
docker-compose -f docker-compose.test.yml up --abort-on-container-exit
```

## 📊 Monitoring

### Health Checks
- **Backend Health**: http://localhost:8080/actuator/health
- **Metrics**: http://localhost:8080/actuator/metrics

### Logs
```bash
# View backend logs
docker-compose logs -f backend

# View frontend logs
docker-compose logs -f frontend

# View all logs
docker-compose logs -f
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Documentation**: Check this README and API docs
- **Issues**: Report bugs via GitHub Issues
- **Discussions**: Join GitHub Discussions for questions

## 🎯 Roadmap

- [ ] **Advanced AI Models** - Integration with more AI providers
- [ ] **Batch Processing** - Generate multiple ads at once
- [ ] **Template System** - Pre-designed ad templates
- [ ] **Analytics Dashboard** - Detailed performance metrics
- [ ] **Team Collaboration** - Multi-user workspaces
- [ ] **API Rate Limiting** - Advanced rate limiting
- [ ] **Webhook Support** - Real-time notifications
- [ ] **Mobile App** - React Native mobile application

---

**Built with ❤️ using Spring Boot, React, and AI**