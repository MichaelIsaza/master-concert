<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[OP.GG](https://op.gg)**
- **[CMS Max](https://www.cmsmax.com/)**
- **[WebReinvent](https://webreinvent.com/?utm_source=laravel&utm_medium=github&utm_campaign=patreon-sponsors)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).





# 🎶 Concert Ticket Reservation System

A full-stack web application built with **Laravel 8** for managing concert ticket reservations, seat sales, and buyer information. Originally developed for the **Maria Reina de La Paz** parish in Hartford, CT, this system provides a complete solution for event ticketing — from public seat selection to admin-side sales management.

---

## 📋 Table of Contents

- [About the Project](#about-the-project)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Database Models](#database-models)
- [Getting Started](#getting-started)
- [Environment Variables](#environment-variables)
- [Usage](#usage)
- [Routes Overview](#routes-overview)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 About the Project

This system was built to streamline the process of selling and managing concert tickets for a parish event. It supports both **in-person** and **online** ticket sales, automated ticket delivery via email (PDF format), an admin dashboard for managing users and sales, and a public-facing reservation page where attendees can choose and purchase their seats.

---

## ✨ Features

### 🌐 Public (Frontend)
- Interactive seat map for selecting available seats
- Online reservation form with buyer details (name, email, phone, address)
- Automatic PDF ticket generation and delivery via email
- Reservation lookup page to consult existing bookings

### 🔐 Admin Panel (Backend)
- Secure login system with role-based access control
- Dashboard with sales overview
- Individual and **bulk seat sales** management
- Edit and delete existing sales
- Payment method tracking (cash, online, etc.)
- Collections/payments tracking per sale
- User management (create, edit, delete system users)
- Downloadable PDF tickets per seat or per bulk order
- Email ticket delivery directly from the admin panel

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Framework** | Laravel 8 |
| **Language** | PHP 7.3 / 8.0 |
| **Frontend** | Blade Templates, Bootstrap 5, jQuery, DataTables |
| **Database** | MySQL |
| **PDF Generation** | barryvdh/laravel-dompdf |
| **Barcode Generation** | milon/barcode |
| **Currency Formatting** | cknow/laravel-money |
| **Avatars** | laravolt/avatar |
| **HTTP Client** | GuzzleHTTP |
| **Authentication** | Laravel Sanctum + Custom Session Auth |
| **Email** | Laravel Mail (SMTP) |

---

## 📁 Project Structure

```
concierto-master/
├── app/
│   ├── Console/             # Artisan commands
│   ├── Exceptions/          # Error handling
│   ├── Http/
│   │   ├── Controllers/     # Application logic
│   │   │   ├── CollectionController.php   # Payment collections
│   │   │   ├── SeatController.php         # Ticket download & email
│   │   │   ├── SeatSoldController.php     # Seat sales (single & bulk)
│   │   │   └── UserController.php         # Auth & user management
│   │   ├── Middleware/      # Admin auth, CSRF, etc.
│   ├── Models/
│   │   ├── Buyer.php        # Buyer information
│   │   ├── Collection.php   # Payment collections
│   │   ├── Seat.php         # Seat inventory
│   │   ├── SeatSold.php     # Sold seat records
│   │   └── User.php         # System users
│   └── Policies/            # Authorization policies
├── config/                  # App configuration files
├── database/
│   ├── factories/           # Test data factories
│   ├── migrations/          # Database schema
│   └── seeders/             # Initial data seeders
├── public/
│   ├── assets/              # CSS, JS, images, fonts
│   └── css-reservations/    # Frontend reservation styles
├── resources/
│   ├── views/
│   │   ├── dist/            # Admin panel views
│   │   ├── frontend/        # Public-facing views & PDF templates
│   │   └── principal/       # Login page
│   └── lang/                # Language files
├── routes/
│   ├── web.php              # Web routes
│   └── api.php              # API routes
├── storage/
│   └── fonts/               # Custom fonts for PDF generation
└── tests/                   # Feature and unit tests
```

---

## 🗄️ Database Models

| Table | Description |
|---|---|
| `seats` | Seat inventory with price, location, and sold status |
| `seat_sold` | Records of sold seats linked to buyers and sellers |
| `buyer` | Buyer contact information (name, email, phone, address) |
| `users_gmos` | System users (admin, sellers) with role assignments |
| `roles_gmos` | User roles (e.g., Admin, Seller) |
| `collections` | Payment collection records linked to sales |

---

## 🚀 Getting Started

### Prerequisites

- PHP >= 7.3
- Composer
- MySQL
- Node.js & npm (for asset compilation)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/concierto-master.git
   cd concierto-master
   ```

2. **Install PHP dependencies**
   ```bash
   composer install
   ```

3. **Install Node dependencies**
   ```bash
   npm install
   npm run dev
   ```

4. **Set up your environment file**
   ```bash
   cp .env.example .env
   php artisan key:generate
   ```

5. **Configure your database** in `.env` (see [Environment Variables](#environment-variables))

6. **Run database migrations**
   ```bash
   php artisan migrate
   ```

7. **Start the development server**
   ```bash
   php artisan serve
   ```

8. Open your browser at `http://localhost:8000`

---

## ⚙️ Environment Variables

Copy `.env.example` to `.env` and fill in the following key variables:

```env
APP_NAME=Laravel
APP_ENV=local
APP_URL=http://localhost

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_database_name
DB_USERNAME=your_db_user
DB_PASSWORD=your_db_password

MAIL_MAILER=smtp
MAIL_HOST=your_smtp_host
MAIL_PORT=587
MAIL_USERNAME=your_email@example.com
MAIL_PASSWORD=your_email_password
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=your_email@example.com
MAIL_FROM_NAME="${APP_NAME}"
```

> ⚠️ **Never commit your `.env` file to version control.** It is already listed in `.gitignore`.

---

## 📖 Usage

### Public Reservation Page
Navigate to `/` to access the interactive seat map. Users can:
- Browse available seats
- Select one or multiple seats
- Fill in buyer information
- Complete their reservation and receive their ticket(s) by email

### Consultation Page
Navigate to `/consult-reservation` to look up an existing reservation using buyer details.

### Admin Login
Navigate to `/form-login` to access the admin panel. Once logged in, roles determine access:
- **Admin** → Full dashboard, user management, sales overview, collections
- **Seller** → Sales page only

---

## 🗺️ Routes Overview

| Method | URL | Description |
|---|---|---|
| GET | `/` | Public reservation page |
| GET | `/consult-reservation` | Look up a reservation |
| GET | `/form-login` | Admin login page |
| POST | `/system/login` | Process login |
| POST | `/system/masive-sell-seats` | Bulk seat sale |
| GET | `/system/download-ticket/{id}` | Download ticket as PDF |
| GET | `/system` | Admin dashboard *(auth required)* |
| GET | `/system/sales` | Sales management *(auth required)* |
| GET | `/system/users` | User management *(auth required)* |
| POST | `/system/sell-seats` | Single seat sale *(auth required)* |
| POST | `/system/create-user` | Create a new system user *(auth required)* |
| GET | `/system/collect-money` | Collections overview *(auth required)* |
| GET | `/system/logout` | Logout *(auth required)* |

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "Add some feature"`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

---

## 📄 License

This project is open-sourced under the [MIT License](https://opensource.org/licenses/MIT).

---

> Built with ❤️ using [Laravel](https://laravel.com)
