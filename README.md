# Homteq

HomTeq - a database-driven retail web application for browsing, purchasing, and managing smart‑home products.

## Requirements
- PHP
- MySQL
- Web server (Apache via XAMPP)

## Quick setup
1. Copy the project into your web root (e.g. `C:\xampp\htdocs\homteq`).
2. Create a MySQL database and user.
3. Update database credentials in [db.php](db.php).
4. (Optional) Create the minimal schema below.

```sql
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(100) UNIQUE NOT NULL,
  password_hash VARCHAR(255) NOT NULL,
  email VARCHAR(255)
);

CREATE TABLE products (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  price DECIMAL(10,2) NOT NULL,
  image VARCHAR(255),
  description TEXT
);
```

## Run (local)
- With XAMPP: start Apache & MySQL, open `http://localhost/homteq/`
- With PHP built-in server (dev):

```powershell
cd C:\xampp\htdocs\homteq
php -S localhost:8000
```

## Important files
- `index.php` - landing / product list
- `signup.php`, `login.php`, `logout.php` - auth
- `basket.php`, `clearbasket.php`, `prodbuy.php` - cart & checkout
- `db.php` - DB connection (edit credentials here)
- `mystylesheet.css` and `images/` - assets

