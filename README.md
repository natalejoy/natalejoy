!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Milktea Island Order Form</title>
</head>
<body>

    <div class="container">
        <form action="#" method="post">
            <h2>Milktea Island Order Form</h2>

            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>

            <label for="Flavor">Flavor:</label>
            <select id="Flavor" name="Flavor" required>
                <option value="black">Black Tea</option>
                <option value="green">Green Tea</option>
                <option value="dark">Dark Choco</option>
                <option value="red">Red Velvet</option>
                <option value="matcha">Matcha</option>
                <option value="mango">Mango Cheese Cake</option>
            </select>

            <label for="quantity">Quantity:</label>
            <input type="number" id="quantity" name="quantity" min="1" value="1" required>

            <label for="sweetness">Sweetness Level:</label>
            <input type="range" id="sweetness" name="sweetness" min="0" max="100" step="10" value="50">
            <output for="sweetness" id="sweetnessValue">50</output>

            <label for="totalPrice">Total Price:</label>
            <input type="text" id="totalPrice" name="totalPrice" readonly>

            <input type="submit" value="Place Order">
        </form>
    </div>

    <script>
        document.getElementById('sweetness').addEventListener('input', function () {
            document.getElementById('sweetnessValue').textContent = this.value;
            updateTotalPrice();
        });

        document.getElementById('quantity').addEventListener('input', function () {
            updateTotalPrice();
        });

        function updateTotalPrice() {
            const quantity = document.getElementById('quantity').value;
            const sweetness = document.getElementById('sweetness').value;
            const unitPrice = calculateUnitPrice();
            const totalPrice = quantity * unitPrice;
            document.getElementById('totalPrice').value = totalPrice.toFixed(2);
        }

        function calculateUnitPrice() {
            // You can add logic to calculate the unit price based on tea type or other factors
            // For simplicity, let's use a fixed unit price here
            return 45;
        }

        // Initial update when the page loads
        updateTotalPrice();
    </script>

</body>
</html>
Jlands replied to themself
Blazado Jlands
INDEX.HTML TASK 9 ADI
Jlands
Blazado Jlands
body {
    font-family: Arial, sans-serif;
    background-image: url('tea ice.jpg');
    background-size: cover;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.container {
    max-width: 400px;
    background: transparent;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

form {
    display: flex;
    flex-direction: column;
}

label {
    margin-bottom: 8px;
}

input[type="text"],
input[type="number"],
select {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
    box-sizing: border-box;
}

input[type="submit"] {
    background: #4caf50;
    color: #fff;
    border: none;
    padding: 10px;
    border-radius: 5px;
    cursor: pointer;
}

input[type="submit"]:hover {
    background: #45a049;
}

output {
    display: block;
    margin-top: 5px;
}
