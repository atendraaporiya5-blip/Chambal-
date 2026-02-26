# Chambal-
Chambal thrift 
index.html<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Chambal Thrift</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
margin:0;
font-family:Arial;
background:#111;
color:white;
text-align:center;
}
header{
background:black;
padding:20px;
font-size:28px;
font-weight:bold;
}
.products{
display:flex;
flex-wrap:wrap;
justify-content:center;
gap:20px;
padding:30px;
}
.card{
background:#1a1a1a;
padding:15px;
width:250px;
border-radius:10px;
}
.card img{
width:100%;
border-radius:8px;
}
button{
background:#ff3c00;
border:none;
padding:10px 15px;
color:white;
border-radius:5px;
cursor:pointer;
margin-top:10px;
}
#cart{
background:#222;
padding:20px;
margin:20px;
border-radius:10px;
}
</style>
</head>

<body>

<header>CHAMBAL THRIFT</header>

<h2>Shop Collection</h2>

<div class="products">

<div class="card">
<img src="https://images.unsplash.com/photo-1521572163474-6864f9cf17ab">
<h3>Oversized T-Shirt</h3>
<p>₹499</p>
<button onclick="addToCart('Oversized T-Shirt',499)">Add to Cart</button>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1541099649105-f69ad21f3246">
<h3>Vintage Hoodie</h3>
<p>₹899</p>
<button onclick="addToCart('Vintage Hoodie',899)">Add to Cart</button>
</div>

</div>

<div id="cart">
<h2>Your Cart</h2>
<ul id="cartItems"></ul>
<h3>Total: ₹<span id="total">0</span></h3>

<button onclick="orderWhatsApp()">Order on WhatsApp</button>
<button onclick="payNow()">Pay Now</button>
</div>

<script>
let cart = [];
let total = 0;

function addToCart(name,price){
cart.push({name,price});
total += price;
document.getElementById("total").innerText = total;

let li = document.createElement("li");
li.innerText = name + " - ₹" + price;
document.getElementById("cartItems").appendChild(li);
}

function orderWhatsApp(){
let message = "Order Details:%0A";
cart.forEach(item=>{
message += item.name + " - ₹" + item.price + "%0A";
});
message += "Total: ₹" + total;

window.open("https://wa.me/91+7747810484text="+message);
}

function payNow(){
alert("Payment integration ke liye Razorpay account banana hoga. Main next step me bata dunga kaise kare.");
}
</script>

</body>
</html>
