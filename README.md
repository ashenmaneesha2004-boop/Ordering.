
<html lang="en">
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Edirisingha Food Cabin</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Segoe UI',sans-serif;
}

body{
background:#fff7f0;
}


/* Banner */

.hero{
background:linear-gradient(135deg,#2b160b,#b84a00);
color:white;
text-align:center;
padding:45px 15px;
}

.hero h1{
font-size:32px;
}

.hero p{
margin-top:8px;
}


/* Order Box */

.order-box{
width:95%;
max-width:450px;
background:white;
margin:20px auto;
padding:18px;
border-radius:18px;
box-shadow:0 6px 20px rgba(0,0,0,.12);
}


.title{
text-align:center;
color:#7a2600;
font-size:22px;
margin-bottom:18px;
}



/* Food Card */

.food-card{
background:#fff0e6;
padding:12px;
margin:12px 0;
border-radius:14px;
display:flex;
align-items:center;
justify-content:space-between;
}


.food-left{
display:flex;
align-items:center;
flex:1;
}


.food-icon{
width:55px;
height:55px;
border-radius:50%;
background:white;
display:flex;
align-items:center;
justify-content:center;
font-size:30px;
margin-right:12px;
}



.food-info h3{
font-size:17px;
color:#3b1b0b;
}


.price{
font-size:15px;
font-weight:bold;
color:#b84a00;
}



/* Quantity */

.qty{
display:flex;
align-items:center;
gap:8px;
}


.qty button{
width:34px;
height:34px;
border-radius:50%;
border:none;
background:#b84a00;
color:white;
font-size:20px;
font-weight:bold;
}


.qty span{
width:25px;
text-align:center;
font-size:18px;
font-weight:bold;
}



/* Summary */

.summary{
background:#fff7f0;
padding:15px;
border-radius:15px;
margin-top:20px;
}


.summary h3{
color:#7a2600;
margin-bottom:10px;
}


.total{
text-align:center;
font-size:22px;
font-weight:bold;
color:#7a2600;
margin:15px;
}



/* Inputs */

input,select,textarea{
width:100%;
padding:10px;
margin:6px 0;
border-radius:10px;
border:1px solid #ddd;
}



/* Button */

.confirm{
width:100%;
padding:14px;
background:#2b160b;
color:white;
border:none;
border-radius:12px;
font-size:16px;
font-weight:bold;
}



/* Confirmation */

.confirm-box{
display:none;
background:#e8fff0;
border:2px solid #28a745;
padding:20px;
border-radius:18px;
text-align:center;
margin-top:20px;
}


.confirm-box h2{
color:#198754;
}



footer{
text-align:center;
padding:15px;
color:#777;
}

</style>

</head>


<body>


<div class="hero">

<h1>🍽️ Edirisingha Food Cabin</h1>

<p>Fresh Sri Lankan Hoppers • Pickup Only</p>

</div>




<div class="order-box">


<h2 class="title">
Place Your Pickup Order
</h2>




<div class="food-card">


<div class="food-left">

<div class="food-icon">
🍳
</div>


<div class="food-info">

<h3>Egg Hopper</h3>

<p class="price">Rs.100</p>

</div>

</div>



<div class="qty">

<button onclick="changeQty('egg',-1)">−</button>

<span id="egg">0</span>

<button onclick="changeQty('egg',1)">+</button>

</div>


</div>






<div class="food-card">


<div class="food-left">

<div class="food-icon">
🥞
</div>


<div class="food-info">

<h3>Plain Hopper</h3>

<p class="price">Rs.25</p>

</div>

</div>



<div class="qty">

<button onclick="changeQty('plain',-1)">−</button>

<span id="plain">0</span>

<button onclick="changeQty('plain',1)">+</button>

</div>


</div>





<div class="summary">

<h3>Order Summary</h3>

<p id="summary">
No items selected
</p>

</div>



<div class="total">

Total Rs. <span id="total">0</span>

</div>





<input id="name" placeholder="Customer Name">

<input id="phone" placeholder="Phone Number">



<select>

<option>Select Pickup Time</option>

<option>Ready Now</option>

<option>15 Minutes</option>

<option>30 Minutes</option>

<option>1 Hour</option>

</select>



<textarea placeholder="Special Request"></textarea>




<button class="confirm" onclick="placeOrder()">

Confirm Pickup Order

</button>




<div class="confirm-box" id="confirmBox">

<h2>🎉 Order Confirmed!</h2>

<br>

<p>Pickup Order No</p>

<h2 id="orderNo"></h2>

<p>Total Rs.<span id="finalTotal"></span></p>

<br>

<p>Please collect your order at the counter.</p>

</div>



</div>




<footer>

© 2026 Edirisingha Food Cabin

</footer>




<script>

let egg=0;
let plain=0;


function changeQty(item,value){


if(item=="egg"){

egg+=value;

if(egg<0) egg=0;

}


if(item=="plain"){

plain+=value;

if(plain<0) plain=0;

}


document.getElementById("egg").innerHTML=egg;

document.getElementById("plain").innerHTML=plain;



let total=(egg*100)+(plain*25);

document.getElementById("total").innerHTML=total;



let text="";


if(egg>0){

text+="🍳 Egg Hopper x "+egg+" = Rs."+egg*100+"<br>";

}


if(plain>0){

text+="🥞 Plain Hopper x "+plain+" = Rs."+plain*25;

}


if(text==""){

text="No items selected";

}


document.getElementById("summary").innerHTML=text;


}




function placeOrder(){


let total=document.getElementById("total").innerHTML;


if(total=="0"){

alert("Please select items");

return;

}


let orderNo="EFC-"+Math.floor(1000+Math.random()*9000);


document.getElementById("confirmBox").style.display="block";

document.getElementById("orderNo").innerHTML=orderNo;

document.getElementById("finalTotal").innerHTML=total;


}

</script>


</body>
</html>
