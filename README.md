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