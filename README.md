# UniSpace - IT Workspace Booking System

A comprehensive web-based workspace booking system for IT environments, built with PHP, MySQL, HTML, CSS, and JavaScript.

## 🚀 Live Demo

**[View Live Demo](https://your-demo-url.com)** *(Coming Soon)*

### Demo Credentials
- **Admin Login**: admin@gmail.com / Admin@123
- **User Registration**: Create your own account or use existing test data

## Features

### User Features
- **User Registration & Login** - Secure account creation and authentication
- **Seat Selection Interface** - Interactive seat grid with real-time availability
- **One Seat Per User** - Restriction to prevent multiple bookings
- **Booking Status Tracking** - View booking status (Pending/Approved/Rejected)
- **QR Code Generation** - Get QR codes for approved bookings
- **User Profile Management** - View and manage personal information

### Admin Features
- **Admin Dashboard** - Comprehensive booking management interface
- **Booking Approval System** - Approve/reject user booking requests
- **User Management** - Edit user details when incorrect information is entered
- **Bulk Actions** - Approve/reject multiple bookings at once
- **Data Export** - Export booking data to CSV
- **Real-time Updates** - Live booking status management

## Technology Stack

- **Backend**: PHP 7.4+
- **Database**: MySQL 5.7+
- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Libraries**: QR Code generation library
- **Server**: Apache (XAMPP recommended for development)

## Installation

### Prerequisites
- XAMPP (or similar PHP/MySQL environment)
- Web browser
- Git (for cloning)

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/UniSpace.git
   cd UniSpace
   ```

2. **Move to web directory**
   ```bash
   # For XAMPP
   cp -r . /Applications/XAMPP/xamppfiles/htdocs/UniSpace/
   ```

3. **Database Setup**
   - Start Apache and MySQL in XAMPP
   - Open phpMyAdmin (http://localhost/phpmyadmin)
   - Create a new database named `unispace`
   - Import the `database.sql` file

4. **Configure Database Connection**
   - Open `includes/db.php`
   - Update database credentials if needed:
     ```php
     $servername = "localhost";
     $username = "root";
     $password = "";
     $dbname = "unispace";
     ```

5. **Access the Application**
   - Visit: `http://localhost/UniSpace/`

## Usage

### For Regular Users
1. **Register** a new account or **login** with existing credentials
2. **Select an available seat** from the interactive grid
3. **Click "Book Now"** to submit your booking request
4. **Check status** on the status page
5. **Download QR code** once booking is approved

### For Administrators
1. **Login** with admin credentials:
   - Email: `admin@gmail.com`
   - Password: `Admin@123`
2. **View all bookings** in the admin dashboard
3. **Approve/reject** individual bookings
4. **Edit user details** if incorrect information was entered
5. **Export data** for reporting purposes

## Project Structure

```
UniSpace/
├── css/                    # Stylesheets
│   ├── admin.css          # Admin panel styles
│   ├── booking.css        # Booking page styles
│   ├── style.css          # Login/signup styles
│   └── success.css        # Success page styles
├── images/                # Static images
│   ├── background.png     # Login background
│   └── logo-main.png      # Application logo
├── includes/              # PHP backend files
│   ├── admin_*.php        # Admin functionality
│   ├── book_seats.php     # Booking logic
│   ├── db.php             # Database connection
│   ├── login.php          # Authentication
│   └── signup.php         # User registration
├── js/                    # JavaScript files
│   ├── admin.js           # Admin panel functionality
│   ├── booking.js         # Seat selection logic
│   └── qrcode.min.js      # QR code generation
├── admin.php              # Admin dashboard
├── booking.php            # Seat selection page
├── database.sql           # Database schema
├── index.php              # Login page
├── profile.php            # User profile page
├── signup.php             # Registration page
├── status.php             # Booking status page
└── README.md              # This file
```

## Database Schema

### Users Table
- `id` (Primary Key)
- `first_name`, `last_name`
- `email` (Unique)
- `registration_number` (Unique)
- `phone_number`
- `password` (Hashed)
- `created_at`

### Bookings Table
- `id` (Primary Key)
- `user_id` (Foreign Key)
- `seat_number`
- `booking_time`
- `status` (pending/approved/rejected)
- `created_at`

## Security Features

- **Password Hashing** - Secure password storage with PHP's password_hash()
- **SQL Injection Prevention** - Prepared statements for all database queries
- **Session Management** - Secure user authentication
- **Input Validation** - Server-side validation for all forms
- **Admin Authentication** - Separate admin role management

## 🌐 Deployment

### Free Hosting Options

1. **InfinityFree** (Recommended)
   - Free PHP/MySQL hosting
   - Custom domains supported
   - [Setup Guide](HOSTING.md)

2. **000WebHost**
   - Easy setup and deployment
   - Free SSL certificates

3. **GitHub Codespaces**
   - Development environment
   - Great for testing and demos

### Quick Deploy Steps

1. Choose a hosting provider (see [HOSTING.md](HOSTING.md) for detailed instructions)
2. Upload all project files
3. Create MySQL database and import `unispace_complete.sql`
4. Update database credentials in `includes/db.php`
5. Access your live application!

For detailed deployment instructions, see [HOSTING.md](HOSTING.md).

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For support, create an issue in the GitHub repository.

---

**⭐ Star this repository if you found it helpful!**

   - Option 2: Using MySQL Command Line
     - Open a terminal or command prompt
     - Navigate to your XAMPP MySQL bin directory
     - Run the following command:
       ```
       mysql -u root -p < /path/to/UniSpace/database.sql
       ```
     - If prompted for a password, press Enter (default XAMPP MySQL has no password)

3. **Verify Database Setup**
   - In phpMyAdmin, you should now see the `unispace_db` database
   - The database should contain two tables: `users` and `bookings`
   - The `users` table should contain sample user data

### Database Structure

#### Users Table
- `id`: Auto-incremented unique identifier
- `first_name`: User's first name
- `last_name`: User's last name
- `registration_number`: Unique registration number (e.g., student ID)
- `email`: Unique email address
- `phone_number`: Contact phone number
- `password`: Hashed password
- `created_at`: Timestamp of account creation

#### Bookings Table
- `id`: Auto-incremented unique identifier
- `user_id`: Foreign key referencing the users table
- `seat_number`: The workspace seat number being reserved
- `booking_time`: Timestamp of when the booking was made

### Sample Data

The database includes sample user data with the following credentials:

1. **John Doe**
   - Email: john.doe@example.com
   - Registration: REG001

2. **Jane Smith**
   - Email: jane.smith@example.com
   - Registration: REG002

3. **Alice Johnson**
   - Email: alice.johnson@example.com
   - Registration: REG003

### Troubleshooting

- If you encounter a connection error, ensure that:
  - XAMPP MySQL service is running
  - Database credentials in `includes/db.php` match your MySQL setup
  - The `unispace_db` database exists

- If you encounter issues with the signup or login process:
  - Check that the `users` table structure matches the expected fields
  - Verify that the database connection in `includes/db.php` is correct