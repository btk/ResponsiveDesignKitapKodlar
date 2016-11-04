HTML Kodu			           							 
```HTML
<body>
	<div class="icerik">
	<p>Lorem ipsum dolor sit amet, ……</p>
	<p>Aenean quis odio magna. Integer ……</p>
	 </div>
</body>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.icerik { font: 15px Arial, sans-serif;  padding:10px; }
```
**Bu bölümde 2 nolu referans resim kullanılacak.**


---



CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.icerik { font: 14px Tahoma, sans-serif;  padding:10px;}
.icerik p {padding-bottom:20px; }
```
**Bu bölümde 3 nolu referans resim kullanılacak.**


---



```HTML
<!-- Önceki örnek ile aynı HTML kodları -->
```
CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.icerik { font: 14px Tahoma, sans-serif;  padding:10px; line-height:25px/1.5em;}
.icerik p {padding-bottom:20px; }
```
**Bu bölümde 4 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
<!-- Önceki örnek ile aynı HTML kodları -->
```
CSS Kodu		
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.icerik { font: 14px Tahoma, sans-serif;  padding:10px; line-height:1.6em;
          letter-spacing: 0.5px / 1px / -0.3px / 1em; }
.icerik p {padding-bottom:20px; }
```
**Bu bölümde 5 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
<!-- Önceki örnek ile aynı HTML kodları -->
```
CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.icerik { font: 14px Tahoma, sans-serif;  padding:10px; line-height:1.6em;
          letter-spacing: -0.2px; word-spacing: 1px / 7px; }
.icerik p {padding-bottom:20px;}
```
**Bu bölümde 7 nolu referans resim kullanılacak.**


---




HTML Kodu
```HTML
<body>
	<div class="icerik">
	<p><span class="kalin">Lorem ipsum</span> dolor sit amet, ……</p>
	<p><span class="italik">Aenean quis</span> odio magna. Integer ……</p>
	 </div>
</body>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.icerik { font: 14px Open Sans, sans-serif;  padding:10px; line-height:1.6em;
          letter-spacing:-0.3px;  }
.kalin { font-weight:bold; }
.italik { font-style:italic; }
.icerik p {padding-bottom:20px; }
```
**Bu bölümde 6 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
<body>
	<div class="icerik">
	<p><span class="altcizgi">Lorem ipsum</span> dolor sit amet, ……</p>
	<p><span class="buyuk">Aenean quis</span> odio magna. Integer ……</p>
	 </div>
</body>
```

CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.icerik { font: 14px Open Sans, sans-serif;  padding:10px; line-height:1.6em;
          letter-spacing:-0.3px;  }
.altcizgi { text-decoration: underline; }
/* Ayrıca overline ve line-through da kullanılabilir */
.buyuk { text-transform: uppercase; }
/* Ayrıca baş harfi büyük yapmaya yarayacan capitalize veya tamamını küçülten lowercase kullanılabilir. */
.icerik p {padding-bottom:20px; }
```
**Bu bölümde 8 nolu referans resim kullanılacak.**


---




HTML Kodu			           							 
```HTML
<body>
	<div class="icerik">
	<p><span class="altcizgi">Lorem ipsum</span> dolor sit amet, ……</p>
	<p><span class="buyuk">Aenean quis</span> odio magna. Integer ……</p>
	 </div>
</body>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.icerik { font: 14px Open Sans, sans-serif;  padding:10px; line-height:1.6em;
          letter-spacing:-0.3px; text-align: justify; text-justify:inner-word; }
.icerik p {padding-bottom:20px; }
```
**Bu bölümde 9 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
<body>
	<div class="icerik">
	<p>Lorem ipsum dolor sit amet, ……</p>
	<p>Aenean quis odio magna. Integer ……</p>
	 </div>
</body>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.icerik { font: 16px Open Sans, sans-serif;  padding:10px; line-height:1.6em;
          letter-spacing:-0.3px; }
.icerik p {padding-bottom:20px; }
@media all and (max-width: 400px){
	.icerik { font-size:14px; letter-spacing:-0.4px; word-spacing:0.1px; }
}
```
**Bu bölümde 10 nolu referans resim kullanılacak.**


---



HTML Kodu			           							 
```HTML
<body>
	<div class="icerik">
	<p>Lorem ipsum dolor sit amet, ……</p>
	<p>Aenean quis odio magna. Integer ……</p>
	 </div>
</body>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.icerik { font-family: Open Sans, sans-serif;  padding:10px; font-size:18px;
	line-height: 1.6em;
       letter-spacing: 0.03em;
	word-spacing: 0.2em;
	}
.icerik p {padding-bottom:20px; }
```
JS Kodu			
```JS
function updateYaziBoyut(){
	var ekranGenisligi = window.innerWidth;
	var icerik = document.getElementsByClassName("icerik");
	if(ekranGenisligi> 1000){
	    icerik[0].style.fontSize = "20px";
	}else if(ekranGenisligi <= 1000 && ekranGenisligi > 400){
	     icerik[0].style.fontSize = parseFloat(14 + ((ekranGenisligi - 400) * 6)/600) + "px";
	}else{
	    icerik[0].style.fontSize = "12px";
	}
}

window.onload = updateYaziBoyut;
window.onresize = updateYaziBoyut;
```
**Bu bölümde 11 nolu referans resim kullanılacak.**
