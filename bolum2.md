HTML KODU;
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Responsive Design</title>
	<link rel="stylesheet" href="style.css"/>
</head>
<body>
	<img id="responsiveResim" src="kozalak.jpg"/>
</body>
</html>

```
CSS Kodu;
```CSS
* { margin:0px; padding:0px; }
```
**Bu bölümde 1 nolu referans resim kullanılacak.**

---

HTML Kodu;
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Responsive Design</title>
	<link rel="stylesheet" href="style.css"/>
</head>
<body>
	<img id="calcResim" src="kozalak.jpg"/>
</body>
</html>
```
CSS Kodu;
```CSS
* { margin:0px; padding:0px; }
#calcResim { width:calc(100% - 120px); }
```
**Bu bölümde 6 nolu referans resim kullanılacak.**

---


HTML Kodu;
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Responsive Design</title>
	<link rel="stylesheet" href="style.css"/>
</head>
<body>
	<div class="kolon1">1. kolon</div>
	<div class="kolon2">2. kolon</div>
</body>
</html>

```
CSS Kodu;
```CSS
* { margin:0px; padding:0px; }
.kolon1 { border-right:1px solid #eee; padding:10px; float:left;
          width:calc(30% - 21px);
          height:calc(100% - 20px); }

.kolon2 { padding:10px; float:right;
          width:calc(70% - 20px);
          height:calc(100% - 20px);}
```
**Bu bölümde 8 nolu referans resim kullanılacak.**

---



HTML Kodu;
```HTML
<!-- HTML kodu bir önceki örnek ile tamamen aynı. -->

```
CSS Kodu;
```CSS
* { margin:0px; padding:0px; }
.kolon1 { box-sizing: border-box; border-right:1px solid #eee;
          padding:10px; float:left;
          width:30%;
          height:100%; }

.kolon2 { box-sizing: border-box; padding:10px; float:right;
          width:70%;
          height:100%;}

```
**Bu kodlar bir önceki örnek ile aynı çıktıyı alır.**


---


CSS Kodu;
```CSS
.kolon { box-sizing: border-box;
         -moz-box-sizing: border-box;
         -webkit-box-sizing: border-box; }
```

---



HTML Kodu;
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Responsive Design</title>
	<link rel="stylesheet" href="style.css"/>
</head>
<body>
	<img id="kozalakResim" src="kozalak.jpg"/>
</body>
</html>
```
CSS Kodu;
```CSS
* { margin:0px; padding:0px;}
 #kozalakResim { width:100%; max-width:500px; }

```
**Bu bölümde 16 nolu referans resim kullanılacak.**


---


HTML Kodu;
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Responsive Design</title>
	<link rel="stylesheet" href="style.css"/>
	<script type="text/javascript" src="script.js"></script>
</head>
<body>
	<img id="kozalakResim" src="kozalak.jpg"/>
</body>
</html>

```
CSS Kodu;
```CSS
* { margin:0px; padding:0px;}
```
Javascript Kodu;
```JS
window.onload = function(){
     document.getElementById("kozalakResim").style.width = "200px";
}

```
**Bu bölümde 10 nolu referans resim kullanılacak.**

---


JS Kodu;
```JS
window.onload = function(){
	var ekranGenisligi = window.innerWidth;
      // var ekranGenisligi = window.outerWidth;

       document.getElementById("kozalakResim").style.width = ekranGenisligi;
}
```
**Bu bölümde 11 nolu referans resim kullanılacak.**


---


JS Kodu:
```JS
window.onload = function(){
	var ekranGenisligi = window.innerWidth;
	var ekranYuksekligi = window.innerHeight;

       document.getElementById("kozalakResim").style.width = ekranGenisligi * 0.5;
       document.getElementById("kozalakResim").style.height = ekranYuksekligi * 1;
}
```
**Bu bölümde 12 nolu referans resim kullanılacak.**

---


JS Kodu;
```JS
function updateStyle(){
	var ekranGenisligi = window.innerWidth;
	var ekranYuksekligi = window.innerHeight;

       document.getElementById("kozalakResim").style.width = ekranGenisligi * 0.5;
       document.getElementById("kozalakResim").style.height = ekranYuksekligi * 1;
}

window.onload = updateStyle;
window.onresize = updateStyle;
```

**Örneğimizin çıktısı CSS ile aynı işlevsel çıktıyı verecek.**

---

JS Kodu;		           							 
```JS
function updateStyle(){
	var ekranGenisligi = window.innerWidth;

       document.getElementById("kozalakResim").style.width = ekranGenisligi - 100;
}

window.onload = updateStyle;
window.onresize = updateStyle;
```

**Bu bölümde 14 nolu referans resim kullanılacak.**

---


JS Kodu;
```JS
function updateStyle(){
	var ekranGenisligi = window.innerWidth;
	var resimGenisligi = 0;
	if(ekranGenisligi < 500){
		resimGenisligi = ekranGenisligi;
	}else{
		resimGenisligi = 500;
	}
    document.getElementById("kozalakResim").style.width = resimGenisligi;
}

window.onload = updateStyle;
window.onresize = updateStyle;
```
**Bu bölümde 19 nolu referans resim kullanılacak.**
