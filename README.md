# MicroBlog 📝

A Flask-based microblogging application with user authentication, blog management, and MongoDB integration. This project provides a complete blogging platform where users can create accounts, manage blogs, and publish posts.

##  Features

- **User Authentication**: Secure registration and login system using Flask-Login and bcrypt password hashing
- **Blog Management**: Create, view, and delete personal blogs
- **Post Creation**: Write and publish blog posts with timestamps
- **User Profiles**: Personal user profiles with blog and post statistics
- **Quick Posts**: Fast post creation directly from the home page
- **Responsive Design**: Clean, user-friendly interface
- **Database Integration**: MongoDB backend for data persistence

## 🛠️ Tech Stack

- **Backend**: Python 3.9, Flask 2.0.1
- **Database**: MongoDB with PyMongo 3.12.0
- **Authentication**: Flask-Login 0.5.0, Flask-Bcrypt 0.7.1
- **Frontend**: Jinja2 templates, HTML/CSS
- **Deployment**: Gunicorn WSGI server ready
- **Environment**: Python-dotenv for configuration

## 📁 Project Structure

```
MicroBlog/
├── main.py              # Flask application factory and routes
├── user.py              # User model and authentication logic
├── blog.py              # Blog model and operations
├── entry.py             # Blog post/entry model
├── db.py                # Database connection and operations wrapper
├── requirements.txt     # Python dependencies
├── Pipfile             # Pipenv configuration
├── Procfile            # Heroku deployment configuration
├── runtime.txt         # Python runtime specification
├── run.sh              # Local development script
└── database/
    └── db.py           # Database utilities
```

## ⚙️ Installation & Setup

### Prerequisites
- Python 3.9+
- MongoDB instance (local or cloud)
- Git

### 1. Clone the Repository
```bash
git clone <repository-url>
cd MicroBlog
```

### 2. Environment Setup
```bash
# Using pipenv (recommended)
pip install pipenv
pipenv install
pipenv shell

# Or using pip
pip install -r requirements.txt
```

### 3. Environment Variables
Create a `.env` file in the root directory:
```env
SECRET_KEY=your_secret_key_here
MONGO_BASE=mongodb://
MONGO_USER=your_mongodb_username
MONGO_PASSWORD=your_mongodb_password
MONGO_REMAINING=@cluster.mongodb.net/microblog?retryWrites=true&w=majority
```

### 4. Database Setup
Ensure your MongoDB instance is running and accessible with the provided credentials.

## 🚀 Running the Application

### Local Development
```bash
# Using the provided script
chmod +x run.sh
./run.sh

# Or directly with Flask
export FLASK_APP=main.py
export FLASK_ENV=development
flask run
```

### Production Deployment
The application is configured for Heroku deployment:
```bash
# Deploy to Heroku
git push heroku main
```

## 📊 Core Components

### [`User`](user.py) Class
- User registration and authentication
- Password hashing with bcrypt
- Session management
- Blog and post statistics
- User profile management

### [`Blog`](blog.py) Class
- Blog creation and management
- Author association
- Post relationship handling
- CRUD operations

### [`Entry`](entry.py) Class
- Individual blog post management
- Content and metadata storage
- Date/time tracking
- Blog association

### [`Database`](db.py) Class
- MongoDB connection wrapper
- CRUD operation utilities
- Query execution
- Connection management

## 🌐 API Routes

| Route | Method | Description |
|-------|--------|-------------|
| `/` | GET/POST | Home page with recent posts |
| `/login` | GET | Login form |
| `/register` | GET | Registration form |
| `/auth/login` | POST | Process login |
| `/auth/register` | POST | Process registration |
| `/blogs` | GET/POST | User's blogs list/delete |
| `/blogs/new` | GET/POST | Create new blog |
| `/posts/<blog_id>` | GET | View blog posts |
| `/posts/new/<blog_id>` | GET/POST | Create new post |
| `/profile/<user_id>` | GET | User profile |
| `/logout` | GET | User logout |

## 🔒 Security Features

- **Password Hashing**: Bcrypt for secure password storage
- **Session Management**: Flask-Login for user sessions
- **Authentication Required**: Protected routes for authenticated users
- **Input Validation**: Form data validation and sanitization

## 📈 Features Implemented

- ✅ User registration and authentication
- ✅ Dynamic blog creation and deletion
- ✅ Quick post creation from home page
- ✅ User profile pages
- ✅ Blog and post statistics
- ✅ Responsive web interface
- ✅ MongoDB integration
- ✅ Production-ready deployment configuration

## 🛣️ Future Enhancements

- [ ] Rich text editor for posts
- [ ] Image upload functionality
- [ ] User following system
- [ ] Comment system
- [ ] Search functionality
- [ ] Email verification
- [ ] Admin panel
- [ ] API endpoints for mobile app

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- Initial inspiration from [Web-dev with Flask and Python](https://www.udemy.com/course/web-developer-bootcamp-flask-python/) Udemy course
- Flask community for excellent documentation
- MongoDB for reliable data storage

## 📧 Contact

For questions or suggestions, please open an issue in the repository.

---

**Note**: This project demonstrates a complete full-stack web application with user authentication, database integration, and modern web development practices using Flask and MongoDB.
