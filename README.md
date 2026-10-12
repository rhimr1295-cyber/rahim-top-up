<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#0a0a0a">
<title>RAHIM TOP UP | متجر الألعاب</title>
<style>
:root{--gold:#edc65b;--bg:#090909;--card:#151515;--muted:#aaa}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:#fff;font-family:Arial,sans-serif}
header{padding:22px 15px;text-align:center;background:linear-gradient(135deg,#171717,#080808);border-bottom:1px solid #6e571e}
.logo{font-size:29px;font-weight:900;color:var(--gold);letter-spacing:1px}
header p{color:#bbb;font-size:13px}
nav{display:flex;justify-content:center;gap:10px;flex-wrap:wrap;padding:12px}
nav a{color:var(--gold);text-decoration:none;border:1px solid #51421d;border-radius:20px;padding:8px 13px;font-size:13px}
.hero{padding:35px 18px;text-align:center;background:radial-gradient(ellipse at top,#302510,#090909 70%)}
.hero h1{font-size:29px;margin:0 0 12px}
.hero h1 span{color:var(--gold)}
.hero p{color:#bbb;line-height:1.8}
.tag{display:inline-block;color:var(--gold);border:1px solid #6b541f;border-radius:20px;padding:7px 13px;font-size:12px}
.wrap{max-width:950px;margin:auto;padding:18px 13px}
.tools{display:flex;gap:9px;flex-wrap:wrap;margin-bottom:18px}
input,select{min-width:0;background:#191919;color:white;border:1px solid #393939;padding:13px;border-radius:9px;font-size:14px}
#search{flex:1}
.games{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
.card{background:linear-gradient(145deg,#1b1b1b,#101010);border:1px solid #39301b;border-radius:15px;padding:15px;text-align:center}
.art{height:85px;display:grid;place-items:center;font-size:48px;background:radial-gradient(circle,#342918,#151515 70%);border-radius:10px}
.card h3{margin:14px 0 6px;color:var(--gold)}
.card p{color:#bbb;font-size:13px;min-height:16px}
.price{font-size:20px;font-weight:bold;margin:14px 0}
button{cursor:pointer;border:0;border-radius:9px;padding:12px;font-weight:bold}
.add{background:var(--gold);color:#17120a;width:100%}
.cart{margin-top:25px;background:#141414;border:1px solid #42351b;border-radius:15px;padding:18px}
h2{font-size:21px}
h2 span{color:var(--gold)}
.field{display:grid;gap:10px;margin:12px 0}
.field input{width:100%}
.item{display:flex;align-items:center;justify-content:space-between;gap:8px;padding:10px 0;border-bottom:1px solid #303030;font-size:13px}
.remove{background:#3a2020;color:white;padding:7px}
.total{display:flex;justify-content:space-between;color:var(--gold);font-size:20px;font-weight:bold;margin:18px 0}
.order{width:100%;background:#20bd5a;color:#07170b;font-size:16px}
.note{font-size:12px;color:#aaa;line-height:1.7}
footer{text-align:center;padding:25px;color:#888;border-top:1px solid #282828;margin-top:25px}
@media(min-width:650px){.games{grid-template-columns:repeat(4,minmax(0,1fr))}.hero h1{font-size:39px}}
</style>
</head>
<body>
<header>
<div class="logo">RAHIM TOP UP</div>
<p>متجرك للألعاب الرقمية في الجزائر 🇩🇿</p>
<span class="tag">GAMING STORE · PRO</span>
</header>
<nav>
<a href="#store">المتجر</a>
<a href="#cart">سلة المشتريات</a>
<a href="#contact">اتصل بنا</a>
</nav>
<section class="hero">
<h1>ارفع مستواك مع <span>RAHIM TOP UP</span></h1>
<p>اختار لعبتك وباقتك، راجع المجموع، وابعث طلبك عبر واتساب.</p>
<span class="tag">الأسعار بالدينار الجزائري DZD</span>
</section>

<main class="wrap" id="store">
<h2>اكتشف <span>الباقات</span></h2>
<div class="tools">
<input id="search" placeholder="🔎 ابحث عن لعبة..." oninput="render()">
<select id="filter" onchange="render()">
<option value="all">كل الألعاب</option>
<option value="ff">Free Fire</option>
<option value="pubg">PUBG Mobile</option>
<option value="efootball">eFootball</option>
</select>
</div>
<div class="games" id="games"></div>

<section class="cart" id="cart">
<h2>🛒 <span>سلة المشتريات</span></h2>
<div id="items">السلة فارغة، اختار باقة أولاً.</div>
<div class="total"><span>المجموع</span><span id="total">0 دج</span></div>
<div class="field">
<input id="buyer" placeholder="اسم الزبون">
<input id="player" placeholder="معرّف اللاعب ID">
</div>
<button class="order" onclick="order()">إرسال الطلب عبر واتساب</button>
<p class="note">الأسعار المعروضة تجريبية. تأكد من الأسعار وتوفر الباقات قبل استقبال الطلبات. لا تدخل كلمة مرور حساب اللعبة.</p>
</section>
</main>
<footer id="contact">
<div class="logo">RAHIM TOP UP</div>
<p>للألعاب، صنعناه بشغف 🎮</p>
<p>الطلب عبر واتساب: 0562949660</p>
</footer>

<script>
const products=[
{id:1,game:"ff",name:"Free Fire",pack:"100 جوهرة",price:250,emoji:"🔥"},
{id:2,game:"ff",name:"Free Fire",pack:"310 جوهرة",price:650,emoji:"💎"},
{id:3,game:"ff",name:"Free Fire",pack:"520 جوهرة",price:1000,emoji:"✨"},
{id:4,game:"pubg",name:"PUBG Mobile",pack:"60 UC",price:300,emoji:"🪖"},
{id:5,game:"pubg",name:"PUBG Mobile",pack:"325 UC",price:1200,emoji:"🎯"},
{id:6,game:"efootball",name:"eFootball",pack:"باقة تجريبية",price:500,emoji:"⚽"}
];
let cart=[];
const money=n=>n.toLocaleString("fr-DZ")+" دج";
function render(){
let q=document.getElementById("search").value.toLowerCase();
let f=document.getElementById("filter").value;
let list=products.filter(p=>(p.name+" "+p.pack).toLowerCase().includes(q)&&(f==="all"||p.game===f));
document.getElementById("games").innerHTML=list.map(p=>`
<div class="card">
<div class="art">${p.emoji}</div>
<h3>${p.name}</h3><p>${p.pack}</p>
<div class="price">${money(p.price)}</div>
<button class="add" onclick="add(${p.id})">أضف للسلة +</button>
</div>`).join("")||"<p>ما لقيناش هذي اللعبة.</p>";
}
function add(id){let p=products.find(x=>x.id===id);cart.push({...p,key:Date.now()+Math.random()});showCart();}
function removeItem(key){cart=cart.filter(x=>x.key!==key);showCart();}
function showCart(){
document.getElementById("items").innerHTML=cart.length?cart.map(p=>`
<div class="item"><span>${p.emoji} ${p.name} - ${p.pack}<br>${money(p.price)}</span>
<button class="remove" onclick="removeItem(${p.key})">حذف</button></div>`).join(""):"السلة فارغة، اختار باقة أولاً.";
document.getElementById("total").textContent=money(cart.reduce((s,p)=>s+p.price,0));
}
function order(){
if(!cart.length){alert("زيد باقة للسلة أولاً.");return;}
let buyer=document.getElementById("buyer").value.trim();
let player=document.getElementById("player").value.trim();
if(!buyer||!player){alert("دخل اسمك ومعرّف اللاعب.");return;}
let lines=cart.map(p=>"- "+p.name+" / "+p.pack+" / "+money(p.price)).join("\n");
let msg="طلب جديد - RAHIM TOP UP\nالاسم: "+buyer+"\nمعرّف اللاعب: "+player+"\n\n"+lines+"\n\nالمجموع: "+money(cart.reduce((s,p)=>s+p.price,0));
window.open("https://wa.me/213562949660?text="+encodeURIComponent(msg),"_blank");
}
render();showCart();
</script>
</body>
</html>