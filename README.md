[index.html](https://github.com/user-attachments/files/25462122/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>3 HERMANOS BTP0</title>
<link href="style.css" rel="stylesheet">
<style>
body { background:#f4f6f9; }
.navbar { background:#111; }
.navbar-brand { font-weight:bold; color:#00ff88 !important; }
.card:hover { transform:scale(1.03); transition:0.3s; }
.price { font-size:1.4rem; font-weight:bold; color:#198754; }
.hero {
    background: linear-gradient(90deg,#000,#222);
    color:white;
    padding:60px 20px;
    text-align:center;
}
.btn-main {
    background:#00ff88;
    border:none;
    font-weight:bold;
}
</style>
</head>
    </form>
    <body>

<nav class="navbar navbar-dark navbar-expand-lg">
<div class="container">
<a class="navbar-brand" href="#">3 HERMANOS BTP0</a>
<form class="text" aria-required="true"
</div><button class="btn btn-outline-light me-2" onclick="showLogin()">Login</button>
<button class="btn btn-success" onclick="showCart()">🛒 Carrito (<span id="cartCount">0</span>)</button>

</div>

</div>
</nav>

<section class="hero">
<h2>TECNOLOGIA MAS VENDIDA ULTIMAMENTE PARA TU ENTRETENIMIENTO DIARIO 🚀</h1>
<p>Los productos más vendidos en Argentina al mejor precio con descuentos todos los findes</p>
</section>

<div class="container mt-5">
<div class="row" id="productList"></div>
</div>

<!-- Modal Producto -->
<div class="modal fade" id="productModal">
<div class="modal-dialog modal-lg">
<div class="modal-content">
<div class="modal-body" id="modalContent"></div>
</div>
</div>
</div>

<!-- Modal Carrito -->
<div class="modal fade" id="cartModal">
<div class="modal-dialog">
<div class="modal-content">
<div class="modal-header"><h5>Tu Carrito</h5></div>
<div class="modal-body" id="cartItems"></div>
<div class="modal-footer">
<h5>Total: $<span id="cartTotal">0</span> ARS</h5>
</div>
</div>
</div>
</div>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>

<script>
let products = [

{
id:1,
name:"Notebook Gamer RTX 4060",
price:1250000,
image:"https://m.media-amazon.com/images/I/71an9eiBxpL._AC_SL1500_.jpg",
description:"Potencia total para gaming y trabajo. Intel i7 13° Gen, 16GB RAM, RTX 4060. Rendimiento profesional.",
seller:"Gaming Pro AR ⭐⭐⭐⭐",
location:"Córdoba"
},
{
id:2,
name:"Smart TV 55'' 4K UHD",
price:780000,
image:"tv55.jpg",
description:"Sumergite en imagen 4K Ultra HD. Netflix, YouTube, HDR10 y sonido envolvente.",
seller:"ElectroHogar ⭐⭐⭐⭐⭐",
location:"Rosario"
},
{
id:3,
name:"Auriculares Bluetooth Sony",
price:45000,
image:"aurissony.jpg",
description:"Cancelación de ruido profesional, batería 30h, graves potentes.",
seller:"AudioMax ⭐⭐⭐⭐",
location:"Mendoza"
},
{
id:4,
name:"Smartwatch Deportivo",
price:120000,
image:"relojsmart.jpg",
description:"Controla tu salud y rendimiento. Monitor cardíaco, oxígeno en sangre, resistente al agua.",
seller:"FitTech ⭐⭐⭐⭐",
location:"La Plata"
}
]
{id:5 
name:"ps5"
price:1400000
image:"ps5.jpg"
description:""
}
let cart = [];

function renderProducts(){
let html="";
products.forEach(p=>{
html+=`
<div class="col-md-4 mb-4">
<div class="card shadow">
<img src="${p.image}" class="card-img-top" height="250">
<div class="card-body">
<h5>${p.name}</h5>
<p class="price">$${p.price.toLocaleString()} ARS</p>
<button class="btn btn-main w-100 mb-2" onclick="viewProduct(${p.id})">Ver Detalles</button>
<button class="btn btn-success w-100" onclick="addToCart(${p.id})">Agregar al carrito</button>
</div>
</div>
</div>`;
});
document.getElementById("productList").innerHTML=html;
}

function viewProduct(id){
let p = products.find(x=>x.id===id);
document.getElementById("modalContent").innerHTML=`
<div class="row">
<div class="col-md-6">
<img src="${p.image}" class="img-fluid">
</div>
<div class="col-md-6">
<h3>${p.name}</h3>
<p class="price">$${p.price.toLocaleString()} ARS</p>
<p>${p.description}</p>
<hr>
<p><strong>Vendedor:</strong> ${p.seller}</p>
<p><strong>Ubicación:</strong> ${p.location}</p>
<button class="btn btn-success w-100" onclick="addToCart(${p.id})">Agregar al carrito</button>
</div>
</div>`;
new bootstrap.Modal(document.getElementById('productModal')).show();
}

function addToCart(id){
let product = products.find(p=>p.id===id);
cart.push(product);
document.getElementById("cartCount").innerText=cart.length;
alert("Producto agregado al carrito 🛒");
}

function showCart(){
let html="";
let total=0;
cart.forEach(p=>{
total+=p.price;
html+=`<p>${p.name} - $${p.price.toLocaleString()} ARS</p>`;
});
document.getElementById("cartItems").innerHTML=html || "Carrito vacío";
document.getElementById("cartTotal").innerText=total.toLocaleString();
new bootstrap.Modal(document.getElementById('cartModal')).show();
}

function showLogin(){
alert("Sistema de Login Simulado ✅\nUsuario: admin\nContraseña: 1234");
}

renderProducts();
</script>

</body>
</html>
