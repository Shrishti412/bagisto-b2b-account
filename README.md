🏢 Bagisto Users & Roles Module
Bagisto Version
PHP Version

📖 Introduction
The Bagisto Users & Roles Module enhances a standard Bagisto storefront by adding advanced B2B account management capabilities. It enables registered business customers to create sub-users (employees or staff) within their main account and assign them detailed roles and permissions through a dynamic, nested access-control tree.

The module is completely decoupled from the Bagisto core, ensuring smooth upgrades while preserving the modern Tailwind CSS design of Bagisto 2.x.

✨ Features
Company Users Management: Allows customers to create, update, and manage multiple sub-users under their company account.
Roles & Permissions: Define custom roles with fine-grained access control using an interactive, nested permission structure.
Seamless UI Integration: Adds native-style menu items directly into the Bagisto Customer Profile sidebar.
Tailwind & Blade Components: Built using Bagisto’s native UI components for a consistent, responsive frontend experience.
Isolated Architecture: Utilizes Konekt Concord contracts and proxies to ensure zero modifications to core files.

⚙️ Requirements
Before installing the module, make sure your environment meets the following requirements:

Bagisto: v2.3.x or higher
PHP: ^8.2 or higher
Composer: v2.0 or higher

🚀 Installation Guide
Follow the steps below to install the module in your existing Bagisto setup.

Step 1: Link the Repository
Open the composer.json file in your Bagisto root directory. Add the following repository entry inside the "repositories" array:

"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/YOUR-USERNAME/bagisto-b2b-account"
    }
]

(Replace YOUR-USERNAME with your actual GitHub username.)

Step 2: Require the Package
Run the following command in your terminal to install the module:

composer require acme/b2b-account:dev-main

Step 3: Register the Service Provider
Open bootstrap/providers.php and add the Service Provider class at the end of the returned array:

return [
    // ... other providers
    Acme\B2BAccount\Providers\B2BAccountServiceProvider::class,
];

Step 4: Run the Installation Command
Execute the custom Artisan command provided by the package. This will run the database migrations and clear the application cache:

php artisan b2b-account:install

🎉 That’s it!
Log in to your Bagisto storefront as a customer. Go to your profile section, and you will find the new "Company Users" and "Roles & Permissions" tabs added to your sidebar.

🛠️ Usage
Create a Role: Navigate to Roles & Permissions → Add Role. Select either "All Access" or choose specific permissions from the custom access tree.

Create a User: Go to Company Users → Add User. Enter the employee’s details, assign the appropriate role, and save. The system will automatically generate a secure password for the user.
