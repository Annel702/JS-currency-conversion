# JS-currency-conversion
HTML, CSS, and javascript rounded button currency converter 


<!DOCTYPE html>
<html lang="en">
    <head>
      <title>CHOOSE CURRENCY TO CONVERT</title>
      <link rel="stylesheet" href="style.css">
      <script src="currency.js"></script>
      <svg viewBox="0 0 512 512" width="100" title="coins">
  <path d="M0 405.3V448c0 35.3 86 64 192 64s192-28.7 192-64v-42.7C342.7 434.4 267.2 448 192 448S41.3 434.4 0 405.3zM320 128c106 0 192-28.7 192-64S426 0 320 0 128 28.7 128 64s86 64 192 64zM0 300.4V352c0 35.3 86 64 192 64s192-28.7 192-64v-51.6c-41.3 34-116.9 51.6-192 51.6S41.3 334.4 0 300.4zm416 11c57.3-11.1 96-31.7 96-55.4v-42.7c-23.2 16.4-57.3 27.6-96 34.5v63.6zM192 160C86 160 0 195.8 0 240s86 80 192 80 192-35.8 192-80-86-80-192-80zm219.3 56.3c60-10.8 100.7-32 100.7-56.3v-42.7c-35.5 25.1-96.5 38.6-160.7 41.8 29.5 14.3 51.2 33.5 60 57.2z" />
</svg>
    </head>
  
      <body>
        <div class="container">
          <h1> CURRENCY CONVERSION</h1>
          <div class="box"> 
            <div class="left-box">
              <select name="currency" class="currency"></select>
              <input type="number" name="" id="num"> </div>
            
            <div class="right-box">
              <select name="currency" class="currency"</select>
              <input type="text" name="" id="answer"></div></div>
          <button class="btn" id="btn">CONVERT</button></div>
        
      </div>    
</html>




*{
  margin: 100;
  padding: 80;
  box-sizing: border-box;
}

body {
  height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #6960EC;
}
.container{
  width: 450px;
}
h1 {
  color: #05d9e8;
  margin-bottom: 0.5em;
}
.container .box{
  width: 100%;
  display: flex;
}
.box div{
  width: 100%;
}
select {
  width: 95%;
  height: 40px;
  font-size: 1em;
  outline: none;
  background: #FF2281;
  color: #00FFC0;
  margin: 0.2em 0;
  padding: 0 1em;
  border-radius: 10px;
  border: none;
  
}
input {
  width: 95%;
  height: 40px;
  font-size: 1em;
  margin: 0.2em 0;
  border-radius: 10px;
  background: #CCCCFF;
  padding: 0 1em;
}

.btn{
  width: 98%;
  background: #4D4DFF;
  color: #B3B3FF;
  border-radius: 10px;
  border: none;
  font-size: 1em;
  margin: 0.5em 0;
}


.wrapper {
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    justify-content: center;
}

.wrapper h1 {
    margin-bottom: 30px;
    color: #F7A579;
}
.wrapper form {
    display: flex;
}

.wrapper form input,
.wrapper form select {
    border: 80;
    background: #06114F;
    padding: 80px;
    color: #F7A579;
}
.wrapper form input:not(:last-child),
.wrapper form select:not(:last-child) {
    margin-right: 50px;
}

.wrapper form input:focus,
.wrapper form select:focus {
    outline: 10;
}



.wrapper form option:checked {
    background: #9C89FF;
}

.wrapper p,
.wrapper span {
    color: #C71585;
}


const select = document.querySelectorAll('.currency');
const btn = document.getElementById('btn');
const num = document.getElementById('num');
const ans = document.getElementById('ans');
    // Send a GET request to the URL
    fetch('https://api-public.sandbox.exchange.coinbase.com=SOL')
    // Put response into json form
    .then((data) => data.json())
    .then(data => {
      display(data);
    });


function display(data){
  const entries = Object.entries(data);
  console.log(entries.length)
  for(var i = 0; i < entries.length; i++){
    select[0].innerHTML += '<option value="${entries[i][0]}">${entries[i][0]}</option>';
    select[1].innerHTML += '<option value="${entries[i][0]}">${entries[i][0]}</option>';
}
    
          
           function convert(currency1, currency2, value){
             const host= 'api-public.sandbox.exchange.coinbase.com';
         fetch('https://${host}/latest?amount=${value}&from=${currency1}&to=${currency2}')
             .then((val) => val.json())
             .then((val) =>{
           console.log(Object.values(val .rates[0]);
                       ans.value = Object.values(val.rates)[0];
         }
           }
