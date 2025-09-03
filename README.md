<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bakery Order Form</title>
  <style>
    body { font-family: Arial, sans-serif; max-width: 600px; margin: 20px auto; padding: 20px; }
    h2 { text-align: center; }
    table { width: 100%; border-collapse: collapse; margin-bottom: 20px; }
    th, td { padding: 10px; text-align: center; border-bottom: 1px solid #ddd; }
    input[type="number"] { width: 60px; text-align: center; }
    .total { font-weight: bold; font-size: 18px; margin: 10px 0; text-align: right; }
    .note { font-size: 14px; color: #555; margin-bottom: 10px; }
    button { padding: 10px 15px; font-size: 16px; cursor: pointer; }
  </style>
</head>
<body>

  <h2>🍞 Bakery Order Form</h2>

  <form action="https://formspree.io/f/mwpnrdzj" method="POST">
    
    <!-- Customer Info -->
    <label>Name:</label><br>
    <input type="text" name="customer_name" required><br><br>

    <label>Email:</label><br>
    <input type="email" name="customer_email" required><br><br>

    <label>Phone:</label><br>
    <input type="tel" name="customer_phone" required><br><br>

    <!-- Product List -->
    <table>
      <tr>
        <th>Product</th>
        <th>Price (₹)</th>
        <th>Quantity</th>
      </tr>
      <tr>
        <td>Bread</td>
        <td>₹40</td>
        <td><input type="number" name="bread_qty" value="0" min="0" onchange="calculateTotal()"></td>
      </tr>
      <tr>
        <td>Cake Slice</td>
        <td>₹60</td>
        <td><input type="number" name="cake_qty" value="0" min="0" onchange="calculateTotal()"></td>
      </tr>
      <tr>
        <td>Donut</td>
        <td>₹30</td>
        <td><input type="number" name="donut_qty" value="0" min="0" onchange="calculateTotal()"></td>
      </tr>
      <tr>
        <td>Cookies Pack</td>
        <td>₹50</td>
        <td><input type="number" name="cookies_qty" value="0" min="0" onchange="calculateTotal()"></td>
      </tr>
    </table>

    <!-- Total -->
    <div class="total">Total: ₹<span id="totalAmount">0</span></div>
    <input type="hidden" name="order_total" id="orderTotal">

    <!-- Payment -->
    <p class="note">Please pay the above total using UPI/Google Pay/Paytm and enter your Transaction/Reference ID below.</p>
    <label>Payment Reference ID:</label><br>
    <input type="text" name="payment_ref" placeholder="e.g. TXN12345678" required><br><br>

    <button type="submit">Submit Order</button>
  </form>

  <script>
    function calculateTotal() {
      const bread = 40 * parseInt(document.querySelector('[name="bread_qty"]').value || 0);
      const cake = 60 * parseInt(document.querySelector('[name="cake_qty"]').value || 0);
      const donut = 30 * parseInt(document.querySelector('[name="donut_qty"]').value || 0);
      const cookies = 50 * parseInt(document.querySelector('[name="cookies_qty"]').value || 0);

      const total = bread + cake + donut + cookies;
      document.getElementById('totalAmount').innerText = total;
      document.getElementById('orderTotal').value = total;
    }
  </script>

</body>
</html>
