# Foodzilla Project Setup Guide

### Development Team Introduction

This website was developed by three programmers:
- **Nasrollahi**: Responsible for **Backend** of the **Admin Panel**
- **Amiri**: Responsible for **Backend** of the **Frontend Site**
- **Kimiya**: Responsible for **Frontend**

**Note:** The reason for having two backend developers is that one worked on the **Admin Panel**, and the other worked on the **Frontend Site**.

---

## Project Setup Steps

### 1. Create Folders and Copy Files
First, create two folders with the following names and copy the respective files into them:
- `adminpanel`
- `laravel`

### 2. Run Initial Commands
Then, open two separate terminals and execute the following commands in each.

#### In the first terminal:
```sh
cd ./adminpanel
composer install
```

#### In the second terminal:
```sh
cd ./laravel
composer install
```

### 3. Start Local Servers
#### In the `adminpanel` terminal:
```sh
php artisan serve --port=8001
```

#### In the `laravel` terminal:
```sh
php artisan serve
```

### 4. Database Setup and Migrations
In the `adminpanel` terminal, first navigate to the `adminpanel` directory and execute the following command:
```sh
cd ./adminpanel
php artisan migrate
```

### 5. Configure `.env` File
In the `.env` file of both projects, set the database name to be the same. Our team used `laravel_golden_down`, but you can change it. Just make sure **both projects connect to the same database.**

### 6. Create a Database in `phpMyAdmin`
By installing **XAMPP**, you can easily manage the database using `phpMyAdmin`:
1. Open `phpMyAdmin`.
2. Click on `New`.
3. Enter the database name and click `Create`.

### 7. Initial Database Setup for Admin Panel
#### 1. Create a user in the `users` table.
#### 2. Create roles in the `roles` table:
   - `admin`
   - `author`
   - `financial`
#### 3. Assign roles to users in the `role_user` table.

> **Note:** Each role has specific permissions. A user can have multiple roles.

### 8. Add Sample Products
To ensure that the `menu` and `singlepage` sections work correctly, add at least **4 to 5 products**.

### 9. Fix Admin Panel Login Issues
If you face login issues while accessing the **Admin Panel**, there are two solutions:
1. **Manually edit the email and password of a user in the `users` table**.
2. **Forcefully disable the login route:**
   - Navigate to the `adminpanel/cache` directory.
   - Open the `app.php` file.
   - **Comment out** the line containing `/login` (using `//`).

---

## Website Setup (Frontend Site)

### 1. Disable Mandatory User Login
If you don’t want users to be forced to log in, edit the following file:

```sh
bootstrap/app.php
```

Comment out or remove the following line:
```php
$middleware->redirectGuestsTo('/login');
```

### 2. Initial Database Setup in `phpMyAdmin`
For the website to display correctly, create the following items:
- **Slider**
- **Footer**
- **About Us**

### 3. Configure OTP and Payment Gateway
- **Testing OTP:** The sent OTP is displayed in the `users` table.
- **Connecting to a Payment Gateway:**
  - Since the project runs on `localhost`, some payment gateways may not work locally.
  - To enable online payments, deploy the website on a hosting server.
  - Documentation for payment gateway configuration is usually available on the provider's website. Contact their support if needed.

### 4. Import Cities and Provinces Data
For the profile section to function correctly, import the following files into the database:
- `cities`
- `provinces`

---

## Contact the Development Team
- **(adminpanel) Backend Support & Database Configuration:** `mjn265813@gmail.com`
- **Frontend Support:** `mjn268513@gmail.com`
- **Backend Support for User-Facing Sections:** `mjef0099@gmail.com`

---

## Project Name: Foodzilla

