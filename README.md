# marciulescu.ro
<!DOCTYPE html>
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WWW.MĂRCIULESCU.RO - Tricouri & Cadouri Personalizate</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f4ef;
            color: #333;
        }
        header {
            background-color: #2c2c54;
            color: #fff;
            padding: 20px;
            text-align: center;
        }
        nav {
            display: flex;
            justify-content: center;
            background-color: #f4c2c2;
            padding: 10px 0;
        }
        nav a {
            text-decoration: none;
            color: #333;
            margin: 0 15px;
            font-weight: bold;
        }
        .hero {
            text-align: center;
            padding: 50px 20px;
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            color: #fff;
        }
        .hero h1 {
            font-size: 2.5rem;
            margin: 0;
        }
        .hero p {
            font-size: 1.2rem;
        }
        .products {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            margin: 20px;
        }
        .product {
            background: #fff;
            border: 1px solid #ddd;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            margin: 10px;
            width: 300px;
            text-align: center;
            padding: 15px;
        }
        .product img {
            max-width: 100%;
            border-radius: 10px;
        }
        .product h3 {
            font-size: 1.5rem;
            margin: 10px 0;
        }
        .product button {
            background-color: #2c2c54;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
        }
        .product button:hover {
            background-color: #444;
        }
        .cart {
            position: fixed;
            top: 20px;
            right: 20px;
            background-color: #fff;
            border: 1px solid #ddd;
            border-radius: 10px;
            padding: 15px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 300px;
        }
        .cart h3 {
            margin-top: 0;
        }
        .cart ul {
            list-style: none;
            padding: 0;
        }
        .cart ul li {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }
        footer {
            background-color: #2c2c54;
            color: #fff;
            text-align: center;
            padding: 10px 0;
        }
    </style>
    <script>
        let cart = [];

        function addToCart(product, price) {
            cart.push({ product, price });
            renderCart();
        }

        function renderCart() {
            const cartElement = document.getElementById('cart-items');
            cartElement.innerHTML = '';
            cart.forEach(item => {
                const li = document.createElement('li');
                li.textContent = `${item.product} - ${item.price} RON`;
                cartElement.appendChild(li);
            });
            document.getElementById('total').textContent = cart.reduce((sum, item) => sum + item.price, 0) + ' RON';
        }
    </script>
</head>
<body>
    <header>
        <h1>WWW.MĂRCIULESCU.RO</h1>
        <p>Tricouri, căni, șepci și accesorii personalizate pentru un stil autentic românesc!</p>
    </header>
    <nav>
        <a href="#acasa">Acasă</a>
        <a href="#categorii">Categorii</a>
        <a href="#despre">Despre</a>
        <a href="#contact">Contact</a>
    </nav>
    <div class="hero">
        <h1>Bine ai venit!</h1>
        <p>Descoperă colecții unice de produse personalizate, create cu drag în România!</p>
    </div>
    <section class="products">
        <div class="product">
            <img src="https://via.placeholder.com/300x200" alt="Tricou Personalizat">
            <h3>Tricou Amuzant</h3>
            <p>99 RON</p>
            <button onclick="addToCart('Tricou Amuzant', 99)">Adaugă în coș</button>
        </div>
        <div class="product">
            <img src="https://via.placeholder.com/300x200" alt="Cană Personalizată">
            <h3>Cană cu Mesaj</h3>
            <p>119 RON</p>
            <button onclick="addToCart('Cană cu Mesaj', 119)">Adaugă în coș</button>
        </div>
        <div class="product">
            <img src="https://via.placeholder.com/300x200" alt="Șapcă Personalizată">
            <h3>Șapcă Tradițională</h3>
            <p>109 RON</p>
            <button onclick="addToCart('Șapcă Tradițională', 109)">Adaugă în coș</button>
        </div>
    </section>
    <div class="cart">
        <h3>Coșul tău de cumpărături</h3>
        <ul id="cart-items"></ul>
        <p>Total: <span id="total">0 RON</span></p>
    </div>
    <footer>
        <p>&copy; 2025 WWW.MĂRCIULESCU.RO - Toate drepturile rezervate.</p>
    </footer>
</body>
</html>
