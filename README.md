<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>حسابداری لوازم التحریر سایه</title>

<style>
*{box-sizing:border-box;margin:0;padding:0}

body{
  font-family:Tahoma,Arial,sans-serif;
  background:#f1f5f9;
  color:#172033;
  min-height:100vh;
}

button,input{font-family:inherit}
button{cursor:pointer}

/* ===== LOGIN ===== */
#loginPage{
  position:fixed;
  inset:0;
  background:#f1f5f9;
  display:flex;
  align-items:center;
  justify-content:center;
  z-index:99999;
}

.login-box{
  width:90%;
  max-width:380px;
  background:#fff;
  padding:25px;
  border-radius:22px;
  box-shadow:0 8px 30px #0002;
}

.login-box h2{
  text-align:center;
  margin-bottom:20px;
}

.login-box input{
  width:100%;
  padding:14px;
  margin-bottom:12px;
  border:1px solid #dbe1e8;
  border-radius:13px;
  outline:none;
}

.login-box button{
  width:100%;
  border:0;
  background:#0f172a;
  color:#fff;
  padding:14px;
  border-radius:13px;
  font-size:14px;
}

#loginMessage{
  text-align:center;
  color:#dc2626;
  font-size:12px;
  margin-top:12px;
}

/* ===== APP ===== */
.app{
  max-width:850px;
  margin:auto;
  padding-bottom:40px;
}

header{
  background:linear-gradient(135deg,#0f172a,#1e293b);
  color:#fff;
  padding:25px 20px;
  border-radius:0 0 28px 28px;
  box-shadow:0 8px 25px #0002;
}

header h1{
  font-size:23px;
  margin-bottom:7px;
}

header p{
  font-size:12px;
  color:#cbd5e1;
}

.logout{
  margin-top:15px;
  background:#dc2626;
  color:white;
  border:0;
  padding:9px 15px;
  border-radius:10px;
}

.nav{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:8px;
  padding:13px;
}

.nav button{
  border:0;
  background:#fff;
  padding:13px 5px;
  border-radius:14px;
  color:#475569;
  box-shadow:0 3px 12px #0000000c;
  font-size:12px;
}

.nav button.active{
  background:#0f172a;
  color:#fff;
}

.page{display:none}
.page.active{display:block}

.cards{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:10px;
  padding:0 13px 13px;
}

.card{
  background:#fff;
  border-radius:20px;
  padding:17px;
  box-shadow:0 4px 15px #0000000c;
}

.card small{
  color:#64748b;
  font-size:11px;
}

.card strong{
  display:block;
  font-size:17px;
  margin-top:9px;
}

.green{color:#15803d}
.red{color:#dc2626}
.blue{color:#2563eb}
.purple{color:#7c3aed}

.panel{
  background:#fff;
  margin:0 13px 13px;
  padding:17px;
  border-radius:21px;
  box-shadow:0 4px 15px #0000000c;
}

.panel h2{
  font-size:17px;
  margin-bottom:15px;
}

.form-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:11px;
}

.full{grid-column:1/-1}

label{
  display:block;
  font-size:11px;
  color:#64748b;
  margin-bottom:5px;
}

input,select{
  width:100%;
  padding:13px;
  border:1px solid #dbe1e8;
  border-radius:13px;
  outline:none;
  font-size:13px;
  background:#fff;
}

.primary{
  width:100%;
  border:0;
  background:#0f172a;
  color:#fff;
  padding:14px;
  border-radius:13px;
  margin-top:12px;
  font-size:13px;
}

.secondary{
  border:1px solid #dbe1e8;
  background:#fff;
  padding:12px;
  border-radius:12px;
  font-size:12px;
}

.danger{
  border:0;
  background:#fee2e2;
  color:#b91c1c;
  padding:8px 10px;
  border-radius:9px;
  font-size:11px;
}

.success{
  border:0;
  background:#dcfce7;
  color:#15803d;
  padding:8px 10px;
  border-radius:9px;
  font-size:11px;
}

.product{
  border:1px solid #e5e7eb;
  padding:13px;
  border-radius:16px;
  margin-bottom:9px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
}

.product-name{
  font-weight:bold;
  font-size:14px;
}

.product-info{
  color:#64748b;
  font-size:10px;
  line-height:1.8;
  margin-top:4px;
}

.product-actions{
  display:flex;
  gap:5px;
}

.search{
  margin-bottom:12px;
}

.invoice-item{
  background:#f8fafc;
  border:1px solid #edf1f5;
  border-radius:13px;
  padding:11px;
  margin-bottom:8px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.invoice-total{
  border-top:2px solid #e5e7eb;
  margin-top:12px;
  padding-top:13px;
  display:flex;
  justify-content:space-between;
  font-size:18px;
  font-weight:bold;
}

.empty{
  text-align:center;
  color:#94a3b8;
  padding:28px 5px;
  font-size:13px;
}

.modal{
  position:fixed;
  inset:0;
  background:#0009;
  display:none;
  align-items:center;
  justify-content:center;
  padding:12px;
  z-index:1000;
}

.modal.show{display:flex}

.modal-box{
  background:#fff;
  width:100%;
  max-width:650px;
  max-height:92vh;
  overflow:auto;
  border-radius:23px;
  padding:18px;
}

.modal-head{
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:15px;
}

.close{
  border:0;
  background:#f1f5f9;
  padding:9px 12px;
  border-radius:10px;
}

.print-invoice{
  background:#fff;
  color:#111827;
  padding:10px;
}

.invoice-paper{
  border:1px solid #dbe1e8;
  border-radius:12px;
  overflow:hidden;
}

.invoice-top{
  background:#0f172a;
  color:#fff;
  padding:24px 20px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:15px;
}

.store-name{
  font-size:22px;
  font-weight:bold;
}

.store-sub{
  font-size:11px;
  color:#cbd5e1;
  margin-top:6px;
}

.invoice-number{
  background:#fff;
  color:#0f172a;
  border-radius:12px;
  padding:11px 14px;
  text-align:center;
  min-width:120px;
}

.invoice-number small{
  font-size:9px;
  color:#64748b;
  display:block;
  margin-bottom:5px;
}

.invoice-number strong{font-size:14px}

.invoice-info{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
  padding:15px 18px;
  background:#f8fafc;
  border-bottom:1px solid #e5e7eb;
}

.info-box{
  font-size:11px;
  color:#475569;
}

.info-box strong{
  display:block;
  color:#111827;
  margin-top:5px;
  font-size:12px;
}

.invoice-table{
  width:100%;
  border-collapse:collapse;
  font-size:11px;
}

.invoice-table th{
  background:#f1f5f9;
  padding:11px 7px;
  text-align:right;
  font-size:10px;
}

.invoice-table td{
  padding:11px 7px;
  border-bottom:1px solid #edf0f3;
}

.invoice-summary{padding:15px 18px}

.summary-line{
  display:flex;
  justify-content:space-between;
  font-size:12px;
  margin-bottom:9px;
  color:#475569;
}

.summary-final{
  display:flex;
  justify-content:space-between;
  font-size:18px;
  font-weight:bold;
  padding-top:11px;
  border-top:2px solid #111827;
}

.invoice-footer{
  padding:18px;
  display:flex;
  justify-content:space-between;
  font-size:10px;
  color:#64748b;
  border-top:1px solid #e5e7eb;
}

.signature{
  width:130px;
  text-align:center;
  padding-top:25px;
  border-top:1px dashed #94a3b8;
}

.backup-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
}

.backup-button{
  border:1px solid #dbe1e8;
  background:#fff;
  border-radius:14px;
  padding:15px 10px;
  font-size:12px;
}

.backup-button strong{
  display:block;
  margin-bottom:5px;
  font-size:14px;
}

.backup-button span{
  color:#64748b;
  font-size:10px;
}

@media(max-width:430px){
  .nav{grid-template-columns:repeat(2,1fr)}
  .cards{gap:8px;padding:0 9px 10px}
  .panel{margin:0 9px 10px;padding:14px}
  .form-grid{grid-template-columns:1fr}
  .invoice-top{padding:18px 13px}
  .store-name{font-size:18px}
  .invoice-number{min-width:95px;padding:9px}
  .invoice-info{grid-template-columns:1fr}
}

@media print{
  body{background:white}
  body *{visibility:hidden}
  #printArea,#printArea *{visibility:visible}
  #printArea{
    position:absolute;
    top:0;
    left:0;
    width:100%;
  }
}
</style>
</head>

<body>

<!-- ================= LOGIN ================= -->

<div id="loginPage">

  <div class="login-box">

    <h2>🔐 ورود به حساب</h2>

    <input
      id="username"
      type="text"
      placeholder="نام کاربری">

    <input
      id="password"
      type="password"
      placeholder="رمز عبور">

    <button onclick="login()">
      ورود
    </button>

    <p id="loginMessage"></p>

  </div>

</div>


<!-- ================= APP ================= -->

<div class="app" id="app">

<header>

<h1>📒 حسابداری لوازم التحریر سایه</h1>

<p>
مدیریت کالا، موجودی، فروش، فاکتور و پشتیبان اطلاعات
</p>

<button class="logout" onclick="logout()">
خروج از حساب
</button>

</header>


<div class="nav">

<button class="active" data-page="dashboard">
🏠 داشبورد
</button>

<button data-page="products">
📦 کالاها
</button>

<button data-page="sale">
🧾 فروش
</button>

<button data-page="invoices">
📋 فاکتورها
</button>

</div>


<!-- ================= DASHBOARD ================= -->

<section id="dashboard" class="page active">

<div class="cards">

<div class="card">
<small>فروش کل</small>
<strong class="green" id="dashSales">
۰ تومان
</strong>
</div>

<div class="card">
<small>سود</small>
<strong class="blue" id="dashProfit">
۰ تومان
</strong>
</div>

<div class="card">
<small>تعداد کالا</small>
<strong class="purple" id="dashProducts">
۰
</strong>
</div>

<div class="card">
<small>فاکتورها</small>
<strong class="red" id="dashInvoices">
۰
</strong>
</div>

</div>


<div class="panel">

<h2>📊 وضعیت انبار</h2>

<div class="product">

<div>

<div class="product-name">
ارزش موجودی
</div>

<div class="product-info">
بر اساس قیمت خرید
</div>

</div>

<strong id="stockValue">
۰ تومان
</strong>

</div>

</div>


<div class="panel">

<h2>💾 پشتیبان اطلاعات</h2>

<p style="font-size:11px;color:#64748b;line-height:2;margin-bottom:12px">

با دانلود پشتیبان، تمام کالاها، موجودی‌ها،
قیمت‌ها و فاکتورها در یک فایل ذخیره می‌شوند.

</p>

<div class="backup-grid">

<button
class="backup-button"
onclick="downloadBackup()">

<strong>
📥 دانلود کل اطلاعات
</strong>

<span>
کالاها + موجودی + فاکتورها
</span>

</button>


<button
class="backup-button"
onclick="document.getElementById('backupFile').click()">

<strong>
📤 بازیابی اطلاعات
</strong>

<span>
انتخاب فایل پشتیبان
</span>

</button>

</div>

<input
id="backupFile"
type="file"
accept=".json"
hidden
onchange="restoreBackup(event)">

</div>


<div class="panel">

<h2>⚠️ مدیریت اطلاعات</h2>

<button
class="danger"
style="width:100%;padding:13px"
onclick="clearEverything()">

🗑 حذف تمام اطلاعات برنامه

</button>

</div>

</section>


<!-- ================= PRODUCTS ================= -->

<section id="products" class="page">

<div class="panel">

<h2>➕ افزودن کالا</h2>

<div class="form-grid">

<div>

<label>نام کالا</label>

<input
id="productName"
placeholder="مثلاً دفتر 100 برگ">

</div>


<div>

<label>قیمت خرید</label>

<input
id="buyPrice"
type="number"
inputmode="numeric">

</div>


<div>

<label>قیمت فروش</label>

<input
id="sellPrice"
type="number"
inputmode="numeric">

</div>


<div>

<label>موجودی اولیه</label>

<input
id="stock"
type="number"
inputmode="numeric"
value="0">

</div>

</div>


<button
class="primary"
onclick="addProduct()">

➕ ثبت کالا

</button>

</div>


<div class="panel">

<h2>📦 کالاهای فروشگاه</h2>

<input
class="search"
id="productSearch"
placeholder="🔎 جستجوی کالا..."
oninput="renderProducts()">

<div id="productList"></div>

</div>

</section>


<!-- ================= SALE ================= -->

<section id="sale" class="page">

<div class="panel">

<h2>🧾 اطلاعات فاکتور</h2>

<div class="form-grid">

<div>

<label>نام مشتری</label>

<input
id="customerName"
placeholder="مثلاً محمد">

</div>


<div>

<label>تاریخ</label>

<input
id="saleDate"
type="date">

</div>


<div>

<label>نوع تخفیف</label>

<select
id="discountType"
onchange="renderCart()">

<option value="amount">
مبلغ ثابت (تومان)
</option>

<option value="percent">
درصدی (%)
</option>

</select>

</div>


<div>

<label>تخفیف</label>

<input
id="discountValue"
type="number"
inputmode="numeric"
min="0"
value="0"
oninput="renderCart()">

</div>

</div>

</div>


<div class="panel">

<h2>🛒 افزودن کالا</h2>

<div class="form-grid">

<div>

<label>کالا</label>

<input
id="saleProduct"
list="productOptions"
placeholder="نام کالا">

<datalist id="productOptions"></datalist>

</div>


<div>

<label>تعداد</label>

<input
id="saleQty"
type="number"
inputmode="numeric"
min="1"
value="1">

</div>

</div>


<button
class="primary"
onclick="addToInvoice()">

➕ افزودن به فاکتور

</button>

</div>


<div class="panel">

<h2>🧾 فاکتور فعلی</h2>

<div id="cart"></div>

<div class="invoice-total">

<span>
مبلغ کل
</span>

<span id="cartTotal">
۰ تومان
</span>

</div>


<button
class="primary"
onclick="saveInvoice()">

✅ ثبت نهایی فاکتور

</button>

</div>

</section>


<!-- ================= INVOICES ================= -->

<section id="invoices" class="page">

<div class="panel">

<h2>📋 فاکتورهای فروش</h2>

<input
class="search"
id="invoiceSearch"
placeholder="🔎 جستجو..."
oninput="renderInvoices()">

<div id="invoiceList"></div>

</div>

</section>


<!-- ================= PRODUCT MODAL ================= -->

<div class="modal" id="productModal">

<div class="modal-box">

<div class="modal-head">

<h2>✏️ ویرایش کالا</h2>

<button
class="close"
onclick="closeProductModal()">

✕

</button>

</div>


<input
id="editId"
type="hidden">


<div class="form-grid">

<div class="full">

<label>نام کالا</label>

<input id="editName">

</div>


<div>

<label>قیمت خرید</label>

<input
id="editBuy"
type="number">

</div>


<div>

<label>قیمت فروش</label>

<input
id="editSell"
type="number">

</div>


<div>

<label>موجودی</label>

<input
id="editStock"
type="number">

</div>

</div>


<button
class="primary"
onclick="saveEditProduct()">

💾 ذخیره

</button>

</div>

</div>


<!-- ================= INVOICE MODAL ================= -->

<div class="modal" id="invoiceModal">

<div class="modal-box">

<div class="modal-head">

<h2>🧾 فاکتور فروش</h2>

<button
class="close"
onclick="closeInvoiceModal()">

✕

</button>

</div>


<div id="printArea"></div>


<button
class="primary"
onclick="window.print()">

🖨 چاپ / ذخیره PDF

</button>

</div>

</div>


<script>

/* =====================================================
   LOGIN
===================================================== */

/*
  این دو مقدار را به نام کاربری و رمز دلخواه خودت تغییر بده.
*/

const LOGIN_USERNAME = "mohammad";
const LOGIN_PASSWORD = "1234";


function login(){

  const username =
    document.getElementById("username").value.trim();

  const password =
    document.getElementById("password").value;

  const message =
    document.getElementById("loginMessage");


  if(
    username === LOGIN_USERNAME &&
    password === LOGIN_PASSWORD
  ){

    localStorage.setItem(
      "sayeh_logged_in",
      "true"
    );

    document.getElementById(
      "loginPage"
    ).style.display = "none";

    message.textContent = "";

  }else{

    message.textContent =
      "❌ نام کاربری یا رمز عبور اشتباه است";

  }

}


function logout(){

  localStorage.removeItem(
    "sayeh_logged_in"
  );

  location.reload();

}


/* بررسی ورود قبلی */

if(
  localStorage.getItem("sayeh_logged_in")
  === "true"
){

  document.getElementById(
    "loginPage"
  ).style.display = "none";

}


/* =====================================================
   ACCOUNTING
===================================================== */

const PRODUCTS_KEY =
  "sayeh_products_final";

const INVOICES_KEY =
  "sayeh_invoices_final";


let products =
  JSON.parse(
    localStorage.getItem(PRODUCTS_KEY)
    || "[]"
  );


let invoices =
  JSON.parse(
    localStorage.getItem(INVOICES_KEY)
    || "[]"
  );


let cart = [];


function saveData(){

  localStorage.setItem(
    PRODUCTS_KEY,
    JSON.stringify(products)
  );

  localStorage.setItem(
    INVOICES_KEY,
    JSON.stringify(invoices)
  );

}


function fa(n){

  return Number(n || 0)
    .toLocaleString("fa-IR");

}


function today(){

  return new Date()
    .toISOString()
    .slice(0,10);

}


function escapeHTML(text){

  return String(text || "")
    .replace(/[&<>"']/g,function(m){

      return {
        "&":"&amp;",
        "<":"&lt;",
        ">":"&gt;",
        '"':"&quot;",
        "'":"&#039;"
      }[m];

    });

}


/* ================= NAVIGATION ================= */

document
.querySelectorAll(".nav button")
.forEach(button=>{

  button.onclick = ()=>{

    document
    .querySelectorAll(".nav button")
    .forEach(x =>
      x.classList.remove("active")
    );

    button.classList.add("active");


    document
    .querySelectorAll(".page")
    .forEach(x =>
      x.classList.remove("active")
    );


    document
    .getElementById(button.dataset.page)
    .classList.add("active");


    renderAll();

  };

});


document.getElementById(
  "saleDate"
).value = today();


/* ================= PRODUCTS ================= */

function addProduct(){

  let name =
    document
    .getElementById("productName")
    .value
    .trim();


  let buy =
    Number(
      document.getElementById("buyPrice").value
    );


  let sell =
    Number(
      document.getElementById("sellPrice").value
    );


  let stock =
    Number(
      document.getElementById("stock").value
    ) || 0;


  if(!name){

    alert("نام کالا را وارد کنید.");
    return;

  }


  if(
    sell <= 0 ||
    buy < 0 ||
    stock < 0
  ){

    alert("اطلاعات وارد شده صحیح نیست.");
    return;

  }


  let duplicate =
    products.some(
      p =>
        p.name.toLowerCase()
        === name.toLowerCase()
    );


  if(duplicate){

    alert("این کالا قبلاً ثبت شده است.");
    return;

  }


  products.push({

    id:Date.now().toString(),

    name:name,

    buyPrice:buy,

    sellPrice:sell,

    stock:stock

  });


  saveData();


  document.getElementById(
    "productName"
  ).value = "";

  document.getElementById(
    "buyPrice"
  ).value = "";

  document.getElementById(
    "sellPrice"
  ).value = "";

  document.getElementById(
    "stock"
  ).value = "0";


  renderAll();

  alert("کالا با موفقیت ثبت شد ✅");

}


function renderProducts(){

  let q =
    (
      document
      .getElementById("productSearch")
      ?.value || ""
    )
    .trim()
    .toLowerCase();


  let list =
    document.getElementById(
      "productList"
    );


  let arr =
    products.filter(
      p =>
        p.name
        .toLowerCase()
        .includes(q)
    );


  if(!arr.length){

    list.innerHTML =
      '<div class="empty">کالایی ثبت نشده است.</div>';

    return;

  }


  list.innerHTML =
    arr.map(p=>`

      <div class="product">

        <div>

          <div class="product-name">
            ${escapeHTML(p.name)}
          </div>

          <div class="product-info">

            قیمت خرید:
            ${fa(p.buyPrice)}
            تومان<br>

            قیمت فروش:
            ${fa(p.sellPrice)}
            تومان<br>

            موجودی:
            <strong>
              ${fa(p.stock)}
            </strong>

          </div>

        </div>


        <div class="product-actions">

          <button
            class="success"
            onclick="editProduct('${p.id}')">

            ✏️

          </button>


          <button
            class="danger"
            onclick="deleteProduct('${p.id}')">

            🗑

          </button>

        </div>

      </div>

    `).join("");


  updateProductOptions();

}


function updateProductOptions(){

  let options =
    document.getElementById(
      "productOptions"
    );


  options.innerHTML =
    products.map(
      p =>
        `<option value="${escapeHTML(p.name)}">`
    ).join("");

}


function editProduct(id){

  let p =
    products.find(
      x => x.id === id
    );


  if(!p)return;


  document.getElementById(
    "editId"
  ).value = p.id;


  document.getElementById(
    "editName"
  ).value = p.name;


  document.getElementById(
    "editBuy"
  ).value = p.buyPrice;


  document.getElementById(
    "editSell"
  ).value = p.sellPrice;


  document.getElementById(
    "editStock"
  ).value = p.stock;


  document.getElementById(
    "productModal"
  ).classList.add("show");

}


function saveEditProduct(){

  let id =
    document.getElementById(
      "editId"
    ).value;


  let p =
    products.find(
      x => x.id === id
    );


  if(!p)return;


  let name =
    document.getElementById(
      "editName"
    ).value.trim();


  let buy =
    Number(
      document.getElementById(
        "editBuy"
      ).value
    );


  let sell =
    Number(
      document.getElementById(
        "editSell"
      ).value
    );


  let stock =
    Number(
      document.getElementById(
        "editStock"
      ).value
    );


  if(
    !name ||
    sell <= 0 ||
    buy < 0 ||
    stock < 0
  ){

    alert("اطلاعات صحیح نیست.");
    return;

  }


  p.name = name;
  p.buyPrice = buy;
  p.sellPrice = sell;
  p.stock = stock;


  saveData();

  closeProductModal();

  renderAll();

}


function deleteProduct(id){

  let p =
    products.find(
      x => x.id === id
    );


  if(!p)return;


  if(
    !confirm(
      "این کالا حذف شود؟"
    )
  )return;


  products =
    products.filter(
      x => x.id !== id
    );


  saveData();

  renderAll();

}


function closeProductModal(){

  document
  .getElementById("productModal")
  .classList.remove("show");

}


/* ================= CART ================= */

function addToInvoice(){

  let name =
    document
    .getElementById("saleProduct")
    .value
    .trim();


  let qty =
    Number(
      document.getElementById(
        "saleQty"
      ).value
    );


  if(
    !name ||
    qty <= 0
  ){

    alert(
      "نام کالا و تعداد را وارد کنید."
    );

    return;

  }


  let product =
    products.find(
      p =>
        p.name
        .toLowerCase()
        === name.toLowerCase()
    );


  if(!product){

    alert(
      "❌ این کالا در فروشگاه ثبت نشده است."
    );

    return;

  }


  if(product.stock <= 0){

    alert(
      "❌ موجودی این کالا تمام شده است."
    );

    return;

  }


  let existing =
    cart.find(
      x =>
        x.productId
        === product.id
    );


  let oldQty =
    existing
    ? existing.qty
    : 0;


  if(
    oldQty + qty
    > product.stock
  ){

    alert(
      "❌ موجودی کافی نیست.\n\n" +
      "موجودی فعلی: "
      + fa(product.stock)
    );

    return;

  }


  if(existing){

    existing.qty += qty;

  }else{

    cart.push({

      productId:product.id,

      name:product.name,

      qty:qty,

      price:product.sellPrice

    });

  }


  document.getElementById(
    "saleProduct"
  ).value = "";


  document.getElementById(
    "saleQty"
  ).value = "1";


  renderCart();

}


function renderCart(){

  let box =
    document.getElementById(
      "cart"
    );


  if(!cart.length){

    box.innerHTML =
      '<div class="empty">فاکتور هنوز خالی است.</div>';


    document.getElementById(
      "cartTotal"
    ).textContent =
      "۰ تومان";


    return;

  }


  let total = 0;


  box.innerHTML =
    cart.map(
      (item,index)=>{

        let sum =
          item.qty *
          item.price;


        total += sum;


        return `

          <div class="invoice-item">

            <div>

              <strong>
                ${escapeHTML(item.name)}
              </strong>

              <div class="product-info">

                ${fa(item.qty)}
                عدد ×
                ${fa(item.price)}
                تومان

              </div>

            </div>


            <div style="text-align:left">

              <strong>
                ${fa(sum)}
                تومان
              </strong>

              <br>

              <button
                class="danger"
                onclick="removeCart(${index})">

                حذف

              </button>

            </div>

          </div>

        `;

      }
    ).join("");


  let discount =
    getDiscount(total);


  let finalTotal =
    Math.max(
      0,
      total - discount
    );


  document.getElementById(
    "cartTotal"
  ).innerHTML =
    fa(finalTotal)
    + " تومان"
    +
    (
      discount > 0
      ?
      `<div style="
        font-size:11px;
        color:#64748b;
        font-weight:normal;
        margin-top:6px
      ">
        جمع:
        ${fa(total)}
        تومان |
        تخفیف:
        ${fa(discount)}
        تومان
      </div>`
      :
      ""
    );

}


function removeCart(index){

  cart.splice(
    index,
    1
  );

  renderCart();

}


function nextInvoiceNumber(){

  let max = 0;


  invoices.forEach(
    inv => {

      let n =
        parseInt(
          String(inv.number)
          .replace(/\D/g,"")
        )
        || 0;


      if(n > max)
        max = n;

    }
  );


  return "SF-"
    + String(max + 1)
      .padStart(5,"0");

}


function getCartSubtotal(){

  return cart.reduce(
    (s,x) =>
      s + (
        x.qty *
        x.price
      ),
    0
  );

}


function getDiscount(subtotal){

  let v =
    Number(
      document
      .getElementById(
        "discountValue"
      )
      ?.value
    )
    || 0;


  let t =
    document
    .getElementById(
      "discountType"
    )
    ?.value
    || "amount";


  if(v < 0)
    v = 0;


  if(t === "percent"){

    v =
      Math.min(
        v,
        100
      );


    return Math.min(
      subtotal,
      Math.round(
        subtotal *
        v /
        100
      )
    );

  }


  return Math.min(
    subtotal,
    Math.round(v)
  );

}


/* ================= SAVE INVOICE ================= */

function saveInvoice(){

  if(!cart.length){

    alert(
      "فاکتور خالی است."
    );

    return;

  }


  for(
    let item of cart
  ){

    let p =
      products.find(
        x =>
          x.id
          === item.productId
      );


    if(!p){

      alert(
        "یکی از کالاها پیدا نشد."
      );

      return;

    }


    if(
      p.stock
      < item.qty
    ){

      alert(
        "موجودی "
        + p.name
        + " کافی نیست."
      );

      return;

    }

  }


  let subtotal =
    cart.reduce(
      (s,x) =>
        s +
        x.qty *
        x.price,
      0
    );


  let discount =
    getDiscount(subtotal);


  let total =
    Math.max(
      0,
      subtotal -
      discount
    );


  let invoice = {

    id:
      Date.now().toString(),

    number:
      nextInvoiceNumber(),

    customer:
      document
      .getElementById(
        "customerName"
      )
      .value
      .trim()
      || "مشتری",

    date:
      document
      .getElementById(
        "saleDate"
      )
      .value
      || today(),

    items:
      JSON.parse(
        JSON.stringify(cart)
      ),

    subtotal:
      subtotal,

    discount:
      discount,

    total:
      total,

    created:
      Date.now()

  };


  cart.forEach(
    item => {

      let p =
        products.find(
          x =>
            x.id
            === item.productId
        );


      p.stock -=
        item.qty;

    }
  );


  invoices.push(
    invoice
  );


  saveData();


  cart = [];


  document.getElementById(
    "customerName"
  ).value = "";


  document.getElementById(
    "saleProduct"
  ).value = "";


  document.getElementById(
    "discountValue"
  ).value = "0";


  document.getElementById(
    "discountType"
  ).value = "amount";


  renderAll();


  showInvoice(
    invoice
  );

}


/* ================= INVOICES ================= */

function renderInvoices(){

  let q =
    (
      document
      .getElementById(
        "invoiceSearch"
      )
      ?.value
      || ""
    )
    .trim()
    .toLowerCase();


  let list =
    document.getElementById(
      "invoiceList"
    );


  let arr =
    invoices
    .filter(
      x =>
        (
          x.number
          + " "
          + x.customer
        )
        .toLowerCase()
        .includes(q)
    )
    .sort(
      (a,b) =>
        b.created -
        a.created
    );


  if(!arr.length){

    list.innerHTML =
      '<div class="empty">هنوز فاکتوری ثبت نشده است.</div>';

    return;

  }


  list.innerHTML =
    arr.map(
      x => `

        <div class="product">

          <div>

            <div class="product-name">

              🧾
              ${escapeHTML(x.number)}

            </div>

            <div class="product-info">

              مشتری:
              ${escapeHTML(x.customer)}
              <br>

              تاریخ:
              ${escapeHTML(x.date)}
              <br>

              تعداد اقلام:
              ${fa(x.items.length)}

            </div>

          </div>


          <div style="text-align:left">

            <strong class="green">

              ${fa(x.total)}
              تومان

            </strong>

            <br><br>

            <button
              class="success"
              onclick="showInvoiceById('${x.id}')">

              مشاهده

            </button>

          </div>

        </div>

      `
    ).join("");

}


function showInvoiceById(id){

  let invoice =
    invoices.find(
      x => x.id === id
    );


  if(invoice)
    showInvoice(invoice);

}


function showInvoice(invoice){

  let area =
    document.getElementById(
      "printArea"
    );


  let rows =
    invoice.items
    .map(
      (item,index) => `

        <tr>

          <td>
            ${index + 1}
          </td>

          <td>
            ${escapeHTML(item.name)}
          </td>

          <td>
            ${fa(item.qty)}
          </td>

          <td>
            ${fa(item.price)}
          </td>

          <td>
            ${fa(
              item.qty *
              item.price
            )}
          </td>

        </tr>

      `
    )
    .join("");


  area.innerHTML = `

    <div class="print-invoice">

      <div class="invoice-paper">

        <div class="invoice-top">

          <div>

            <div class="store-name">
              لوازم التحریر سایه
            </div>

            <div class="store-sub">
              فاکتور فروش کالا
            </div>

          </div>


          <div class="invoice-number">

            <small>
              شماره فاکتور
            </small>

            <strong>
              ${escapeHTML(invoice.number)}
            </strong>

          </div>

        </div>


        <div class="invoice-info">

          <div class="info-box">

            تاریخ

            <strong>
              ${escapeHTML(invoice.date)}
            </strong>

          </div>


          <div class="info-box">

            مشتری

            <strong>
              ${escapeHTML(invoice.customer)}
            </strong>

          </div>

        </div>


        <table class="invoice-table">

          <thead>

            <tr>

              <th>ردیف</th>
              <th>شرح کالا</th>
              <th>تعداد</th>
              <th>قیمت واحد</th>
              <th>مبلغ</th>

            </tr>

          </thead>


          <tbody>

            ${rows}

          </tbody>

        </table>


        <div class="invoice-summary">

          <div class="summary-line">

            <span>
              تعداد اقلام
            </span>

            <span>
              ${fa(invoice.items.length)}
            </span>

          </div>


          <div class="summary-line">

            <span>
              جمع کالاها
            </span>

            <span>
              ${fa(invoice.subtotal ?? invoice.total)}
              تومان
            </span>

          </div>


          <div
            class="summary-line"
            style="color:#15803d">

            <span>
              تخفیف
            </span>

            <span>
              −
              ${fa(invoice.discount || 0)}
              تومان
            </span>

          </div>


          <div class="summary-final">

            <span>
              مبلغ قابل پرداخت
            </span>

            <span>
              ${fa(invoice.total)}
              تومان
            </span>

          </div>

        </div>


        <div class="invoice-footer">

          <div class="signature">
            امضای مشتری
          </div>

          <div class="signature">
            مهر و امضای فروشگاه
          </div>

        </div>

      </div>

    </div>

  `;


  document
  .getElementById(
    "invoiceModal"
  )
  .classList.add("show");

}


function closeInvoiceModal(){

  document
  .getElementById(
    "invoiceModal"
  )
  .classList.remove("show");

}


/* ================= DASHBOARD ================= */

function renderDashboard(){

  let sales =
    invoices.reduce(
      (s,x) =>
        s + x.total,
      0
    );


  let profit = 0;


  invoices.forEach(
    invoice => {

      invoice.items.forEach(
        item => {

          let p =
            products.find(
              x =>
                x.id
                === item.productId
            );


          let buy =
            p
            ? p.buyPrice
            : 0;


          profit +=
            (
              item.price -
              buy
            )
            *
            item.qty;

        }
      );

    }
  );


  let stockValue =
    products.reduce(
      (s,p) =>
        s +
        (
          p.buyPrice *
          p.stock
        ),
      0
    );


  document.getElementById(
    "dashSales"
  ).textContent =
    fa(sales)
    + " تومان";


  document.getElementById(
    "dashProfit"
  ).textContent =
    fa(profit)
    + " تومان";


  document.getElementById(
    "dashProducts"
  ).textContent =
    fa(products.length);


  document.getElementById(
    "dashInvoices"
  ).textContent =
    fa(invoices.length);


  document.getElementById(
    "stockValue"
 
