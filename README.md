<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>RAHIM TOP UP</title>
<style>
*{box-sizing:border-box}
body{margin:0;background:#090909;color:#fff;font-family:Arial,sans-serif}
header{text-align:center;padding:28px 12px;background:#151515;border-bottom:2px solid #d7b34c}
h1{color:#e6c45d;margin:0;font-size:30px}
header p{color:#ccc}
.hero{text-align:center;padding:24px 12px}
.hero h2{color:#e6c45d}
.games{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px;padding:12px}
.card{background:#191919;border:1px solid #51401b;border-radius:14px;padding:14px;text-align:center}
.emoji{font-size:40px}
.card h3{color:#e6c45d}
.price{font-size:20px;margin:12px}
button{width:100%;padding:12px;border:0;border-radius:8px;background:#e0bc53;color:#111;font-weight:bold}
.cart{margin:12px;padding:16px;background:#191919;border-radius:12px}
input{width:100%;padding:12px;margin:7px 0;background:#292929;color:white;border:1px solid #555;border-radius:8px}
footer{text-align:center;padding:20px;color:#aaa}
</style>
</head>
<body>
<header>
<h1>RAHIM TOP UP</h1>
<p>متجرك لشحن الألعاب في الجزائر 🇩🇿</p>
</header>
<section class="hero">
<h2>اختار لعبتك وابدأ الشحن 🎮</h2>
<p>خدمة طلب عبر واتساب</p>
</section>
<section class="games">
<div class="card">
<div class="emoji">🔥</div>
<h3>Free Fire</h3>
<p>100 جوهرة</p>
<div class="price">250 دج</div>
<button onclick="add('Free Fire - 100 جوهرة',250)">أضف للسلة</button>
</div>
<div class="card">
<div class="emoji">💎</div>
<h3>Free Fire</h3>
<p>310 جوهرة</p>
<div class="price">650 دج</div>
<button onclick="add('Free Fire - 310 جوهرة',650)">أضف للسلة</button>
</div>
<div class="card">
<div class="emoji">🪖</div>
<h3>PUBG Mobile</h3>
<p>60 UC</p>
<div class="price">300 دج</div>
<button onclick="add('PUBG Mobile - 60 UC',300)">أضف للسلة</button>
</div>
<div class="card">
<div class="emoji">⚽</div>
<h3>eFootball</h3>
<p>باقة تجريبية</p>
<div class="price">500 دج</div>
<button onclick="add('eFootball - باقة تجريبية',500)">أضف للسلة</button>
</div>
</section>
<section class="cart">
<h2>🛒 سلة المشتريات</h2>
<div id="items">السلة فارغة</div>
<h3>المجموع: <span id="total">0</span> دج</h3>
<input id="buyer" placeholder="اسمك">
<input id="player" placeholder="معرّف اللاعب ID">
<button onclick="order()">اطلب عبر واتساب</button>
<p style="color:#aaa;font-size:12px">الأسعار تجريبية وتحتاج التأكيد قبل البيع.</p>
</section>
<footer>© RAHIM TOP UP</footer>
<script>
let cart=[];
function add(name,price){cart.push({name,price});show();}
function show(){
document.getElementById('items').innerHTML=cart.length?cart.map((x,i)=>'<p>'+x.name+' — '+x.price+' دج <button style="width:auto" onclick="removeItem('+i+')">حذف</button></p>').join(''):'السلة فارغة';
document.getElementById('total').textContent=cart.reduce((s,x)=>s+x.price,0);
}
function removeItem(i){cart.splice(i,1);show();}
function order(){
if(!cart.length){alert('زيد باقة للسلة أولاً');return;}
let buyer=document.getElementById('buyer').value.trim();
let player=document.getElementById('player').value.trim();
if(!buyer||!player){alert('دخل اسمك ومعرّف اللاعب');return;}
let msg='طلب RAHIM TOP UP\nالاسم: '+buyer+'\nID: '+player+'\n';
cart.forEach(x=>msg+=x.name+' - '+x.price+' دج\n');
msg+='المجموع: '+cart.reduce((s,x)=>s+x.price,0)+' دج';
window.open('https://wa.me/213562949660?text='+encodeURIComponent(msg),'_blank');
}
</script>
</body>
</html>