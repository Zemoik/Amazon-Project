# Amazon Clone

A multi-page Amazon homepage clone built with HTML, CSS, and vanilla JavaScript 
— featuring a dynamic product grid loaded from JSON, a persistent shopping cart, 
a full checkout page with delivery options, and unit tests written in Jasmine.

![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Jasmine](https://img.shields.io/badge/Jasmine-8A4182?style=flat&logo=jasmine&logoColor=white)

## Features
- Product grid dynamically rendered from a `products.json` backend file
- Add to Cart button updates live cart quantity count in the header
- Cart persists across page reloads using `localStorage`
- Checkout page showing each cart item with product image, name, price, and quantity
- Dynamic delivery date calculation using `dayjs` based on selected delivery option
- Three delivery options per item (FREE standard, paid expedited, paid same-day)
- Remove item from cart with instant DOM update — no page reload
- Payment summary panel calculating item subtotal, shipping cost, tax, and order total
- Prices stored in cents and formatted to dollars using a `formatCurrency()` utility
- Cart merges quantity when the same product is added multiple times
- Unit tests for cart logic and money formatting written in Jasmine 5.1.1
- ES Modules (`import`/`export`) used across all JavaScript files
- Separate CSS files for shared styles, page-specific styles, and checkout styles

## Pages
| Page | File | Description |
|------|------|-------------|
| Homepage | `amazon.html` | Product grid with Add to Cart |
| Checkout | `checkout.html` | Order summary, delivery options, payment summary |
| Orders | `orders.html` | Order history page |
| Tracking | `tracking.html` | Order tracking page |

## Tech Stack
| Layer | Technology |
|-------|------------|
| Structure | HTML5 |
| Styling | CSS3 (Flexbox, shared + page-specific stylesheets) |
| Logic | Vanilla JavaScript (ES6 Modules) |
| Date handling | dayjs |
| Testing | Jasmine 5.1.1 |
| Data | JSON (products backend) |
| Storage | Browser localStorage API |

## Setup
```bash
git clone https://github.com/Zemoik/Amazon-Project.git
cd Amazon-Project
open amazon.html
```
No dependencies or build step required. Uses ES Modules so open via a local 
server if your browser blocks module imports:
```bash
npx serve .
```

## Project Structure
```
Amazon-Project/
├── amazon.html                        # Homepage — product grid
├── checkout.html                      # Checkout — order summary + payment
├── orders.html                        # Order history page
├── tracking.html                      # Order tracking page
├── backend/
│   └── products.json                  # Product data loaded via fetch
├── data/
│   ├── cart.js                        # Cart state, localStorage, add/remove/update
│   ├── cart-class.js                  # OOP version of cart using ES6 class
│   ├── products.js                    # Product class with getPrice(), getStarsUrl()
│   └── deliveryOptions.js             # Delivery option definitions and lookup
├── scripts/
│   ├── amazon.js                      # Renders product grid, handles add to cart
│   ├── checkout.js                    # Bootstraps checkout page
│   ├── checkout/
│   │   ├── orderSummary.js            # Renders cart items with delivery options
│   │   └── paymentSummary.js          # Calculates and renders order total
│   └── utils/
│       └── money.js                   # formatCurrency() — converts cents to dollars
├── tests/
│   ├── data/cartTest.js               # Unit tests for cart add/remove/update logic
│   ├── checkout/orderSummaryTest.js   # Unit tests for order summary rendering
│   └── utils/moneyTest.js             # Unit tests for formatCurrency()
└── styles/
    ├── shared/                        # amazon-header.css, general.css
    └── pages/                         # amazon.css, checkout.css, orders.css, tracking.css
```

## What I Learned
- Structuring a multi-page JavaScript app using ES Modules (`import`/`export`)
- Persisting and merging cart state in `localStorage` with JSON serialization
- Dynamically rendering HTML from data arrays using template literals
- Calculating estimated delivery dates using the `dayjs` library
- Separating concerns across modules — cart logic, product data, utility functions
- Writing unit tests for pure functions using Jasmine 5.1.1
- Building an OOP version of the cart using an ES6 class (`cart-class.js`)
- Managing DOM updates without a framework using `querySelector` and `innerHTML`

## Author
**Dev Patel** — [LinkedIn](https://www.linkedin.com/in/dev--patel--/) · [GitHub](https://github.com/Zemoik)
