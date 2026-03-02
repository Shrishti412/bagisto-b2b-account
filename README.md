# 🏢 Bagisto Users & Roles Module

Enhance your Bagisto storefront with advanced B2B account management capabilities. This module enables business customers to create sub-users (employees/staff) within their company account and assign them custom roles with detailed permissions — all without modifying core files.

---

## 📖 Introduction

The **Bagisto Users & Roles Module** transforms a standard Bagisto store into a structured B2B platform.

It allows:

- Company-level employee management  
- Custom role creation  
- Granular permission assignment  
- Dynamic nested access-control tree  

The module is fully decoupled from the Bagisto core, ensuring safe upgrades and seamless compatibility with Bagisto 2.x (Tailwind CSS-based UI).

---

## ✨ Features

### ✅ Company Users Management
- Add multiple employees under a company account  
- Edit and manage sub-users anytime  
- Assign roles for controlled access  

### ✅ Roles & Permissions
- Create unlimited custom roles  
- Choose **All Access** or specific permissions  
- Interactive nested permission tree  

### ✅ Seamless UI Integration
- Native-looking sidebar menu integration  
- Fully responsive frontend  
- Consistent Tailwind-based design  

### ✅ Isolated Architecture
- Built using Konekt Concord contracts & proxies  
- No core file modifications  
- Upgrade-safe implementation  

---

## ⚙️ Requirements

Ensure your environment meets the following:

- **Bagisto:** v2.3.x or higher  
- **PHP:** ^8.2 or higher  
- **Composer:** v2.0 or higher  

---

## 🚀 Installation Guide

Follow these steps to install the module into your Bagisto application.

---

### Step 1: Add Repository

Open your main `composer.json` file and add the repository inside the `"repositories"` array:

```json
"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/YOUR-USERNAME/bagisto-b2b-account"
    }
]
```

> Replace `YOUR-USERNAME` with your actual GitHub username.

---

### Step 2: Require the Package

Run the following command from your Bagisto root directory:

```bash
composer require acme/b2b-account:dev-main
```

---

### Step 3: Register the Service Provider

Open:

```
bootstrap/providers.php
```

Add the Service Provider to the returned array:

```php
return [
    // ... other providers
    Acme\B2BAccount\Providers\B2BAccountServiceProvider::class,
];
```

---

### Step 4: Run Installation Command

Execute the custom Artisan command:

```bash
php artisan b2b-account:install
```

This command will:

- Run database migrations  
- Publish required resources  
- Clear application cache  

---

## 🎉 Installation Complete

Log in to your Bagisto storefront as a customer and navigate to your profile section.

You will now see:

- **Company Users**
- **Roles & Permissions**

added to the sidebar.

---

## 🛠️ Usage Guide

### 🔹 Create a Role

1. Navigate to **Roles & Permissions**  
2. Click **Add Role**  
3. Select:
   - **All Access**, or  
   - Choose specific permissions from the access tree  
4. Save the role  

---

### 🔹 Create a Company User

1. Navigate to **Company Users**  
2. Click **Add User**  
3. Enter employee details  
4. Assign a role  
5. Save  

The system automatically generates a secure password for the user.

---

## 📦 Module Architecture

- Modular package structure  
- Concord-based contracts & proxies  
- Blade + Tailwind UI components  
- Fully decoupled from Bagisto core  

---

## 🧩 Troubleshooting

If you encounter issues:

Run:

```bash
composer dump-autoload
```

Then clear cache:

```bash
php artisan optimize:clear
```

Also verify your PHP and Bagisto versions meet the requirements.

---

## 📄 License

This module is open-source and available under the MIT License.
