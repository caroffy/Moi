# Moi<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Kaverilista</title>
    <link rel="stylesheet" type="text/css" href="tyylit/style.css">
</head>
<body>
    <div id="myDIV" class="header">
            <img src="gif/giphy.gif" alt="HTML5 Icon" width="128" height="128">
            <img src="gif/giphy.gif" alt="HTML5 Icon" style="width:128px;height:128px;">
            <img src="gif/giphy.gif" alt="HTML5 Icon" width="128" height="128">
            <img src="gif/giphy.gif" alt="HTML5 Icon" style="width:128px;height:128px;">
            <img src="gif/giphy.gif" alt="HTML5 Icon" width="128" height="128">
            <img src="gif/giphy.gif" alt="HTML5 Icon" style="width:128px;height:128px;">
            <img src="gif/giphy.gif" alt="HTML5 Icon" width="128" height="128">
            <img src="gif/giphy.gif" alt="HTML5 Icon" style="width:128px;height:128px;">
            <img src="gif/giphy.gif" alt="HTML5 Icon" width="128" height="128">
            <img src="gif/giphy.gif" alt="HTML5 Icon" style="width:128px;height:128px;">
            <img src="gif/giphy.gif" alt="HTML5 Icon" width="128" height="128">
            <img src="gif/giphy.gif" alt="HTML5 Icon" style="width:128px;height:128px;">
            <img src="gif/giphy.gif" alt="HTML5 Icon" width="128" height="128">
        <p>Koiret pelkäävät huehue-mörköä, auta koireita listaamalla ystävesi, jotta mörkö katoaa</p>
        <input type="text" id="myInput" placeholder="Kaverin nimi...">
        <span onclick="newElement()" class="addBtn">Lisää ystävä</span>
      </div> 
      <ul id="myUL">
        <li><span class="close">×</span></li> 
      </ul>
    <script src="js/script.js"></script>
</body>
</html>


body {

    background-image: url("https://media.giphy.com/media/2B4PdZHctzB3W/source.gif");

    height: 100%; 
    background-repeat: no-repeat;
    background-size: cover;
    
}
  
  * {
    box-sizing: border-box;
  }
  
  ul {
    margin: 0;
    padding: 0;
  }
  
  ul li {
    cursor: pointer;
    position: relative;
    padding: 12px 8px 12px 40px;
    background: #D8CEF6;
    font-size: 18px;
    transition: 0.2s;
  
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }
  
  ul li:nth-child(odd) {
    background: #A9BCF5;
  }
  

  ul li:hover {
    background: #CEF6F5;
  }

  ul li.checked {
    background: #F8E0EC;
    color: #fff;
    text-decoration: line-through;
  }
  
  ul li.checked::before {
    content: '';
    position: absolute;
    border-color: #fff;
    border-style: solid;
    border-width: 0 2px 2px 0;
    top: 10px;
    left: 16px;
    transform: rotate(45deg);
    height: 15px;
    width: 7px;
  }
  
  .close {
    position: absolute;
    right: 0;
    top: 0;
    padding: 12px 16px 12px 16px;
  }
  
  .close:hover {
    background-color: #819FF7;
    color: white;
  }
  
  .header {
    background-color:#E0ECF8;
    padding: 30px 40px;
    color: #000000;
    text-align: center;
  }
  

  .header:after {
    content: "";
    display: table;
    clear: both;
  }

  input {
    border: none;
    width: 75%;
    padding: 10px;
    float: left;
    font-size: 16px;
  }
  
  .addBtn {
    padding: 10px;
    width: 25%;
    background: #A9BCF5;
    color: #FFFFFF;
    float: left;
    text-align: center;
    font-size: 16px;
    cursor: pointer;
    transition: 0.3s;
  }
  
  .addBtn:hover {
    background-color: #A9E2F3
  }
  
  
var myNodelist = document.getElementsByTagName("LI");
var i;
for (i = 0; i < myNodelist.length; i++) {
  var span = document.createElement("SPAN");
  var txt = document.createTextNode("\u00D7");
  span.className = "close";
  span.appendChild(txt);
  myNodelist[i].appendChild(span);
}

var close = document.getElementsByClassName("close");
var i;
for (i = 0; i < close.length; i++) {
  close[i].onclick = function() {
    var div = this.parentElement;
    div.style.display = "none";
  }
}

var list = document.querySelector('ul');
list.addEventListener('click', function(ev) {
  if (ev.target.tagName === 'LI') {
    ev.target.classList.toggle('checked');
  }
}, false);

function newElement() {
  var li = document.createElement("li");
  var inputValue = document.getElementById("myInput").value;
  var t = document.createTextNode(inputValue);
  li.appendChild(t);
  if (inputValue === '') {
    alert("Kirjoita ystävän nimi!");
  } else {
    document.getElementById("myUL").appendChild(li);
  }
  document.getElementById("myInput").value = "";

  var span = document.createElement("SPAN");
  var txt = document.createTextNode("\u00D7");
  span.className = "close";
  span.appendChild(txt);
  li.appendChild(span);

  for (i = 0; i < close.length; i++) {
    close[i].onclick = function() {
      var div = this.parentElement;
      div.style.display = "none";
    }
  }
}


  
