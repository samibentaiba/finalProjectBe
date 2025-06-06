# Final Project Backend

This is the backend for the Final Project, built using Node.js, Express, and Prisma as the ORM. The project follows a clean architecture, organizing files into separate directories for better maintainability and scalability.

## Data Flow

```
Database → Repository → Services → Controller → Routes → Server
```

## Project Structure

```
.
├── config
│   ├── database.js          # Database configuration
│   └── passport.js          # Authentication configuration using Passport.js
├── controllers              # Handles request logic and calls services
│   ├── actionController.js
│   ├── adminController.js
│   ├── appointmentController.js
│   ├── appointmentTypeController.js
│   ├── authController.js
│   ├── doctorController.js
│   ├── patientController.js
│   └── paymentController.js
├── hook.js                  # Webhook implementation (if needed)
├── mailer.js                # Email service configuration
├── middlewares
│   └── authMiddleware.js    # Middleware for authentication and authorization
├── nodemon.json             # Configuration for nodemon (automatic server restart)
├── package.json             # Project dependencies and scripts
├── package-lock.json        # Lock file for dependencies
├── prisma                   # Database management (Prisma ORM)
│   ├── migrations           # Database migration files
│   ├── schema.prisma        # Prisma schema definition
│   └── seed.js              # Database seeding script
├── README.md                # Project documentation (this file)
├── repositories             # Data access layer (DB queries)
│   ├── actionRepository.js
│   ├── adminRepository.js
│   ├── appointmentRepository.js
│   ├── appointmentTypeRepository.js
│   ├── authRepository.js
│   ├── doctorRepository.js
│   ├── patientRepository.js
│   └── paymentRepository.js
├── restart.flag             # A flag for restarting the server
├── routes                   # API routes definitions
│   ├── actionRoutes.js
│   ├── adminRoutes.js
│   ├── appointmentRoutes.js
│   ├── appointmentTypeRoutes.js
│   ├── authRoutes.js
│   ├── doctorRoutes.js
│   ├── patientRoutes.js
│   └── paymentRoutes.js
├── server.js                # Entry point of the application
├── services                 # Business logic layer
│   ├── actionService.js
│   ├── adminService.js
│   ├── appointmentService.js
│   ├── appointmentTypeService.js
│   ├── authService.js
│   ├── doctorService.js
│   ├── mailService.js
│   ├── patientService.js
│   └── paymentService.js
└── utils                    # Utility functions
    └── tokenUtil.js         # Token generation and validation utilities
```

## Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/finalProjectBe.git
   cd finalProjectBe
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Set up the environment variables:

   - Create a `.env` file in the root directory and add your configuration variables.

   **Example `.env` File:**

   ```env
   # Database Configuration (PostgreSQL Required)
   DATABASE_URL=postgresql://<USERNAME>:<PASSWORD>@localhost:5432/<DATABASE_NAME>

   # Application URLs
   FRONTEND_URL=http://localhost:3000
   BACKEND_URL=http://localhost:4000

   # Authentication Secrets
   JWT_SECRET=<GENERATE_A_STRONG_SECRET>
   REFRESH_TOKEN_SECRET=<GENERATE_A_STRONG_SECRET>
   JWT_TEMP_SECRET=<GENERATE_A_STRONG_SECRET>

   # Email Configuration
   GMAIL_USER=<YOUR_GMAIL>
   GMAIL_PASSWORD=<YOUR_APP_PASSWORD>

   # Google OAuth Credentials
   GOOGLE_CLIENT_ID=<YOUR_GOOGLE_CLIENT_ID>
   GOOGLE_CLIENT_SECRET=<YOUR_GOOGLE_CLIENT_SECRET>
   GOOGLE_CALLBACK_URL=http://localhost:4000/auth/google/callback

   # Server Configuration
   NODE_ENV=development
   PORT=4000
   ```

   **Important:** This project requires a PostgreSQL database to work properly. Ensure you have PostgreSQL installed and running before proceeding.

   **Security Best Practices:**

   - **Never commit `.env` files** to Git. Add it to `.gitignore`.
   - **Use `.env.example`** (without real values) for documentation.
   - **Generate strong secrets** using:
     ```sh
     openssl rand -hex 32
     ```
   - **Use a secret manager** for production (e.g., AWS Secrets Manager, HashiCorp Vault).

4. Run database migrations:
   ```sh
   npx prisma migrate dev
   ```
5. Seed the database (optional):
   ```sh
   node prisma/seed.js
   ```
6. Start the server:
   ```sh
   npm run dev
   ```

## API Endpoints

Each module (e.g., authentication, appointments, patients) has a set of routes defined in the `routes` directory. Controllers handle requests and interact with services to execute business logic.

### Authentication

- `POST /auth/register` - Register a new user
- `POST /auth/login` - Login and receive a JWT
- `POST /auth/logout` - Logout the user

### Users (Admin, Doctor, Patient)

- `GET /admin` - Retrieve all admins
- `GET /doctors` - Retrieve all doctors
- `GET /patients` - Retrieve all patients

### Appointments

- `POST /appointments` - Create an appointment
- `GET /appointments` - List all appointments
- `DELETE /appointments/:id` - Cancel an appointment

## Technologies Used

- **Node.js & Express** - Backend framework
- **Prisma** - ORM for database management
- **PostgreSQL** - Relational database
- **Passport.js** - Authentication middleware
- **JWT** - Token-based authentication
- **Nodemailer** - Email service
- **Nodemon** - Auto-restarting development server

## Contributing

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -m 'Add feature X'`
4. Push to the branch: `git push origin feature-name`
5. Open a Pull Request.

## License

This project is licensed under the MIT License.

.
├── config
│   ├── database.js          # Database configuration
│   └── passport.js          # Authentication configuration using Passport.js
├── controllers              # Handles request logic and calls services
│   ├── actionController.js
│   ├── adminController.js
│   ├── appointmentController.js
│   ├── appointmentTypeController.js
│   ├── authController.js
│   ├── doctorController.js
│   ├── patientController.js
│   └── paymentController.js
├── hook.js                  # Webhook implementation (if needed)
├── mailer.js                # Email service configuration
├── middlewares
│   └── authMiddleware.js    # Middleware for authentication and authorization
├── nodemon.json             # Configuration for nodemon (automatic server restart)
├── package.json             # Project dependencies and scripts
├── package-lock.json        # Lock file for dependencies
├── prisma                   # Database management (Prisma ORM)
│   ├── migrations           # Database migration files
│   ├── schema.prisma        # Prisma schema definition
│   └── seed.js              # Database seeding script
├── README.md                # Project documentation (this file)
├── repositories             # Data access layer (DB queries)
│   ├── actionRepository.js
│   ├── adminRepository.js
│   ├── appointmentRepository.js
│   ├── appointmentTypeRepository.js
│   ├── authRepository.js
│   ├── doctorRepository.js
│   ├── patientRepository.js
│   └── paymentRepository.js
├── restart.flag             # A flag for restarting the server
├── routes                   # API routes definitions
│   ├── actionRoutes.js
│   ├── adminRoutes.js
│   ├── appointmentRoutes.js
│   ├── appointmentTypeRoutes.js
│   ├── authRoutes.js
│   ├── doctorRoutes.js
│   ├── patientRoutes.js
│   └── paymentRoutes.js
├── server.js                # Entry point of the application
├── services                 # Business logic layer
│   ├── actionService.js
│   ├── adminService.js
│   ├── appointmentService.js
│   ├── appointmentTypeService.js
│   ├── authService.js
│   ├── doctorService.js
│   ├── mailService.js
│   ├── patientService.js
│   └── paymentService.js
└── utils                    # Utility functions
    └── tokenUtil.js         # Token generation and validation utilities