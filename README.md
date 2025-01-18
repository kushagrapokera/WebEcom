# E-Commerce Platform - ReadMe

This project represents a simple e-commerce platform implemented in Django. It allows users to browse products, view their details, and proceed to checkout. Below is a detailed guide to the included files and how to set up and run the project.

## Files Overview

### `detail.html`
This HTML file is the template used to display a product's detailed view, including its image, title, price, discounted price, and description.

#### Features:
- **Responsive Design**: Leverages Bootstrap 4 for layout and styling.
- **Dynamic Content Rendering**: Uses Django's template language (`{{ }}`) to display product details dynamically based on the context provided by views.

#### Components:
- **Product Image**: Renders from `product_object.image`.
- **Title**: Displays the product title using `product_object.title`.
- **Price & Discount**: Shows the original price (`product_object.price`) and discounted price (`product_object.discount_price`).
- **Description**: A brief about the product fetched from `product_object.description`.

### `urls.py`
This file defines URL patterns for routing requests to their respective views.

#### Key Routes:
1. **Admin Panel**:
   ```
   path('admin/', admin.site.urls)
   ```
   Provides access to Django's admin interface.
2. **Home Page**:
   ```
   path('', views.index, name='index')
   ```
   Displays the list of products.
3. **Product Detail**:
   ```
   path('<int:id>/', views.detail, name='detail')
   ```
   Displays the details of a specific product, identified by its unique ID.
4. **Checkout**:
   ```
   path('checkout/', views.checkout, name='checkout')
   ```
   Routes to the checkout page.

## How to Set Up and Run the Project

### Prerequisites
- **Python**: Ensure Python 3.x is installed on your system.
- **Django**: Install Django using pip:
  ```bash
  pip install django
  ```

### Steps:
1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```
2. **Run Migrations**:
   ```bash
   python manage.py migrate
   ```
3. **Start the Development Server**:
   ```bash
   python manage.py runserver
   ```
4. **Access the Application**:
   - Home: `http://127.0.0.1:8000/`
   - Product Detail: `http://127.0.0.1:8000/<product_id>/`
   - Checkout: `http://127.0.0.1:8000/checkout/`

## Browser Recommendation

For optimal performance and compatibility, it is strongly recommended to use **Mozilla Firefox**. Its robust support for modern web technologies ensures a seamless user experience on this platform.

## Notes for Deployment
- Configure media and static files properly for the production environment.
- Ensure the `product_object` passed to templates includes fields like `image`, `title`, `price`, `discount_price`, and `description`.
- Use a production-ready server (e.g., Gunicorn) behind a reverse proxy (e.g., Nginx) for deploying this application.

## License
This project is open-source and available under the [MIT License](LICENSE).

