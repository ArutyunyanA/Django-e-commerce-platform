# eCommerce Platform with Asynchronous Features in Django

This project is an advanced eCommerce platform built with Django. It features asynchronous processing with Celery and RabbitMQ, real-time product recommendations powered by Redis, a coupon discount system, Stripe payment integration, and a user dashboard to manage orders and download invoices. Designed for efficient online retail, this project offers a robust and scalable solution for eCommerce.

## Features

- **Asynchronous Task Processing**: Utilizes Celery and RabbitMQ to handle background tasks, ensuring smooth user experience and efficient task management.
- **Product Recommendations**: Integrated with Redis to deliver real-time product recommendations based on user interactions and purchase history.
- **Coupon System**: Allows for customizable discount codes to enhance customer engagement and increase conversions.
- **User Authentication**: Secure user registration and login with dedicated personal dashboards for tracking orders and downloading PDF invoices.
- **Stripe Payment Gateway**: Seamless integration with Stripe to manage online payments securely and efficiently.
- **Order Management**: Allows users to view order history, track current orders, and download invoices for completed purchases.
- **PDF Invoices**: Automatically generates downloadable PDF invoices for users once an order is marked as paid.

## Technology Stack

- **Backend**: Django, Django REST Framework
- **Asynchronous Processing**: Celery, RabbitMQ
- **Database**: PostgreSQL
- **Caching and Recommendations**: Redis
- **Payment Integration**: Stripe API
- **Frontend**: HTML, CSS, JavaScript (enhanced with modern design elements such as glassmorphism for a visually appealing interface)

## Setup and Installation

To set up this project on your local environment, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name

	2.	Create a virtual environment:

python3 -m venv venv
source venv/bin/activate


	3.	Install dependencies:

pip install -r requirements.txt


	4.	Set up environment variables:
Create a .env file in the root directory and configure the following variables:

SECRET_KEY=your_secret_key
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key


	5.	Configure RabbitMQ and Redis:
Ensure RabbitMQ and Redis are running on your system. You can install them via Homebrew on macOS:

brew install rabbitmq redis
brew services start rabbitmq
brew services start redis


	6.	Apply migrations:

python manage.py migrate


	7.	Create a superuser:

python manage.py createsuperuser


	8.	Run the development server:

python manage.py runserver


	9.	Start Celery Worker:

celery -A your_project_name worker --loglevel=info


	10.	Start Celery Beat Scheduler (for scheduled tasks):

celery -A your_project_name beat --loglevel=info


	11.	Generate requirements.txt (if not already created):

pip freeze > requirements.txt



Usage

	•	User Dashboard: After registration, users can access their dashboard to view order history and download PDF invoices for completed orders.
	•	Order Creation and Checkout: Only authenticated users can proceed with checkout. Orders are created through a secure payment process integrated with Stripe.
	•	Coupon Management: Users can apply discount codes at checkout.
	•	Real-Time Product Recommendations: Recommendations are updated based on user behavior, providing a personalized shopping experience.

Screenshots

Include screenshots of your main pages here to demonstrate the UI and key features.

Contributing

If you’d like to contribute to this project, please fork the repository and create a pull request.

License

This project is licensed under the MIT License.

