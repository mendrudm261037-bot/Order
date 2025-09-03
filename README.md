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
