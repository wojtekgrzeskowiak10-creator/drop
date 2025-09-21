<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sklep Fitness</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: #f4f4f4;
        }
        header {
            background: #2c3e50;
            color: #fff;
            padding: 20px;
            text-align: center;
        }
        nav a {
            color: #fff;
            margin: 0 15px;
            text-decoration: none;
        }
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 20px auto;
        }
        .product {
            background: #fff;
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 15px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
        }
        .product img {
            width: 150px;
            height: 150px;
            object-fit: cover;
            margin-right: 20px;
            border-radius: 5px;
        }
        .product h3 {
            margin: 0 0 10px;
        }
        .product p {
            margin: 5px 0;
        }
        .product button {
            padding: 10px 20px;
            background: #e74c3c;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .product button:hover {
            background: #c0392b;
        }
        footer {
            background: #2c3e50;
            color: #fff;
            text-align: center;
            padding: 15px;
            margin-top: 20px;
        }
    </style>
</head>
<body>

<header>
    <h1>Sklep Fitness</h1>
    <nav>
        <a href="#products">Produkty</a>
        <a href="#contact">Kontakt</a>
    </nav>
</header>

<div class="container" id="products">
    <div class="product">
        <img src="https://via.placeholder.com/150" alt="Gumy oporowe">
        <div>
            <h3>Gumy oporowe</h3>
            <p>Cena: 59 zł</p>
            <p>Idealne do treningu siłowego w domu.</p>
            <button onclick="addToCart('Gumy oporowe', 59)">Dodaj do koszyka</button>
        </div>
    </div>

    <div class="product">
        <img src="https://via.placeholder.com/150" alt="Mata do ćwiczeń">
        <div>
            <h3>Mata do ćwiczeń</h3>
            <p>Cena: 79 zł</p>
            <p>Komfortowa i antypoślizgowa.</p>
            <button onclick="addToCart('Mata do ćwiczeń', 79)">Dodaj do koszyka</button>
        </div>
    </div>

    <div class="product">
        <img src="https://via.placeholder.com/150" alt="Skakanka profesjonalna">
        <div>
            <h3>Skakanka profesjonalna</h3>
            <p>Cena: 49 zł</p>
            <p>Do treningu cardio i koordynacji.</p>
            <button onclick="addToCart('Skakanka profesjonalna', 49)">Dodaj do koszyka</button>
        </div>
    </div>
</div>

<div class="container" id="cart">
    <h2>Koszyk</h2>
    <ul id="cartItems"></ul>
    <p id="totalPrice">Łączna cena: 0 zł</p>
</div>

<footer id="contact">
    <p>Kontakt: kontakt@sklepfitness.pl</p>
    <p>© 2025 Sklep Fitness</p>
</footer>

<script>
    let cart = [];

    function addToCart(name, price) {
        cart.push({name: name, price: price});
        updateCart();
        alert(name + " dodano do koszyka!");
    }

    function updateCart() {
        const cartItems = document.getElementById('cartItems');
        const totalPrice = document.getElementById('totalPrice');
        cartItems.innerHTML = '';
        let total = 0;
        cart.forEach(item => {
            let li = document.createElement('li');
            li.textContent = item.name + " - " + item.price + " zł";
            cartItems.appendChild(li);
            total += item.price;
        });
        totalPrice.textContent = "Łączna cena: " + total + " zł";
    }
</script>

</body>
</html
