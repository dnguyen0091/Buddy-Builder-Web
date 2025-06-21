# Buddy Builder 🚀

**Your ultimate companion for managing and connecting with your contacts.**

A modern, responsive CRUD (Create, Read, Update, Delete) contact management application built with vanilla JavaScript, PHP, and MySQL. Buddy Builder provides an intuitive interface for organizing your personal and professional contacts with advanced features like real-time search, multiple display modes, and form validation.

## ✨ Features

### Core Functionality
- **User Authentication**: Secure sign-up and login system
- **Contact Management**: Full CRUD operations for contacts
- **Real-time Search**: Instantly find contacts by name, email, or phone
- **Dual Display Modes**: Switch between grid and list views
- **Form Validation**: Client-side validation with visual feedback
- **Responsive Design**: Works seamlessly across desktop and mobile devices

### Advanced Features
- **Lazy Loading**: Optimized performance with intersection observer
- **Visual Feedback**: Interactive UI elements with smooth transitions
- **Password Security**: Toggle password visibility with eye icons
- **Input Validation**: Real-time validation with requirement indicators
- **Error Handling**: Comprehensive error management and user feedback

## 🛠️ Tech Stack

### Frontend
- **HTML5**: Semantic markup structure
- **CSS3**: Custom styling with CSS Grid, Flexbox, and animations
- **Vanilla JavaScript**: ES6+ features, async/await, DOM manipulation
- **SVG Icons**: Custom scalable vector graphics

### Backend
- **PHP**: Server-side logic and API endpoints
- **MySQL**: Relational database for data persistence
- **JSON**: Data exchange format between client and server

### Development Tools
- **VS Code**: Primary development environment
- **Git**: Version control system

## 📁 Project Structure

```
BuddyBuilder/
├── index.html              # Main application entry point
├── assets/                 # Static assets (SVG icons, images)
│   ├── add.svg
│   ├── correct.svg
│   ├── eyeClosed.svg
│   ├── eyeOpen.svg
│   ├── grid.svg
│   ├── list.svg
│   ├── lock.svg
│   ├── logo.png
│   ├── rocket.svg
│   ├── search.svg
│   ├── stars.png
│   ├── twinkling.png
│   ├── user.svg
│   └── wrong.svg
├── css/
│   └── index.css           # Main stylesheet
├── js/                     # JavaScript modules
│   ├── index.js           # Main application logic
│   ├── createContact.js   # Contact creation functionality
│   ├── displaySwitch.js   # Display mode switching
│   ├── editContact.js     # Contact editing functionality
│   └── validateForm.js    # Form validation utilities
├── LAMPAPI/               # PHP API endpoints
│   ├── AddContact.php     # Create new contact
│   ├── deleteContact.php  # Delete contact
│   ├── EditContact.php    # Update contact
│   ├── Login.php          # User authentication
│   ├── register.php       # User registration
│   └── SearchContacts.php # Search functionality
└── Readme.md             # Project documentation
```

## 🚀 Getting Started

### Prerequisites
- **Web Server**: Apache/Nginx with PHP support
- **PHP**: Version 7.4 or higher
- **MySQL**: Version 5.7 or higher
- **Browser**: Modern browser with ES6+ support

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd BuddyBuilder
   ```

2. **Set up the database**
   ```sql
   CREATE DATABASE COP4331;
   USE COP4331;
   
   CREATE TABLE Users (
       ID INT AUTO_INCREMENT PRIMARY KEY,
       FirstName VARCHAR(50) NOT NULL,
       LastName VARCHAR(50) NOT NULL,
       Login VARCHAR(50) UNIQUE NOT NULL,
       Password VARCHAR(255) NOT NULL
   );
   
   CREATE TABLE Contacts (
       ID INT AUTO_INCREMENT PRIMARY KEY,
       FirstName VARCHAR(50) NOT NULL,
       LastName VARCHAR(50) NOT NULL,
       Phone VARCHAR(20) NOT NULL,
       Email VARCHAR(100) NOT NULL,
       UserID INT NOT NULL,
       FOREIGN KEY (UserID) REFERENCES Users(ID)
   );
   ```

3. **Configure database connection**
   Update the database credentials in the PHP files:
   ```php
   $conn = new mysqli("localhost", "your_username", "your_password", "COP4331");
   ```

4. **Deploy to web server**
   - Copy files to your web server directory
   - Ensure PHP has proper permissions
   - Access via `http://localhost/BuddyBuilder`

## 📋 API Endpoints

### Authentication
- `POST /LAMPAPI/register.php` - Register new user
- `POST /LAMPAPI/Login.php` - Authenticate user

### Contact Management
- `POST /LAMPAPI/AddContact.php` - Create new contact
- `POST /LAMPAPI/SearchContacts.php` - Search contacts
- `POST /LAMPAPI/EditContact.php` - Update contact
- `DELETE /LAMPAPI/deleteContact.php` - Delete contact

### Request/Response Format
```javascript
// Example: Add Contact Request
{
    "firstName": "John",
    "lastName": "Doe",
    "phone": "123-456-7890",
    "email": "john.doe@example.com",
    "userID": 1
}

// Example: Response
{
    "id": 15,
    "error": ""
}
```

## 🎨 User Interface

### Key Components
- **Header**: Navigation with sign-in/up button
- **Search Bar**: Real-time contact search with auto-complete
- **Display Toggle**: Switch between grid and list views
- **Contact Cards**: Interactive contact display with edit/delete actions
- **Modal Forms**: Overlay forms for adding/editing contacts
- **Validation Feedback**: Real-time form validation with visual indicators

### Responsive Design
- **Mobile-first approach**: Optimized for mobile devices
- **Flexible layouts**: CSS Grid and Flexbox for adaptive layouts
- **Touch-friendly**: Large touch targets for mobile interaction

## 🔧 Features in Detail

### Form Validation
- **Real-time validation**: Instant feedback as users type
- **Visual indicators**: Color-coded borders and icons
- **Password requirements**: Strength indicators with live feedback
- **Email validation**: Format verification with regex patterns

### Search Functionality
- **Instant search**: Real-time filtering as you type
- **Multiple fields**: Search across name, email, and phone
- **Fuzzy matching**: Flexible search algorithm
- **No results handling**: Graceful empty state management

### Security Features
- **Password hashing**: Secure password storage
- **Input sanitization**: Protection against XSS and SQL injection
- **Session management**: Secure user authentication
- **CORS handling**: Proper cross-origin request management

## 🐛 Troubleshooting

### Common Issues

**Empty form values**
- Ensure event listeners are attached after DOM load
- Check for conflicting validation functions
- Verify input name attributes match JavaScript selectors

**JSON parsing errors**
- Remove debug output from PHP files
- Ensure proper Content-Type headers
- Validate JSON structure before sending

**Database connection issues**
- Verify MySQL credentials
- Check database and table existence
- Ensure proper permissions for PHP user

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Your Name** - *Initial work* - [YourGitHub](https://github.com/yourusername)

## 🙏 Acknowledgments

- Icons provided by custom SVG assets
- CSS animations and transitions for enhanced UX
- Modern JavaScript features for optimal performance
- PHP and MySQL for robust backend functionality

---

**Built with ❤️ for COP4331C - Processes for Object Oriented Software Development**