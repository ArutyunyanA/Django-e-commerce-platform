# eCommerce Platform with Asynchronous Features in Django

This project is an advanced eCommerce platform built with Django. It features asynchronous processing with Celery and RabbitMQ, real-time product recommendations powered by Redis, a coupon discount system, Stripe payment integration, and a user dashboard to manage orders and download invoices.

## Features

- **Asynchronous Task Processing**: Utilizes Celery and RabbitMQ for background task management.
- **Product Recommendations**: Real-time product recommendations powered by Redis.
- **Coupon System**: Discount code integration for order management.
- **User Authentication**: User registration and login system with a personal dashboard.
- **Stripe Payment Integration**: Secure Stripe payments for order processing.
- **Order Management**: Track orders and download invoices for completed purchases.
- **PDF Invoices**: Automatically generated PDF invoices for paid orders.

## Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    ```

2. **Create a virtual environment**:
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Create `.env` file**:
    Create a `.env` file in the root directory with the following environment variables:
    ```bash
    SECRET_KEY=your_secret_key
    STRIPE_SECRET_KEY=your_stripe_secret_key
    STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
    ```

5. **Configure RabbitMQ and Redis**:
    Ensure RabbitMQ and Redis are running on your system. You can install them via Homebrew on macOS:
    ```bash
    brew install rabbitmq redis
    brew services start rabbitmq
    brew services start redis
    ```

6. **Apply migrations**:
    ```bash
    python manage.py migrate
    ```

7. **Create a superuser**:
    ```bash
    python manage.py createsuperuser
    ```

8. **Run the development server**:
    ```bash
    python manage.py runserver
    ```

9. **Start Celery Worker**:
    ```bash
    celery -A your_project_name worker --loglevel=info
    ```

10. **Start Celery Beat Scheduler** (for scheduled tasks):
    ```bash
    celery -A your_project_name beat --loglevel=info
    ```

11. **Generate `requirements.txt`** (if not already created):
    ```bash
    pip freeze > requirements.txt
    ```

## Usage

- **User Dashboard**: After registration, users can access their dashboard to view order history and download PDF invoices for completed orders.
- **Order Creation and Checkout**: Only authenticated users can proceed with checkout. Orders are created through a secure payment process integrated with Stripe.
- **Coupon Management**: Users can apply discount codes at checkout.
- **Real-Time Product Recommendations**: Recommendations are updated based on user behavior, providing a personalized shopping experience.

## Project Structure

- `accounts/` - Contains the authentication app with forms for login, logout, password change/reset, and user registration.
- `orders/` - Order-related models and views for order processing and invoice generation.
- `products/` - Models and views for handling products, categories, and recommendations.
- `static/` - Static files (CSS, JS) for styling the pages.
- `templates/` - HTML templates for rendering views.
- `settings.py` - Configuration for the project, including Stripe integration, Celery, and Redis settings.

## Security

- **HTTPS Support**: Ensure secure connections with HTTPS (use SSL certificates in production).
- **Password management**: Includes secure user registration, login, and password reset functionality.
- **CSRF Protection**: All forms include CSRF protection to prevent cross-site request forgery.

## Requirements

- Python 3.10+
- Django 4.x
- Celery
- RabbitMQ
- Redis
- Stripe API

## Contributing

If you’d like to contribute to this project, feel free to fork the repository and submit a pull request.

## License

This project is licensed under the MIT License.
