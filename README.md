# Backend POS (Point of Sale)

Backend API untuk aplikasi Point of Sale (POS) yang dibangun dengan Node.js, Express, dan Prisma ORM.

## 🚀 Features

- **Authentication & Authorization**: JWT-based authentication system
- **User Management**: User registration and login with role-based access
- **Product Management**: CRUD operations for products with categories and suppliers
- **Inventory Management**: Stock tracking and management
- **Order Processing**: Complete order lifecycle management
- **Order Returns**: Return order functionality
- **Purchase Management**: Purchase order tracking
- **Shopping Cart**: Cart functionality for customers
- **File Upload**: Support for product images and documents
- **Export Functionality**: Excel and PDF export capabilities
- **Logging**: Comprehensive logging with Winston
- **Input Validation**: Request validation with Joi
- **CORS Support**: Cross-origin resource sharing enabled

## 🛠 Tech Stack

- **Runtime**: Node.js
- **Framework**: Express.js 5.1.0
- **Database**: MySQL with Prisma ORM
- **Authentication**: JWT (jsonwebtoken)
- **Password Hashing**: bcrypt
- **File Upload**: express-fileupload
- **Validation**: Joi
- **Logging**: Winston with daily rotate files
- **Export**: ExcelJS, PDF Creator Node
- **Development**: Nodemon, ESLint

## 📋 Prerequisites

- Node.js (v18 or higher)
- MySQL database
- npm or yarn package manager

## ⚙️ Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/mirzam-muhammad/backend-pos.git
   cd backend-pos
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   
   Create a `.env` file in the root directory:
   ```env
   DATABASE_URL="mysql://username:password@localhost:3306/pos_database"
   PORT=4300
   JWT_SECRET=your_jwt_secret_key
   ```

4. **Database Setup**
   ```bash
   # Generate Prisma client
   npx prisma generate
   
   # Run database migrations
   npx prisma migrate dev
   
   # (Optional) Seed the database
   npx prisma db seed
   ```

## 🚀 Running the Application

### Development Mode
```bash
npm run dev
```

### Production Mode
```bash
npm start
```

The server will start on `http://localhost:4300` (or the port specified in your `.env` file).

## 📁 Project Structure

```
backend-pos/
├── src/
│   ├── controllers/        # Route controllers
│   │   └── user.controller.js
│   ├── middleware/         # Custom middleware
│   │   └── index.js
│   ├── routes/            # API routes
│   │   ├── index.js
│   │   └── user.route.js
│   ├── utils/             # Utility functions
│   │   ├── bcript.js      # Password hashing
│   │   ├── client.js      # Prisma client
│   │   ├── documentPattern.js # Document generators
│   │   ├── jwt.js         # JWT utilities
│   │   └── winston.js     # Logging configuration
│   ├── validations/       # Input validation schemas
│   │   ├── category.validation.js
│   │   ├── orderReturn.validation.js
│   │   ├── product.validation.js
│   │   ├── purchase.validation.js
│   │   ├── supplier.validation.js
│   │   └── user.validation.js
│   └── index.js          # Application entry point
├── prisma/
│   ├── migrations/        # Database migrations
│   └── schema.prisma     # Database schema
├── public/               # Static files
├── logs/                # Application logs
└── package.json
```

## 🗃️ Database Schema

The application uses the following main entities:

- **User**: System users with role-based access
- **Category**: Product categories
- **Supplier**: Product suppliers
- **Product**: Products with inventory tracking
- **Carts**: Shopping cart items
- **Orders**: Customer orders
- **OrderDetail**: Order line items
- **OrderReturn**: Return orders
- **OrderReturnDetail**: Return order line items
- **Purchase**: Purchase orders
- **PurchaseDetail**: Purchase order line items

## 🔌 API Endpoints

### Authentication
- `POST /api/users` - Create new user

### Available Routes
The API follows RESTful conventions. Current implemented routes:
- User management endpoints

*More endpoints will be documented as they are implemented.*

## 🔧 Configuration

### Environment Variables
- `DATABASE_URL`: MySQL connection string
- `PORT`: Server port (default: 4300)
- `JWT_SECRET`: Secret key for JWT token generation

### Logging
Logs are stored in the `logs/` directory with daily rotation. Log levels include:
- Error logs: Application errors and exceptions
- Info logs: General application information
- Debug logs: Detailed debugging information

## 🧪 Development

### Code Style
The project uses ESLint for code linting. Run:
```bash
npm run lint
```

### Database Operations
```bash
# View database in Prisma Studio
npx prisma studio

# Reset database
npx prisma migrate reset

# Deploy migrations to production
npx prisma migrate deploy
```

## 🐛 Troubleshooting

### Common Issues

1. **Prisma Client Not Initialized**
   ```bash
   npx prisma generate
   ```

2. **Database Connection Issues**
   - Check your `DATABASE_URL` in `.env`
   - Ensure MySQL server is running
   - Verify database credentials

3. **Port Already in Use**
   - Change the `PORT` in your `.env` file
   - Kill the process using the port: `lsof -ti:4300 | xargs kill`

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📧 Contact

**Author**: Mirzam  
**Repository**: [https://github.com/mirzam-muhammad/backend-pos](https://github.com/mirzam-muhammad/backend-pos)

## 🔄 Recent Updates

### v1.0.0
- Fixed Prisma Client initialization issues
- Resolved Express routing path-to-regexp errors
- Implemented comprehensive logging system
- Added file upload functionality
- Set up validation middleware
- Configured CORS for cross-origin requests

---

Made with ❤️ for efficient POS management