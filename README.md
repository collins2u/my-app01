# my-app01
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">

<title>TOLU TECH COMPANY</title>

<script src="https://js.paystack.co/v1/inline.js"></script>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial;
}

body{
background:#eef2f7;
}

header{
background:linear-gradient(90deg,#0b2f56,#1679c4);
padding:20px;
color:white;
position:sticky;
top:0;
z-index:100;
}

.top{
display:flex;
justify-content:space-between;
align-items:center;
}

.logo{
display:flex;
align-items:center;
gap:10px;
}

.ttc{
width:60px;
height:60px;
border-radius:50%;
background:gold;
color:#0b2f56;
display:flex;
justify-content:center;
align-items:center;
font-size:22px;
font-weight:bold;
}

.hero{
height:350px;
background:url('https://images.unsplash.com/photo-1517336714739-489689fd1ca8') center/cover;
display:flex;
justify-content:center;
align-items:center;
color:white;
font-size:45px;
font-weight:bold;
text-shadow:2px 2px 5px black;
}

.products{
padding:30px;
}

.title{
text-align:center;
font-size:30px;
margin-bottom:20px;
color:#0b2f56;
}

.grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
gap:20px;
}

.card{
background:white;
border-radius:15px;
overflow:hidden;
box-shadow:0 5px 15px rgba(0,0,0,.1);
}

.card img{
width:100%;
height:220px;
object-fit:cover;
}

.info{
padding:15px;
}

.price{
color:#1679c4;
font-size:22px;
font-weight:bold;
margin:10px 0;
}

button{
padding:10px;
border:none;
background:#1679c4;
color:white;
width:100%;
cursor:pointer;
border-radius:8px;
}

.cart{
margin:30px;
background:white;
padding:20px;
border-radius:10px;
}

.forms{
display:grid;
grid-template-columns:1fr 1fr;
gap:20px;
padding:30px;
}

form{
background:white;
padding:20px;
border-radius:10px;
}

input,textarea{
width:100%;
padding:12px;
margin-top:10px;
margin-bottom:15px;
}

.contactBtns{
display:flex;
gap:10px;
margin-top:10px;
}

.whatsapp{
background:green;
}

.sms{
background:orange;
}

footer{
background:#0b2f56;
color:white;
text-align:center;
padding:20px;
margin-top:30px;
}

@media(max-width:768px){

.forms{
grid-template-columns:1fr;
}

.hero{
font-size:28px;
}

}

</style>
</head>

<body>

<header>

<div class="top">

<div class="logo">

<div class="ttc">TTC</div>

<div>
<h2>TOLU TECH COMPANY</h2>
<small>Laptops • Phones • Accessories</small>
</div>

</div>

<h3>🛒 Cart: ₦<span id="total">0</span></h3>

</div>

</header>

<div class="hero">
TOLU TECH COMPANY
</div>

<section class="products">

<h2 class="title">OUR PRODUCTS</h2>

<div class="grid">

<div class="card">
<img src="https://images.unsplash.com/photo-1496181133206-80ce9b88a853">
<div class="info">
<h3>HP EliteBook</h3>
<p class="price">₦550,000</p>
<button onclick="add(550000)">Add To Cart</button>
</div>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1511707171634-5f897ff02aa9">
<div class="info">
<h3>iPhone 15</h3>
<p class="price">₦1,250,000</p>
<button onclick="add(1250000)">Add To Cart</button>
</div>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1580910051074-3eb694886505">
<div class="info">
<h3>Dell XPS</h3>
<p class="price">₦780,000</p>
<button onclick="add(780000)">Add To Cart</button>
</div>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1583394838336-acd977736f90">
<div class="info">
<h3>Samsung Galaxy</h3>
<p class="price">₦850,000</p>
<button onclick="add(850000)">Add To Cart</button>
</div>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1505740420928-5e560c06d30e">
<div class="info">
<h3>Headset</h3>
<p class="price">₦35,000</p>
<button onclick="add(35000)">Add To Cart</button>
</div>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1606220588913-b3aacb4d2f46">
<div class="info">
<h3>Smart Watch</h3>
<p class="price">₦80,000</p>
<button onclick="add(80000)">Add To Cart</button>
</div>
</div>

</div>

</section>

<div class="cart">

<h2>Order Summary</h2>

<p>Total Amount: ₦<span id="amount">0</span></p>

<br>

<button onclick="payNow()">PAY ONLINE</button>

</div>

<div class="forms">

<form>

<h2>Order Form</h2>

<input placeholder="Customer Name">

<input placeholder="Phone">

<input placeholder="Address">

<textarea placeholder="Product details"></textarea>

<button type="submit">
Place Order
</button>

</form>

<form>

<h2>Contact Us</h2>

<input placeholder="Name">

<input placeholder="Email">

<textarea placeholder="Message"></textarea>

<button>Send Message</button>

<div class="contactBtns">

<a href="https://wa.me/2349015680037" style="width:100%;">
<button type="button" class="whatsapp">
WhatsApp
</button>
</a>

<a href="sms:+2349015680037" style="width:100%;">
<button type="button" class="sms">
SMS
</button>
</a>

</div>

</form>

</div>

<footer>

TOLU TECH COMPANY © 2026

</footer>

<script>

let total=
localStorage.getItem("cart")
?
parseInt(localStorage.getItem("cart"))
:0;

update();

function add(price){

total+=price;

localStorage.setItem(
"cart",
total
);

update();

}

function update(){

document.getElementById(
"total"
).innerHTML=
total.toLocaleString();

document.getElementById(
"amount"
).innerHTML=
total.toLocaleString();

}

function payNow(){

let handler=
PaystackPop.setup({

key:
'pk_test_xxxxxxxxx',

email:
'tolu@gmail.com',

amount:
total*100,

currency:
'NGN',

callback:function(){

alert(
'Payment Successful'
);

}

});

handler.openIframe();

}

</script>

</body>
</html>
