# Next.js Authentication Project 🚀

<p align="center">
  <img src="https://cdn.freelogovectors.net/wp-content/uploads/2023/09/next-js-logo-freelogovectors.net_.png" alt="Next.js Logo" width="200">
</p>

A comprehensive authentication system built with Next.js, NextAuth.js, and Drizzle ORM. This project provides a complete authentication flow including user registration, login, password management, and two-factor authentication.

## Features ✨

- **User Authentication**
  - Email and password login
  - Session management with NextAuth.js
  - Protected routes with middleware

- **User Registration**
  - Email validation
  - Password strength requirements
  - Duplicate email detection

- **Password Management**
  - Password reset via email
  - Password change for authenticated users
  - Secure password hashing with bcrypt

- **Two-Factor Authentication (2FA)**
  - Google Authenticator integration
  - QR code generation for easy setup
  - Enable/disable 2FA from user account

- **Security Features**
  - CSRF protection
  - Rate limiting
  - Secure HTTP-only cookies
  - Password validation with Zod

## Project Structure 📁

```
nextjs-nextauth-dizzle/
├── app/                      # Next.js app directory
│   ├── (logged-in)/          # Protected routes for authenticated users
│   │   ├── change-password/  # Password change functionality
│   │   ├── my-account/       # User account management
│   │   └── layout.tsx        # Layout for authenticated routes
│   ├── (logged-out)/         # Public routes
│   │   ├── login/            # Login functionality
│   │   ├── register/         # User registration
│   │   ├── password-reset/   # Password reset flow
│   │   └── update-password/  # Password update after reset
│   └── api/                  # API routes
├── components/               # UI components
│   └── ui/                   # Shadcn UI components
├── db/                       # Database configuration
│   ├── drizzle.ts            # Drizzle ORM setup
│   ├── usersSchema.ts        # User table schema
│   └── passwordResetTokensSchema.ts # Password reset tokens schema
├── lib/                      # Utility functions
│   ├── email.ts              # Email sending functionality
│   └── utils.ts              # Helper functions
├── public/                   # Static assets
├── validation/               # Zod validation schemas
│   ├── passwordMatchSchema.ts # Password matching validation
│   └── passwordSchema.ts     # Password strength validation
└── auth.ts                   # NextAuth.js configuration
```

## Technologies Used 🛠️

- **Frontend**
  - [Next.js 14](https://nextjs.org/) - React framework
  - [React](https://reactjs.org/) - UI library
  - [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
  - [Shadcn UI](https://ui.shadcn.com/) - UI component library

- **Authentication**
  - [NextAuth.js](https://next-auth.js.org/) - Authentication for Next.js
  - [bcrypt](https://www.npmjs.com/package/bcryptjs) - Password hashing
  - [otplib](https://www.npmjs.com/package/otplib) - TOTP for 2FA
  - [qrcode.react](https://www.npmjs.com/package/qrcode.react) - QR code generation

- **Database**
  - [Drizzle ORM](https://orm.drizzle.team/) - TypeScript ORM
  - [PostgreSQL](https://www.postgresql.org/) - Relational database

- **Validation**
  - [Zod](https://zod.dev/) - TypeScript-first schema validation
  - [React Hook Form](https://react-hook-form.com/) - Form validation

## Getting Started 🚀

### Prerequisites

- Node.js 18+ and npm
- PostgreSQL database

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/nextjs-nextauth-dizzle.git
cd nextjs-nextauth-dizzle
```

2. Install dependencies
```bash
npm install
```

3. Set up environment variables
Create a `.env.local` file in the root directory with the following variables:
```
# Database
DATABASE_URL=postgresql://username:password@localhost:5432/your_database

# NextAuth
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your-nextauth-secret

# Email (for password reset)
EMAIL_SERVER=smtp://username:password@smtp.example.com:587
EMAIL_FROM=noreply@example.com
```

4. Run database migrations
```bash
npm run db:migrate
```

5. Start the development server
```bash
npm run dev
```

6. Open [http://localhost:3000](http://localhost:3000) in your browser

## Authentication Flow 🔄

### Registration
1. User enters email and password
2. System validates input and checks for duplicate emails
3. Password is hashed and stored in the database
4. User is redirected to login page

### Login
1. User enters email and password
2. System validates credentials
3. If 2FA is enabled, user is prompted for OTP
4. On successful authentication, user is redirected to account page

### Password Reset
1. User requests password reset by providing email
2. System sends reset link with token to user's email
3. User clicks link and enters new password
4. System validates token and updates password

### Two-Factor Authentication
1. User enables 2FA from account settings
2. System generates QR code for Google Authenticator
3. User scans QR code and enters OTP to confirm
4. 2FA is enabled for future logins

## Security Considerations 🔒

- Passwords are hashed using bcrypt
- Authentication tokens are short-lived and rotated
- Two-factor authentication adds an extra layer of security
- Form inputs are validated on both client and server
- Protected routes are secured with middleware
- CSRF protection is enabled

## License 📝

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgements 🙏

- [Next.js Documentation](https://nextjs.org/docs)
- [NextAuth.js Documentation](https://next-auth.js.org/getting-started/introduction)
- [Drizzle ORM Documentation](https://orm.drizzle.team/docs/overview)
- [Shadcn UI](https://ui.shadcn.com/)