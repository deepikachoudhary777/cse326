<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Baké Bliss</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            background-color: #fff8e1;
            color: #4e342e;
        }
        header {
            background-color: #3e2723;
            color: #fff;
            padding: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        nav ul {
            list-style-type: none;
            display: flex;
            gap: 20px;
        }
        nav ul li {
            display: inline;
        }
        nav a {
            color: #ffcc80;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s;
        }
        nav a:hover {
            color: #ffe0b2;
        }
        .hero {
            text-align: center;
            padding: 100px 20px;
            background-image: url('https://i.pinimg.com/originals/ee/4e/fd/ee4efd0d960b477e4dc0373c2837f7a2.jpg');
            background-size: cover;
            background-position: center; 
        }
        .hero h1 {
            font-size: 48px;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            color: white;
        }
        .hero p {
            font-size: 20px;
            margin-bottom: 0;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
            color: white;
        }
        .menu, .about, .contact {
            padding: 30px;
            margin: 20px auto;
            max-width: 900px;
            background-color: #ffffff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .menu h3, .about h3, .contact h3 {
            border-bottom: 2px solid #4e342e;
            padding-bottom: 5px;
            margin-bottom: 15px;
        }
        .menu-item {
            display: flex;
            align-items: center;
            background-color: #ffecb3;
            padding: 15px;
            margin: 10px 0;
            border-radius: 5px;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .menu-item img {
            width: 80px;
            height: 80px;
            border-radius: 10px;
            margin-right: 15px;
        }
        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
        }
        .more-items-button {
            position: relative; /* Required for absolute positioning of .more-items */
            cursor: pointer;
            margin-top: 10px;
        }
        .more-items {
            display: none; /* Hide by default */
            position: absolute;
            top: 100%; /* Position below the "More Items" button */
            left: 0;
            background-color: #ffecb3;
            padding: 10px;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            z-index: 1;
            width: 100%; /* Match the width of the parent */
        }
        .more-items-button:hover .more-items,
        .more-items:hover {
            display: block; /* Show on hover of button or items */
        }
        .more-items h4 {
            margin-top: 10px;
        }
        form input {
            display: block;
            width: 100%;
            margin: 10px 0;
            padding: 10px;
            border-radius: 5px;
            border: 1px solid #ccc;
            font-family: 'Georgia', serif;
        }
        button {
            padding: 12px 20px;
            background-color: #4e342e;
            color: #fff;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #5d4037;
        }
        .cart {
            position: fixed;
            right: 20px;
            top: 80px;
            width: 300px;
            background-color: #ffffff;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            display: none;
            z-index: 1000;
        }
        .cart-header {
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        .cart-items {
            list-style-type: none;
            padding: 0;
        }
        .cart-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }
        .cart-total {
            font-weight: bold;
            margin-top: 10px;
        }
        .show-cart-btn {
            position: fixed;
            right: 20px;
            top: 20px;
            padding: 10px;
            background-color: #4e342e;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <h1>Bakè Bliss</h1>
            <ul>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#about">About Us</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <section class="hero">
        <h1>Welcome to Baké Bliss</h1>
        <p>Experience the best bakery items of the town.</p>
    </section>

    <section id="menu" class="menu">
        <h3>Our Menu</h3>
        <div class="menu-item">
            <img src="https://www.glorioustreats.com/wp-content/uploads/2017/05/cheesecake-recipe-square.jpeg" alt="Latte">
            <div>
                <h4>Cheese Cake</h4>
                <p>₹1000.00</p>
                <input type="number" min="1" value="1" id="cheesecake-qty" style="width: 60px;">
                <button onclick="addToCart('Cheese Cake', 1000, document.getElementById('cheesecake-qty').value)">Add to Cart</button>
            </div>
        </div>
        <div class="menu-item">
            <img src="https://th.bing.com/th/id/OIP.YxCPLUUAzZNQE_fAl95ayAHaHP?rs=1&pid=ImgDetMain" alt="Black-Forest Cake">
            <div>
                <h4>Black-Forest Cake</h4>
                <p>₹750.00</p>
                <input type="number" min="1" value="1" id="blackforest-qty" style="width: 60px;">
                <button onclick="addToCart('Black-Forest Cake', 750, document.getElementById('blackforest-qty').value)">Add to Cart</button>
            </div>
        </div>
        <div class="menu-item">
            <img src="https://bakewithshivesh.com/wp-content/uploads/2021/06/IMG_9649-scaled.jpg" alt="Fruit Cake">
            <div>
                <h4>Fruit Cake</h4>
                <p>₹800.00</p>
                <input type="number" min="1" value="1" id="fruitcake-qty" style="width: 60px;">
                <button onclick="addToCart('Fruit Cake', 800, document.getElementById('fruitcake-qty').value)">Add to Cart</button>
            </div>
        </div>

        <!-- More Items Button and Dropdown -->
        <div class="more-items-button">
            <button>More Items</button>
            <div class="more-items">
                <!-- Additional items like Brownie, Fruit Tart, etc. here -->
                <!-- Update IDs and price values accordingly -->
            </div>
        </div>
    </section>

    <section id="about" class="about">
        <h3>About Us</h3>
        <p>Bakè Bliss is a cozy place where you can enjoy delicious bakery items prepared with love...</p>
    </section>

    <section id="contact" class="contact">
        <h3>Contact Us</h3>
        <form>
            <input type="text" placeholder="Your Name">
            <input type="email" placeholder="Your Email">
            <textarea placeholder="Your Message" rows="4"></textarea>
            <button type="submit">Send Message</button>
        </form>
    </section>

    <div class="cart" id="cart">
        <div class="cart-header">Your Cart</div>
        <ul class="cart-items" id="cart-items"></ul>
        <div class="cart-total" id="cart-total">Total: ₹0.00</div>
    </div>

    <button class="show-cart-btn" onclick="toggleCart()">Show Cart</button>

    <script>
        let cart = [];

        function toggleCart() {
            const cartElement = document.getElementById('cart');
            cartElement.style.display = cartElement.style.display === 'none' ? 'block' : 'none';
        }

        function addToCart(name, price, quantity) {
            quantity = parseInt(quantity);
            const itemIndex = cart.findIndex(item => item.name === name);

            if (itemIndex === -1) {
                cart.push({ name, price, quantity });
            } else {
                cart[itemIndex].quantity += quantity;
            }

            updateCart();
        }

        function updateCart() {
            const cartItemsElement = document.getElementById('cart-items');
            const cartTotalElement = document.getElementById('cart-total');
            cartItemsElement.innerHTML = '';
            let total = 0;

            cart.forEach(item => {
                const totalPrice = item.price * item.quantity;
                total += totalPrice;
                
                cartItemsElement.innerHTML += `
                    <li class="cart-item">
                        ${item.name} (₹${item.price}) x ${item.quantity} = ₹${totalPrice}
                        <button onclick="removeFromCart('${item.name}')">Remove</button>
                    </li>
                `;
            });

            cartTotalElement.textContent = Total: ₹${total.toFixed(2)};
        }

        function removeFromCart(name) {
            const itemIndex = cart.findIndex(item => item.name === name);

            if (itemIndex !== -1) {
                cart.splice(itemIndex, 1);
                updateCart();
            }
        }
    </script>
</body>
</html>
