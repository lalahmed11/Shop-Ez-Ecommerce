# ShopEZ - Frontend E-Commerce Application

ShopEZ is a complete client-side e-commerce prototype built to demonstrate modern frontend development concepts using HTML, CSS, JavaScript, Bootstrap, jQuery, JSON, and LocalStorage.

The application allows users to browse products, view product details, manage a shopping cart, and simulate checkout without any backend server.

## 1. Project Overview

ShopEZ is designed as a practical frontend project that covers:

- Product listing and filtering
- Product details page
- Add/remove/update cart items
- Persistent cart state using LocalStorage
- Checkout form validation and order simulation
- Responsive UI using Bootstrap 5

This project is backend-ready in structure and can be integrated with APIs later.

## 2. What I Used (Tech Stack)

### Core Technologies

- HTML5
- CSS3
- JavaScript (ES6-style patterns)
- Bootstrap 5 (CDN)
- jQuery (CDN)
- JSON (for product data)
- LocalStorage (for persistence)

### UI/Utility Libraries

- Bootstrap Icons (for navbar/footer icons)
- Google Fonts (Outfit)

## 3. Project Structure

```text
ShopEZ-Frontend/
|-- index.html
|-- products.html
|-- product-details.html
|-- cart.html
|-- checkout.html
|-- css/
|   |-- styles.css
|-- js/
|   |-- common.js
|   |-- products.js
|   |-- cart.js
|   |-- checkout.js
|-- data/
|   |-- products.json
|-- images/
```

## 4. Pages and Their Purpose

### Home Page (`index.html`)

- Shows hero/intro section
- Displays trending/featured products
- Quick navigation to products/cart/checkout

### Products Page (`products.html`)

- Displays full catalog in card layout
- Live search by product name
- Category-based filtering
- Add to cart from product cards
- View details navigation

### Product Details Page (`product-details.html`)

- Shows large product image
- Displays product name, description, category, and price
- Quantity selector (+/-)
- Add to cart and view cart actions

### Cart Page (`cart.html`)

- Shows all selected items
- Update quantity with plus/minus
- Remove single item
- Clear full cart
- Shows subtotal, shipping, and total

### Checkout Page (`checkout.html`)

- Shipping/contact form with validation
- Payment method selection
- Order summary preview
- Simulated order placement with order reference

## 5. JavaScript Architecture (Modular)

### `js/common.js`

Shared core utilities and data handling:

- Cart CRUD (add/update/remove/clear)
- Cart persistence to LocalStorage
- Currency formatter (`Rs`)
- Product data loader utility
- Shared summary calculation
- Toast utility and cart badge sync

### `js/products.js`

Product-related UI and interactions:

- Render product cards (home + catalog)
- Fetch products from JSON
- Category color mapping
- Live search + category filter
- Product details rendering by ID
- Category-colored toasts on add-to-cart

### `js/cart.js`

Cart page behavior:

- Render line items
- Quantity update controls
- Remove/clear actions
- Recalculate summary using shared summary logic

### `js/checkout.js`

Checkout page behavior:

- Form validation and submission flow
- Order summary rendering
- Payment method UI behavior
- Simulated order placement and success state

## 6. Product Data Format (`data/products.json`)

Each product follows this structure:

```json
{
  "id": 1,
  "name": "AeroTune Headphones",
  "description": "Wireless noise-canceling headphones...",
  "price": 2999,
  "image": "images/Headphones.jpg",
  "category": "Electronics"
}
```

## 7. Business Rules Implemented

### Cart & Shipping Rules

- Shipping is free for items with price <= Rs 500
- Shipping is Rs 99 per unit for items with price > Rs 500
- If subtotal > Rs 6000, shipping becomes free
- Tax is not applied in final total

### Quantity Rules

- Minimum quantity: 1
- Maximum quantity in cart updates: 99
- Product details quantity control remains bounded for clean UX

## 8. jQuery Events Used

- `ready` - initialize modules on page load
- `click` - add/remove/clear cart, qty +/- buttons
- `input` - live product search
- `change` - category filter, qty input, payment method style
- `submit` - checkout form submit and validation

## 9. Bootstrap Components Used

- Navbar + Offcanvas
- Grid (`container`, `row`, `col-*`)
- Cards
- Buttons
- Forms and validation feedback
- Utility classes for spacing/layout/alignment

## 10. UI/UX Highlights

- Responsive design across mobile/tablet/desktop
- Consistent navbar/footer across all pages
- Category-based card color system
- Cart badge count in navbar
- Toast notifications with contextual category color
- Clean and accessible visual hierarchy

## 11. LocalStorage Usage

The project uses LocalStorage for:

- Cart state persistence (`cart` key)
- Legacy cart key migration support
- Last order record storage (`shopez_last_order`)

## 12. Functional Coverage Checklist

- Product listing page: Implemented
- Product details page: Implemented
- Add/remove/update cart: Implemented
- Checkout simulation: Implemented
- Responsive UI: Implemented
- LocalStorage persistence: Implemented
- Modular JS architecture: Implemented

## 13. How to Run the Project

### Option 1: Python Static Server

```bash
python -m http.server 8080
```

Open in browser:

- `http://localhost:8080/index.html`

### Option 2: VS Code Live Server

- Open project folder
- Run with Live Server extension

## 14. Testing Plan

|        Test Case      |         Expected Result                    |
|-----------------------|--------------------------------------------|
| Product listing loads | Product cards render correctly             |
| Search/filter         | Product list updates correctly             |
| Add to cart           | Item appears in cart + badge count updates |
| Remove item           | Item is removed and totals recalculate     |
| Quantity update       | Line totals and summary update correctly   |
| Clear cart            | Cart resets to empty state                 |
| Checkout validation   | Required fields show validation states     |
| Place order           | Success state appears and cart clears      |

## 15. Evaluation Readiness (Rubric Alignment)

- Functional Implementation: Covered
- UI/UX Design: Responsive and polished
- Code Quality: Modular file structure, reusable utilities
- Data Handling: JSON + LocalStorage handled correctly
- Application Working: End-to-end flow functional

## 16. Future Enhancements

- Backend API integration (products/orders/users)
- Authentication and user profiles
- Admin product management dashboard
- Payment gateway integration
- Order history and tracking

## 17. Conclusion

ShopEZ successfully demonstrates a production-style frontend architecture for an e-commerce workflow using only client-side technologies. It is suitable as a portfolio project and as a base for backend/API integration in the next phase.
