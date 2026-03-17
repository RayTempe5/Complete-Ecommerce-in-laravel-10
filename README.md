[![github-follow](https://img.shields.io/github/followers/Prajwal100?label=Follow&logoColor=purple&style=social)](https://github.com/Prajwal100)
[![GitHub stars](https://img.shields.io/github/stars/Prajwal100/Complete-Ecommerce-in-laravel-10.svg?style=social)](https://github.com/Prajwal100/Complete-Ecommerce-in-laravel-10/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/Prajwal100/Complete-Ecommerce-in-laravel-10.svg)](https://github.com/Prajwal100/Complete-Ecommerce-in-laravel-10/network)
[![license](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://choosealicense.com/licenses/mit/)
[![Buy Me A Coffee](https://img.shields.io/badge/Support-Buy%20Me%20A%20Coffee-yellow?style=flat-square&logo=buy-me-a-coffee)](https://buymeacoffee.com/prajwalrai/support-my-work-complete-laravel-e-commerce-project)

# 🚀 Complete E-commerce Website in Laravel 10

A full-fledged **eCommerce solution** built on **Laravel 10**, featuring a modern UI, powerful admin panel, seamless payment integration, and a user-friendly shopping experience.

## 📋 Requirements

- PHP >= 8.1
- Composer
- Node.js & NPM
- MySQL/PostgreSQL
- Laravel 10.x

## 🌟 Features

### 🔹 **Frontend**

- ⚡ **Progressive Web App (PWA) support**
- 🎨 **Modern & responsive design**
- 🛒 **Shopping cart, wishlist, and order tracking**
- 🔎 **SEO-friendly URLs & metadata**
- 💳 **Integrated PayPal payment gateway**
- 📢 **Social login (Google, Facebook, Github)**
- 💬 **Multi-level comments & reviews**

### 🔹 **Admin Dashboard**

- 🎛️ **Role management**
- 📊 **Advanced analytics & reporting**
- 🛍️ **Product & order management**
- 🔔 **Real-time notifications & messaging**
- 🏷️ **Coupon & discount system**
- 📰 **Blog & category management**
- 📸 **Media & banner manager**

### 🔹 **User Dashboard**

- 📦 **Order history & tracking**
- 💬 **Review & comment system**
- 🔧 **Profile customization**

---

## 🛠️ Installation Guide

### 🔹 **Step 1: Clone the Repository**

```sh
git clone https://github.com/Prajwal100/Complete-Ecommerce-in-laravel-10.git
cd Complete-Ecommerce-in-laravel-10
```

### 🔹 **Step 2: Install Dependencies**

```sh
composer install
npm install
```

### 🔹 **Step 3: Environment Setup**

```sh
cp .env.example .env
php artisan key:generate
```

Update `.env` with your database credentials, PayPal settings, and social login configurations.

### 🔹 **Step 4: Database Configuration**

```sh
php artisan migrate --seed
```

**Note:** The seeder will create the admin user. Alternatively, you can import `database/e-shop.sql` manually.

### 🔹 **Step 5: Setup Storage**

```sh
php artisan storage:link
```

### 🔹 **Step 6: Run the Application**

```sh
php artisan serve
```

🔗 Open `http://localhost:8000`

### **Admin Login Credentials:**

📧 **Email:** `admin@gmail.com`  
🔑 **Password:** `1111`

---

## 🤖 Powered by NepVox AI - Complete AI Solution

🚀 **[NepVox AI](https://nepvox.com/)** is a cutting-edge **online AI application** that provides three powerful AI capabilities in one platform:

### 🎙️ **Text-to-Speech (TTS)**
- Convert any text into natural, human-like voice
- Multiple languages and voice options
- Perfect for videos, accessibility, podcasts, and e-learning

### 🗣️ **Speech-to-Text (STT)**
- Transcribe audio and speech to text with high accuracy
- Real-time transcription support
- Ideal for meetings, interviews, and voice notes

### 🎨 **Text-to-Image (TTI)**
- Generate stunning images from text descriptions
- AI-powered image creation
- Creative design and content generation

### ✨ **Key Features:**
- ✅ **All-in-One Platform**: TTS, STT, and TTI in a single application
- ✅ **Multiple Languages**: Support for various languages and voices
- ✅ **API Integration**: Simple API for seamless business integration
- ✅ **High Quality**: Professional-grade AI technology
- ✅ **User-Friendly**: Intuitive interface for all skill levels

🎯 **Perfect for:** Content creators, developers, businesses, educators, and anyone looking to leverage AI technology.

🔗 **Try it now:** [Visit NepVox AI](https://nepvox.com/) | [Documentation](https://nepvox.com/)

---

## 📷 Screenshots

### **Admin Panel**

![Admin](https://user-images.githubusercontent.com/29488275/90719413-13b82200-e2d4-11ea-8ca0-f0e5551c4c9d.png)

### **Product Management**

![Products](https://user-images.githubusercontent.com/29488275/90719534-61348f00-e2d4-11ea-8a81-409daee0ad94.png)

### **User Dashboard**

![User Dashboard](https://user-images.githubusercontent.com/29488275/90719563-7a3d4000-e2d4-11ea-9e6a-56caac13b146.png)

---

## 📩 Contact Me

💼 Need a **Full Stack Laravel Developer**? Let's work together!

📧 **Email:** Prajwal.iar@gmail.com
📲 **WhatsApp:** +977-9818441226

🔗 **[Hire Me on Upwork](https://www.upwork.com/freelancers/~01210bb2575a8c05a9)**

### ☕ Support My Work

If you find this project helpful, consider [buying me a coffee](https://buymeacoffee.com/prajwalrai/support-my-work-complete-laravel-e-commerce-project). Your support helps maintain and improve this project! 🚀

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📜 License

🔹 This project is **MIT Licensed** – Feel free to use & modify!

⭐ **If you find this project helpful, don't forget to star it!** ⭐
Implementation Notes

Task 1 - Add order product list on order detail
Added an ORDER PRODUCTS section to resources/views/user/order/show.blade.php that displays a table of all products in the order (photo, name, price, quantity, subtotal). Data is loaded via the existing cart_info relationship on the Order model.

Task 2 - Order detail should not change if product is edited/deleted
Problem: The carts table only stored product_id with onDelete CASCADE. If a product was deleted, the cart row was also deleted. If edited, the order detail would reflect the new data.

Solution: Added a product snapshot to the carts table:
- Migration: added product_title, product_price, product_photo columns and changed foreign key to onDelete SET NULL
- OrderController store: saves snapshot data when order is placed
- Cart model: added snapshot columns to fillable
- View: reads from snapshot columns instead of live product relation

Suggestions

1. Authorization on order detail - Any logged-in user can access /user/order/show/id by guessing the ID. Add ownership check using Order where user_id and findOrFail.

2. Database transactions - Checkout process should be wrapped in DB transaction to ensure atomicity.

3. N+1 query problem - Several views load relationships inside loops. Use eager loading with with() in controllers.

4. Form Request validation - Move validation logic into dedicated FormRequest classes for cleaner code.

5. Order status email notification - Send email to user when order status changes.

6. Test coverage - No tests exist. Add feature tests for checkout flow and order detail at minimum.

7. Soft delete on products - Use SoftDeletes on the Product model so deleted products are still accessible for historical orders.