# Grocery-Delivery-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grocery Delivery App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        
        header {
            background-color: #f0f0f0;
            padding: 20px;
            text-align: center;
        }
        
        main {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        section {
            background-color: #fff;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        
        #order-form {
            width: 50%;
        }
        
        #orders-list {
            width: 50%;
        }
        
        #orders-ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }
        
        #orders-ul li {
            padding: 10px;
            border-bottom: 1px solid #ccc;
        }
        
        #orders-ul li:last-child {
            border-bottom: none;
        }
        
        #delivery-status {
            width: 50%;
        }
        
        #delivery-status-msg {
            font-size: 18px;
            font-weight: bold;
            color: #666;
        }
        
        #deliver-orders-btn {
            background-color: #4CAF50;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        
        #deliver-orders-btn:hover {
            background-color: #3e8e41;
        }
    </style>
</head>
<body>
    <header>
        <h1>Grocery Delivery App</h1>
    </header>
    <main>
        <section id="order-form">
            <h2>Place an Order</h2>
            <form>
                <label for="customer-name">Customer Name:</label>
                <input type="text" id="customer-name" required>
                <br>
                <label for="items">Items:</label>
                <textarea id="items" required></textarea>
                <br>
                <label for="address">Address:</label>
                <input type="text" id="address" required>
                <br>
                <button id="place-order-btn">Place Order</button>
            </form>
        </section>
        <section id="orders-list">
            <h2>Orders</h2>
            <ul id="orders-ul">
                <!-- orders will be displayed here -->
            </ul>
        </section>
        <section id="delivery-status">
            <h2>Delivery Status</h2>
            <p id="delivery-status-msg">No orders to deliver</p>
            <button id="deliver-orders-btn">Deliver Orders</button>
        </section>
    </main>
    <script>
        let orders = [];

        document.getElementById('place-order-btn').addEventListener('click', (e) => {
            e.preventDefault();
            const customerName = document.getElementById('customer-name').value;
            const items = document.getElementById('items').value;
            const address = document.getElementById('address').value;
            const order = { customerName, items, address };
            orders.push(order);
            displayOrders();
            document.getElementById('order-form').reset();
        });

        document.getElementById('deliver-orders-btn').addEventListener('click', () => {
            deliverOrders();
        });
       

        function displayOrders() {
            const ordersUl = document.getElementById('orders-ul');
            ordersUl.innerHTML = '';
            orders.forEach((order) => {
                const li = document.createElement('li');
                li.textContent = `Customer: ${order.customerName}, Items: ${order.items}, Address: ${order.address}`;
                ordersUl.appendChild(li);
            });
        }

        function deliverOrders() {
            const deliveryStatusMsg = document.getElementById('delivery-status-msg');
            if (orders.length > 0) {
                deliveryStatusMsg.textContent = `Delivering orders to ${orders[0].address}...`;
                // simulate delivery process
                setTimeout(() => {
                    deliveryStatusMsg.textContent = `Orders delivered successfully!`;
                    orders.shift();
                    displayOrders();
                }, 2000);
            } else {
                deliveryStatusMsg.textContent = `No orders to deliver`;
            }
        }
    </script>
    <div class="grocery item ">
        <img src="C:\Users\Dell\OneDrive\Pictures\Screenshots\th (7).jpeg" alt="" />
        <h4>buy any thing</h4>
        <div class="rating">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <p>₹50.00</p>
        <li><a href="index.html">BUY</a></li>
        <li><a href="index.html">add to cart</a></li>
      </div>
      <div class="grocery item ">
        <img src="C:\Users\Dell\OneDrive\Pictures\Screenshots\th.jpeg" alt="" />
        <h4>buy any thing</h4>
        <div class="rating">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <p>₹299.00</p>
        <li><a href="index.html">BUY</a></li>
        <li><a href="index.html">add to cart</a></li>
      </div>
      <div class="grocery item ">
        <img src="C:\Users\Dell\OneDrive\Pictures\Screenshots\th (6).jpeg" alt="" />
        <h4>buy any thing</h4>
        <div class="rating">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <p>₹99.00</p>
        <li><a href="index.html">BUY</a></li>
        <li><a href="index.html">add to cart</a></li>
      </div>
      <div class="grocery item ">
        <img src="C:\Users\Dell\OneDrive\Pictures\Screenshots\th (5).jpeg" alt="" />
        <h4>buy any thing</h4>
        <div class="rating">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <p>₹110.00</p>
        <li><a href="index.html">BUY</a></li>
        <li><a href="index.html">add to cart</a></li>
      </div>
      <div class="grocery item ">
        <img src="C:\Users\Dell\OneDrive\Pictures\Screenshots\th.jpeg" alt="" />
        <h4>buy any thing</h4>
        <div class="rating">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <p>₹60.00</p>
        <li><a href="index.html">BUY</a></li>
        <li><a href="index.html">add to cart</a></li>
      </div>
</body>
</html>
<p>
    "web dev :- By Er.Aryan"
</p>

