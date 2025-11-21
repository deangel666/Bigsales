<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BigSales E-commerce Store</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 1em;
            text-align: center;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            padding: 0.5em;
        }

        main {
            display: flex;
            flex-wrap: wrap;
            padding: 20px;
            justify-content: space-around;
        }

        .product-item {
            border: 1px solid #ddd;
            padding: 10px;
            margin: 10px;
            width: 200px;
            text-align: center;
            background-color: #fff;
        }

        .product-item img {
            max-width: 100%;
            height: auto;
        }

        footer {
            text-align: center;
            padding: 1em;
            background-color: #333;
            color: #fff;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>BigSales Store</h1>
        <nav>
            <a href="index.html">Home</a>
            <a href="cart.html">Cart</a>
        </nav>
    </header>

    <main id="product-list">
        <!-- Product items will be dynamically added here -->
    </main>

    <footer>
        <p>&copy; 2024 BigSales Store</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const productList = document.getElementById('product-list');

            // Sample product data
            const products = [
                {
                    "id": "1",
                    "name": "Product 1",
                    "price": 20.00,
                    "image": "https://via.placeholder.com/150"
                },
                {
                    "id": "2",
                    "name": "Product 2",
                    "price": 30.00,
                    "image": "https://via.placeholder.com/150"
                },
                {
                    "id": "3",
                    "name": "Product 3",
                    "price": 40.00,
                    "image": "https://via.placeholder.com/150"
                }
            ];

            products.forEach(product => {
                const productDiv = document.createElement('div');
                productDiv.classList.add('product-item');

                productDiv.innerHTML = `
                    <img src="${product.image}" alt="${product.name}">
                    <h3>${product.name}</h3>
                    <p>$${product.price}</p>
                    <button class="add-to-cart" data-id="${product.id}">Add to Cart</button>
                `;
                productList.appendChild(productDiv);
            });

            const addToCartButtons = document.querySelectorAll('.add-to-cart');
            addToCartButtons.forEach(button => {
                button.addEventListener('click', addToCart);
            });

            function addToCart(event) {
                const productId = event.target.dataset.id;
                console.log(`Product ID ${productId} added to cart`);
                // Implement your cart logic here
            }
        });
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shopping Cart - BigSales</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 1em;
            text-align: center;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            padding: 0.5em;
        }

        main {
            padding: 20px;
        }

        footer {
            text-align: center;
            padding: 1em;
            background-color: #333;
            color: #fff;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>Shopping Cart - BigSales</h1>
        <nav>
            <a href="index.html">Home</a>
            <a href="cart.html">Cart</a>
        </nav>
    </header>

    <main id="cart-items">
        <!-- Cart items will be dynamically added here -->
        <p>Your cart is empty.</p>
    </main>

    <footer>
        <p>&copy; 2024 BigSales Store</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const cartItems = document.getElementById('cart-items');
            let cart = [];

            if (cart.length === 0) {
                cartItems.innerHTML = '<p>Your cart is empty.</p>';
            } else {
                displayCart();
            }

            function displayCart() {
                cartItems.innerHTML = '';
                cart.forEach(item => {
                    const cartItemDiv = document.createElement('div');
                    cartItemDiv.innerHTML = `
                        <p>${item.name} - $${item.price}</p>
                    `;
                    cartItems.appendChild(cartItemDiv);
                });
            }
        });
    </script>
</body>
</html>
