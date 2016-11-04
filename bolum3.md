
HTML Kodu        							 
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Responsive Design</title>
	<link rel="stylesheet" href="style.css"/>
</head>
<body>
    <div class="kolon1">İlk kolon içeriği</div>
    <div class="kolon2">İkinci kolon içeriği</div>
</body>
</html>
```

CSS Kodu
```CSS
* { margin:0px; padding:0px; }
.kolon1 { width:calc(30% - 2px); border-right:1px solid #ccc;
          float:left; font-size:40px; height:100%; background:#eee;}
.kolon2 { width:70%; border-right:1px solid #ccc; float:right;
          font-size:40px;  height:100%; background:#aaa;}
```

**Bu bölümde 1 nolu referans resim kullanılacak.**

---

HTML Kodu;			           							 
```HTML
<head> 	
   <meta name="viewport" content="width=device-width, initial-scale=2">
</head>
```
**Bu bölümde 4 nolu referans resim kullanılacak.**

---

HTML Kodu;			           							 
```HTML
<head> 	
   <meta name="viewport" content="width=device-width, user-scalable=no">
</head>
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
    İçerik!
</body>
</html>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body  { background:#ccc; }
@media all and (max-width: 400px){
	body  { background:#555; }
}
```
**Bu bölümde 6 nolu referans resim kullanılacak.**

---

CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body  { background:#ccc; }
@media all and (min-width: 400px){
	body  { background:#555; }
}
```
**Bu bölümde 7 nolu referans resim kullanılacak.**

---


HTML Kodu
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Responsive Design</title>
	<link rel="stylesheet" href="style.css"/>
</head>
<body>
    	<div class="satir satir1">Satır 1</div>
	<div class="satir satir2">Satır 2</div>
	<div class="satir satir3">Satır 3</div>
	<div class="satir satir4">Satır 4</div>
</body>
</html>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body  { background:#fff; }
.satir  { width:100%; height:50px; border-bottom:1px solid #999;
         line-height:50px; }
.satir1 { background:#ccc; }
@media all and (min-width:400px){
	.satir2 { background:#ccc; }
}
@media all and (min-width:600px){
	.satir3 { background:#ccc; }
}
```
**Bu bölümde 11 nolu referans resim kullanılacak.**

---

CSS Kodu			           							 
```CSS
* { margin:0px; padding:0px;}
body  { background:#fff; }
.satir  { width:100%; height:50px; border-bottom:1px solid #999;
         line-height:50px; }
.satir1 { background:#ccc; }
@media all and (min-width:400px) and (max-width:600px){
	.satir2 { background:#ccc; }
}
@media all and (min-width:600px){
	.satir3 { background:#ccc; }
}
```
**Bu bölümde 12 nolu referans resim kullanılacak.**

---


CSS Kodu			           							 
```CSS
* { margin:0px; padding:0px;}
@media handheld and (orientation:landscape) {...}
@media handheld and (orientation:portrait) {...}
```

---

CSS Kodu
```CSS
* { margin:0px; padding:0px;}
@media screen and (device-width: 960px) {...}
```

---

CSS Kodu		
```CSS
* { margin:0px; padding:0px;}
@media screen and (max-device-width: 960px) {...}
```

---

CSS Kodu		
```CSS
* { margin:0px; padding:0px;}
@media screen and (device-aspect-ratio: 16/9) { … }
@media screen and (device-aspect-ratio: 32/18) { … }
@media screen and (device-aspect-ratio: 1280/720) { … }
@media print and (resolution: 300dpi) { … }
@media print and (min-resolution: 290dpi) { … }
```

---
