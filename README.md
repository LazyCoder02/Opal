# Opal Event Management System

---

Welcome to Opal! This is a simple and intuitive event management system that allows users to register, log in, create, view, edit, and delete events.

## Features

- **User Registration**: Sign up to create an account.
- **User Login**: Log in to access your account.
- **Event Management**: Create, view, edit, and delete your events.
- **User Authentication**: Secure login and registration system.

## File Organization

### Main Files

- `index.php`: Home page.
- `register.php`: Registration form and handling.
- `login.php`: Login form and handling.
- `logout.php`: Logout handling.
- `displayEvents.php`: View events created by users.
- `eventManagement.php`: Manage your events.
- `addEvent.php`: Add new events.
- `editEvent.php`: Edit existing events.
- `deleteEvent.php`: Delete events.
- `updateAttendance.php`: Update event attendance.
- `registerHandler.php`: Handles registration logic.
- `loginHandler.php`: Handles login logic.
- `config.php`: Configuration file for database connection.

### Additional Files

- `classes/`: Directory for class files.
  - `Database.php`: Database connection class.
  - `User.php`: User class for handling user data.
  - `Event.php`: Event class for managing events.
  - `Session.php`: Session management class.
- `pictures/`: Directory for storing event images.

## Getting Started

### Prerequisites

- A web server (e.g., Apache)
- PHP 7.4 or higher
- MySQL or MariaDB database

---

### Installation

1. **Download the Project Files:**
   Extract the project files from the provided archive to your web server's root directory (e.g., `htdocs` for XAMPP, `www` for WAMP, or `/var/www/html` for Linux servers).

2. **Configure the Database:**

   - Update the `config.php` file with your database credentials.
   - Import the provided SQL file to set up the database schema.

3. **Tables that need to be created:**

   - Users table, sql query:
     CREATE TABLE users (
     id INT AUTO_INCREMENT PRIMARY KEY,
     username VARCHAR(50) NOT NULL UNIQUE,
     email VARCHAR(100) NOT NULL UNIQUE,
     password VARCHAR(255) NOT NULL,
     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
     );

   - Events table:
     CREATE TABLE events (
     id INT AUTO_INCREMENT PRIMARY KEY,
     user_id INT NOT NULL,
     event_name VARCHAR(100) NOT NULL,
     description TEXT NOT NULL,
     date_and_time DATETIME NOT NULL,
     location VARCHAR(255) NOT NULL,
     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
     FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
     );

   - User_events table:
     CREATE TABLE user_events (
     user_id INT,
     event_id INT,
     PRIMARY KEY (user_id, event_id),
     FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
     FOREIGN KEY (event_id) REFERENCES events(id) ON DELETE CASCADE
     );

4. **Run the Project:**

   - Ensure your web server is running.
   - Ensure that the name of each column is consistent to the ones in the code.
   - Open your browser and navigate to `http://localhost/your-project-directory`.

   ***

### Usage

1. **Register**: Go to the registration page and create an account.

- Click the login button at the top right corner:

![](/pictures/SCT1.png)

- Then eiter click 'Register' on the navbar or 'click here' to register.

2. **Login**: Use your credentials to log in (can also be imaginary).
3. **Manage Events**: Create, view, edit, and delete events from your dashboard.

- Using this website is really simple and fun!
- Note that the events that you add are not visible in the displayEvents.php page.
  ![](/pictures/SCT2.png)
- See events will allow you to see other users' events.
- So add one or 2 different users and add random events and you can see the other events
- Toggle button was added for fun as a way for you to mark events you are interested in but it ia not functioning well:
  ![](/pictures/image.png)

## Contributing

Feel free to suggest improvements or report issues via teams (escrira_aehit@students.vizja.pl).

## Contact

If you have any questions or need further assistance, please contact me at escrira_aehit@students.vizja.pl on teams.

---

Enjoy using Opal Event Management System!
