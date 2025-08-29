# 🛍️ RedStore - E-Commerce Platform

A modern, full-stack e-commerce website built with Spring Boot backend and HTML/CSS/JavaScript frontend.

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Usage](#-usage)
- [API Endpoints](#-api-endpoints)
- [Database Schema](#-database-schema)
- [Features Overview](#-features-overview)
- [Screenshots](#-screenshots)
- [Contributing](#-contributing)
- [License](#-license)

## ✨ Features

### 🛒 Shopping Features
- **Product Catalog**: Browse products by categories (Electronics, Fashion, Home & Living, Beauty)
- **Search & Filter**: Advanced search with price range and category filters
- **Shopping Cart**: Add/remove items, update quantities, view cart total
- **Order Management**: Complete order history with tracking
- **User Authentication**: Secure login/signup system

### 👤 User Account Features
- **Profile Management**: Update personal information
- **Address Management**: Add, edit, delete, and set default addresses
- **Order Tracking**: Real-time order status and delivery tracking
- **Order History**: Complete purchase history with "Buy Again" functionality
- **Contact Support**: Integrated contact form for customer support

### 🎨 UI/UX Features
- **Responsive Design**: Works perfectly on desktop, tablet, and mobile
- **Modern Interface**: Clean, intuitive design inspired by Amazon/Flipkart
- **Real-time Updates**: Dynamic cart count and order status updates
- **Smooth Animations**: Enhanced user experience with subtle animations
- **Error Handling**: Comprehensive error messages and validation

## 🛠️ Tech Stack

### Backend
- **Java 17**
- **Spring Boot 3.x**
- **Spring Data JPA**
- **MySQL Database**
- **Maven Build Tool**

### Frontend
- **HTML5**
- **CSS3** (with modern features like Flexbox, Grid, Animations)
- **Vanilla JavaScript** (ES6+)
- **Font Awesome Icons**
- **Responsive Design**

### Database
- **MySQL 8.0**
- **JPA/Hibernate ORM**

## 📁 Project Structure

```
RedStore/
├── src/
│   ├── frontend/                 # Frontend files
│   │   ├── shopping.html         # Main shopping page
│   │   ├── products.html         # Product catalog
│   │   ├── cart.html            # Shopping cart
│   │   ├── Login.html           # Login page
│   │   ├── signup.html          # Registration page
│   │   ├── Account.html         # User account dashboard
│   │   ├── *.css                # Stylesheets
│   │   └── assets/              # Images and static assets
│   │
│   └── backend/                 # Spring Boot application
│       ├── src/main/java/
│       │   └── com/example/Shopping/website/
│       │       ├── Entity/      # JPA entities
│       │       ├── Repository/  # Data access layer
│       │       ├── Service/     # Business logic
│       │       ├── Controller/  # REST API endpoints
│       │       └── DataInitializer.java
│       ├── src/main/resources/
│       │   └── application.properties
│       └── pom.xml
│
└── README.md
```

## 🚀 Installation

### Prerequisites
- Java 17 or higher
- MySQL 8.0 or higher
- Maven 3.6 or higher
- Modern web browser

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd RedStore
   ```

2. **Configure Database**
   ```sql
   CREATE DATABASE redstore;
   CREATE USER 'redstore_user'@'localhost' IDENTIFIED BY 'your_password';
   GRANT ALL PRIVILEGES ON redstore.* TO 'redstore_user'@'localhost';
   FLUSH PRIVILEGES;
   ```

3. **Update Database Configuration**
   Edit `src/backend/src/main/resources/application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/redstore
   spring.datasource.username=redstore_user
   spring.datasource.password=your_password
   ```

4. **Build and Run Backend**
   ```bash
   cd src/backend
   mvn clean install
   mvn spring-boot:run
   ```
   Backend will start on `http://localhost:8080`

### Frontend Setup

1. **Open Frontend Files**
   - Navigate to `src/frontend/`
   - Open `shopping.html` in your web browser
   - Or use a local server (recommended):
     ```bash
     # Using Python
     python -m http.server 5502
     
     # Using Node.js
     npx http-server -p 5502
     ```

2. **Access the Application**
   - Main URL: `http://localhost:5502/src/frontend/shopping.html`
   - Products: `http://localhost:5502/src/frontend/products.html`
   - Cart: `http://localhost:5502/src/frontend/cart.html`

## 📖 Usage

### For Customers

1. **Browse Products**
   - Visit the main shopping page
   - Use category filters and search functionality
   - View product details and prices

2. **Create Account**
   - Click "Sign Up" to create a new account
   - Fill in personal details and address information
   - Verify email and complete registration

3. **Shopping Experience**
   - Add products to cart
   - Review cart and proceed to checkout
   - Complete payment and place order
   - Track order status in account dashboard

4. **Account Management**
   - View order history
   - Manage delivery addresses
   - Update profile information
   - Contact customer support

### For Administrators

1. **Product Management**
   - Add new products via database or API
   - Update product information
   - Manage inventory levels

2. **Order Management**
   - View all customer orders
   - Update order status
   - Process refunds and cancellations

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/signup` - User registration
- `POST /api/auth/logout` - User logout

### Products
- `GET /api/products` - Get all products
- `GET /api/products/{id}` - Get product by ID
- `GET /api/products/category/{category}` - Get products by category

### Cart
- `GET /api/cart/{username}` - Get user's cart
- `POST /api/cart/add` - Add item to cart
- `PUT /api/cart/update` - Update cart item quantity
- `DELETE /api/cart/remove/{id}` - Remove item from cart

### Orders
- `GET /api/orders/{username}` - Get user's orders
- `POST /api/orders` - Create new order
- `PUT /api/orders/{id}/status` - Update order status

### Addresses
- `GET /api/addresses/{username}` - Get user's addresses
- `POST /api/addresses` - Add new address
- `PUT /api/addresses/{id}` - Update address
- `DELETE /api/addresses/{id}` - Delete address
- `PUT /api/addresses/{id}/default` - Set default address

### Contact
- `POST /api/contact-messages` - Submit contact form

## 🗄️ Database Schema

### Core Tables
- **users** - User account information
- **products** - Product catalog
- **cart** - Shopping cart items
- **orders** - Order information
- **addresses** - User delivery addresses
- **contact_messages** - Customer support messages

### Key Relationships
- Users can have multiple addresses
- Users can have multiple orders
- Orders contain multiple cart items
- Products are categorized by type

## 🎯 Features Overview

### 🔐 Security Features
- Password encryption
- Session management
- Input validation
- SQL injection prevention

### 📱 Responsive Design
- Mobile-first approach
- Cross-browser compatibility
- Touch-friendly interface
- Adaptive layouts

### ⚡ Performance Features
- Optimized database queries
- Efficient image loading
- Minimal HTTP requests
- Caching strategies

### 🛡️ Error Handling
- Comprehensive validation
- User-friendly error messages
- Graceful degradation
- Logging and monitoring

## 📸 Screenshots

### 🏠 **Homepage - RedStore Landing**
![RedStore Homepage](assests/Screenshot%20(114).png)
*Modern e-commerce homepage featuring:*
- **Hero Section**: Dynamic athlete imagery with "Your Ultimate Shopping Destination" tagline
- **Search Bar**: Advanced product search with category filters
- **Navigation**: Clean purple header with logo, user actions, and delivery options
- **Featured Content**: Promotional banners and product highlights

### 🛍️ **Product Catalog - Smart Shopping**
![Product Catalog](assests/Screenshot%20(115).png)
*Comprehensive product browsing experience:*
- **Category Filters**: Electronics, Fashion, Home & Living, Beauty categories
- **Price Range Slider**: Interactive price filtering (₹0 - ₹100,000)
- **Product Grid**: 23 products displayed with "New" and "Best Seller" badges
- **Sorting Options**: Relevance-based product sorting
- **Product Cards**: iPhone and MacBook examples with wishlist and quick view features

### 🔐 **User Authentication - Secure Login**
![Login Page](assests/Screenshot%20(116).png)
*Professional authentication interface:*
- **Clean Design**: Purple background with centered white login panel
- **Form Fields**: Email/username and password with visibility toggle
- **User Experience**: Remember me checkbox and forgot password link
- **Brand Consistency**: RedStore logo and branding throughout

### 👤 **Account Dashboard - Personal Hub**
![Account Dashboard](assests/Screenshot%20(117).png)
*Complete user account management:*
- **Welcome Message**: Personalized greeting "Welcome back, M.omeprakash"
- **Navigation Tabs**: Overview, Order History, Profile, Addresses, Contact, Track Order
- **Profile Card**: User avatar with name and email display
- **Order Summary**: "2 Total Orders" with shopping bag icon
- **Quick Actions**: Easy access to all account features

### 📱 **Responsive Design**
*All pages are fully responsive and optimized for:*
- **Desktop**: Full-featured experience with sidebar navigation
- **Tablet**: Adaptive layouts with touch-friendly interfaces
- **Mobile**: Mobile-first design with optimized navigation
- **Cross-Browser**: Consistent experience across Chrome, Firefox, Safari, Edge

### 🎨 **Design Highlights**
- **Color Scheme**: Professional purple and white theme
- **Typography**: Clean, readable fonts with proper hierarchy
- **Icons**: Font Awesome icons for enhanced user experience
- **Animations**: Smooth transitions and hover effects
- **Accessibility**: WCAG compliant design elements

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines
- Follow Java coding conventions
- Use meaningful commit messages
- Test thoroughly before submitting
- Update documentation as needed

## 📝 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### License Summary:
- ✅ **Commercial Use**: Allowed
- ✅ **Modification**: Allowed  
- ✅ **Distribution**: Allowed
- ✅ **Private Use**: Allowed
- ❌ **Liability**: Limited
- ❌ **Warranty**: No warranty provided

### Copyright Notice:
```
Copyright (c) 2024 Motukuri Omeprakash

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 📞 Support

For support and questions:
- Email: mothukuriomeprakash@gmail.com
- Create an issue in the repository
- Check the documentation

## 🚀 Deployment

### Production Deployment
1. Build the backend JAR file
2. Configure production database
3. Set up web server (Apache/Nginx)
4. Deploy frontend files
5. Configure SSL certificates
6. Set up monitoring and logging

### Environment Variables
```bash
# Database
DB_URL=jdbc:mysql://localhost:3306/redstore
DB_USERNAME=redstore_user
DB_PASSWORD=secure_password

# Server
SERVER_PORT=8080
SERVER_CONTEXT_PATH=/api

# Security
JWT_SECRET=your_jwt_secret_key
```

---

## 👨‍💻 Developer

**Motukuri Omeprakash** - Full Stack Developer

- **Email**: mothukuriomeprakash@gmail.com
- **GitHub**: [@MotukuriOmeprakash](https://github.com/MotukuriOmeprakash)
- **LinkedIn**: [Motukuri Omeprakash](https://www.linkedin.com/in/omeprakashmotukuri/)

---

**RedStore** - Your Ultimate Shopping Destination 🛍️

Built with ❤️ by **Motukuri Omeprakash** using Spring Boot and modern web technologies.
