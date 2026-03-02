# Bagisto Users & Roles Module

**Bagisto Version**  
**PHP Version**

---

## Introduction

The Bagisto Users & Roles Module enhances a standard Bagisto storefront by adding structured B2B account management capabilities. It enables registered business customers to create sub-users (employees or staff members) under their main account and assign them precise roles and permissions through a dynamic, nested access-control system.

The module is completely decoupled from the Bagisto core, ensuring safe upgrades while preserving the modern Tailwind CSS design used in Bagisto 2.x.

---

## Features

### Company Users Management
Allows business customers to create, update, and manage multiple sub-users within their primary company account.

### Roles & Permissions
Create custom roles with fine-grained access control using an interactive, nested permissions tree.

### Seamless UI Integration
Adds native-style menu items directly into the Bagisto Customer Profile sidebar for a consistent user experience.

### Tailwind & Blade Components
Built entirely with Bagisto’s native Blade and Tailwind components to ensure a responsive and uniform frontend interface.

### Isolated Architecture
Implements Konekt Concord contracts and proxies to maintain complete separation from core files and guarantee upgrade safety.

---

## Requirements

Ensure your environment meets the following requirements before installation:

- **Bagisto:** v2.3.x or higher  
- **PHP:** ^8.2 or higher  
- **Composer:** v2.0 or higher  

---

## Installation Guide

Follow the steps below to install the module in your existing Bagisto application.

### Step 1: Link the Repository

Open the `composer.json` file located in your Bagisto root directory. Add the following entry to the `"repositories"` array:

```json
"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/YOUR-USERNAME/bagisto-b2b-account"
    }
]
```

Replace `YOUR-USERNAME` with your actual GitHub username.

---

### Step 2: Require the Package

Run the following command in your terminal from the Bagisto root directory:

```bash
composer require acme/b2b-account:dev-main
```

---

### Step 3: Register the Service Provider

Open the file:

```
bootstrap/providers.php
```

Add the following Service Provider to the end of the returned array:

```php
return [
    // ... other providers
    Acme\B2BAccount\Providers\B2BAccountServiceProvider::class,
];
```

---

### Step 4: Run the Installation Command

Execute the Artisan command provided by the package:

```bash
php artisan b2b-account:install
```

This command will automatically run the necessary database migrations and clear the application cache.

---

After completing these steps, log in to your Bagisto storefront as a customer and navigate to your profile section. You will find the new **"Company Users"** and **"Roles & Permissions"** tabs available in the sidebar.

---

## Usage

### Create a Role

Go to **Roles & Permissions → Add Role**.  
Select either **"All Access"** or manually choose specific permissions from the custom access-control tree.

### Create a User

Navigate to **Company Users → Add User**.  
Enter the employee’s information, assign the appropriate role, and save. A secure password will be automatically generated for the new user.
