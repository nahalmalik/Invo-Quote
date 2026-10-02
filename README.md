# InvoQuote

### Smart Invoice & Business Document Management System

InvoQuote is a centralized business document management system designed to simplify the creation, management, conversion, previewing, sharing, and downloading of essential business documents.

The system brings customers, products, and business documents into one unified platform, allowing businesses to manage their day-to-day documentation without relying on multiple disconnected tools.

InvoQuote supports multiple document types including:

* Invoices
* Quotations
* Purchase Orders
* Delivery Challans
* Notes

The application is designed to provide a consistent experience across **Web, Desktop, and Android** platforms.

---

## ✨ Features

### 👥 Customer Management

Manage your complete customer database from a single interface.

* Add new customers
* View customer details
* Edit customer information
* Delete customers
* Associate customers with business documents
* Quickly select customers while creating documents

---

### 📦 Product Management

Maintain a centralized product catalog.

* Add products
* Edit product information
* Delete products
* Manage product details and pricing
* Select products while creating documents
* Reuse product information across multiple documents

---

### 🧾 Invoice Management

Create and manage professional invoices.

* Create invoices
* Add customers and products
* Calculate item quantities and prices
* Manage invoice details
* Preview invoices
* Download invoices
* Share invoices
* Delete invoices
* Convert invoices into other supported document formats

---

### 📋 Quotation Management

Create professional quotations for customers.

* Create quotations
* Add customer information
* Add multiple products
* Manage quantities and pricing
* Preview quotations
* Download quotations
* Share quotations
* Delete quotations
* Convert quotations into other supported document types

---

### 🛒 Purchase Orders

Manage purchase orders from the same platform.

* Create purchase orders
* Add products and quantities
* Manage supplier/order information
* Preview purchase orders
* Download documents
* Share documents
* Delete purchase orders
* Convert documents between supported formats

---

### 🚚 Delivery Challans

Create and manage delivery challans for dispatched goods.

* Create delivery challans
* Add customer information
* Add products and quantities
* Preview challans
* Download challans
* Share challans
* Delete challans
* Convert documents between supported formats

---

### 📝 Notes

Create and manage business notes alongside formal documents.

* Create notes
* Store business-related information
* Preview notes
* Download notes
* Share notes
* Delete notes

---

## 🔄 Document Conversion

One of the core features of InvoQuote is the ability to work with different business document types from one centralized system.

Documents can be converted between supported formats, reducing the need to recreate information manually.

For example:

```text
Quotation
    ↓
Invoice
    ↓
Delivery Challan
```

This workflow allows businesses to reuse existing customer and product information while moving through different stages of a transaction.

---

## 👁️ Preview, Download & Share

Every major business document can be managed directly from the application.

### Preview

View the generated document before downloading or sharing it.

### Download

Generate and download documents for offline use, printing, or record keeping.

### Share

Share generated documents directly through supported sharing mechanisms.

This makes the system suitable for businesses that frequently need to send quotations, invoices, purchase orders, or delivery documents to customers and suppliers.

---

# 🖥️ Multi-Platform Support

InvoQuote is designed as a multi-platform application.

### 🌐 Web

The core application can be accessed through a web environment.

### 🖥️ Desktop

The web application is packaged as a native-style desktop application using **Electron**.

The current Electron configuration generates a Windows installer using Electron Builder.

### 📱 Android

The application can also be packaged for Android using **Capacitor**.

The repository includes Capacitor Android integration and commands for syncing and opening the Android project.

This provides a shared application experience across:

```text
              InvoQuote
                  │
        ┌─────────┼─────────┐
        │         │         │
       Web      Desktop   Android
                 │
              Electron
                           │
                        Capacitor
```

---

# 🏗️ Application Architecture

InvoQuote follows a web-based application architecture with additional platform wrappers.

```text
                    ┌─────────────────────┐
                    │      InvoQuote      │
                    │  Business Document  │
                    │   Management System  │
                    └──────────┬──────────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
        ┌─────▼─────┐    ┌─────▼─────┐    ┌────▼──────┐
        │ Customers │    │  Products │    │ Documents │
        └───────────┘    └───────────┘    └─────┬─────┘
                                                │
                         ┌──────────────────────┼──────────────────────┐
                         │          │            │          │           │
                    Invoice    Quotation    Purchase    Delivery     Notes
                                               Order      Challan
```

The project also separates backend/API functionality from the frontend application through the repository's `api` directory. The repository includes database and PHP dependency configuration alongside the frontend and desktop/mobile packaging components.

---

# 🛠️ Technology Stack

## Frontend

* HTML5
* CSS3
* JavaScript
* Responsive UI
* Client-side document management interfaces

## Backend

* PHP
* REST-style API architecture
* MySQL

## Document Generation

* DOMPDF
* PDF document generation
* Dynamic business document templates

The repository includes `dompdf` font/cache resources and PHP Composer configuration for backend dependencies.

## Desktop

* Electron
* Electron Builder

The Electron application uses `main.js` as its main process entry point and Electron Builder for packaging.

## Mobile

* Capacitor
* Android

The project includes Capacitor Android dependencies and configuration for building the application for Android.

## Database

* MySQL

A database schema is included in the repository through `database.sql`.

---

# 📂 Project Structure

The repository is organized around the application, API, generated files, frontend scripts, storage, and platform packaging.

```text
DocuEngine/
│
├── api/
│   └── Backend/API components
│
├── downloads/
│   └── Generated/downloadable documents
│
├── js/
│   └── Frontend JavaScript
│
├── storage/
│   └── Document/PDF related storage
│
├── vendor/
│   └── PHP Composer dependencies
│
├── build/
│   └── Desktop application assets
│
├── database.sql
│   └── Database structure
│
├── index.html
│   └── Main application interface
│
├── main.js
│   └── Electron main process
│
├── package.json
│   └── Node/Electron/Capacitor configuration
│
├── composer.json
│   └── PHP dependency configuration
│
└── README.md
```

---

# 🚀 Getting Started

## Prerequisites

Before running the project, make sure the following are installed:

* PHP
* MySQL
* Composer
* Node.js
* npm
* Git

For Android development:

* Android Studio
* Android SDK
* Java/JDK

For desktop development:

* Node.js
* Electron dependencies

---

## 1. Clone the Repository

```bash
git clone https://github.com/nahalmalik/DocuEngine.git

cd DocuEngine
```

---

## 2. Install Node Dependencies

```bash
npm install
```

---

## 3. Install PHP Dependencies

```bash
composer install
```

---

## 4. Configure the Database

Create a MySQL database and import:

```text
database.sql
```

Then configure the database connection according to the backend configuration used by the application.

---

# 🖥️ Running the Desktop Application

The project includes an Electron wrapper.

Run the application in development mode:

```bash
npm start
```

The repository defines the following Electron-related scripts:

```bash
npm start
```

Start Electron.

```bash
npm run dist
```

Build the distributable desktop application.

```bash
npm run pack
```

Package the application without creating the final installer.

The current Electron Builder configuration targets Windows and generates an NSIS installer named:

```text
InvoQuote-Setup-${version}.exe
```

It also supports desktop and Start Menu shortcuts.

---

# 📱 Android Application

The application uses Capacitor to package the web application for Android.

Sync the project:

```bash
npm run sync
```

Open the Android project in Android Studio:

```bash
npm run android
```

The repository currently includes Capacitor Android and Capacitor core dependencies.

---

# 📄 Supported Documents

| Document         | Create | Preview | Download | Share | Delete | Convert |
| ---------------- | :----: | :-----: | :------: | :---: | :----: | :-----: |
| Invoice          |    ✅   |    ✅    |     ✅    |   ✅   |    ✅   |    ✅    |
| Quotation        |    ✅   |    ✅    |     ✅    |   ✅   |    ✅   |    ✅    |
| Purchase Order   |    ✅   |    ✅    |     ✅    |   ✅   |    ✅   |    ✅    |
| Delivery Challan |    ✅   |    ✅    |     ✅    |   ✅   |    ✅   |    ✅    |
| Notes            |    ✅   |    ✅    |     ✅    |   ✅   |    ✅   |    —    |

---

# 🎯 Use Cases

InvoQuote can be used by businesses and individuals who regularly create and manage business documentation.

Potential use cases include:

* Small businesses
* Retail businesses
* Wholesalers
* Distributors
* Freelancers
* Service providers
* Suppliers
* Trading businesses
* Startups
* Sales teams
* Office administration
* Purchase and inventory workflows

---

# 💡 Why InvoQuote?

Traditional business documentation often involves creating separate files for quotations, invoices, purchase orders, and delivery documents.

InvoQuote brings these workflows into one system.

Instead of repeatedly entering the same customer and product information, users can maintain centralized records and reuse them throughout their documentation workflow.

```text
Customers
     │
     ├──────────────┐
     │              │
Products        Documents
     │              │
     └──────┬───────┘
            │
      ┌─────▼─────┐
      │ InvoQuote │
      └─────┬─────┘
            │
     ┌──────┼──────┐
     │      │      │
  Preview Download Share
```

---

# 🔐 Data Management

The application maintains structured customer, product, and document information rather than treating every generated document as an isolated file.

This makes it possible to:

* Reuse customer information
* Reuse product information
* Generate documents from existing records
* Maintain consistent document data
* Convert documents without manually recreating all information

Database initialization is provided through the included `database.sql` file.

---

# 🧩 Key Modules

The application can be viewed as several interconnected modules:

### Customer Module

Responsible for maintaining customer records.

### Product Module

Responsible for maintaining product/catalog information.

### Document Module

Handles the creation and management of:

* Invoices
* Quotations
* Purchase Orders
* Delivery Challans
* Notes

### Document Generation Module

Responsible for generating printable/downloadable document outputs.

### Conversion Module

Allows information from an existing document to be reused when creating another supported document.

### Sharing Module

Provides document sharing functionality from the application.

### Platform Module

Allows the same application concept to be packaged for desktop and Android environments.

---

# 📦 Desktop Build Configuration

The desktop application is configured with the product name:

```text
InvoQuote
```

and application identifier:

```text
com.ibzi.invoquote
```

The Windows build uses NSIS and supports installation-directory selection as well as desktop and Start Menu shortcuts.

---

# 🗺️ Future Improvements

Potential future development areas include:

* User authentication and role-based access
* Business/company profiles
* Multiple company support
* Invoice numbering customization
* Tax and discount management
* Payment tracking
* Product stock management
* Supplier management
* Dashboard analytics
* Sales reports
* Purchase reports
* Customer statements
* Cloud synchronization
* Automated backups
* Email integration
* WhatsApp sharing
* Advanced PDF templates
* Custom company branding
* Multi-language support
* Dark mode
* Cloud deployment
* iOS support

---

# 🤝 Contributing

Contributions, suggestions, and improvements are welcome.

To contribute:

```bash
# Fork the repository

# Clone your fork
git clone https://github.com/nahalmalik/DocuEngine.git

# Create a feature branch
git checkout -b feature/your-feature

# Make your changes

# Commit your changes
git commit -m "Add your feature"

# Push your branch
git push origin feature/your-feature
```

Then open a Pull Request.

---

# 📜 License

This project currently uses the ISC license as specified in the project configuration.

Please review the repository license and dependency licenses before using or redistributing the software.

---

# 👨‍💻 Developer

Developed by **Nahal Malik**

Software Engineer & Full-Stack Developer

GitHub:
https://github.com/nahalmalik

---

# ⭐ Project

If you find InvoQuote useful or interesting, consider giving the repository a ⭐ on GitHub.

**Repository:**
https://github.com/nahalmalik/DocuEngine

---

## 📌 Project Summary

> **InvoQuote is a multi-platform business document management system that brings customers, products, invoices, quotations, purchase orders, delivery challans, and notes together in one centralized application. It allows users to create, preview, convert, download, share, and manage business documents across Web, Windows Desktop, and Android.**
