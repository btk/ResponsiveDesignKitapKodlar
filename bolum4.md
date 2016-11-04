
HTML Kodu
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Yan Bölüm – Asıl Bölüm</title>
       <meta name="viewport" content="width=device-width">
	<link rel="stylesheet" href="style.css"/>
</head>
<body>
	<div class="tasiyici">
	     <div class="solbolum">SolBölüm İçeriği</div>
	     <div class="asilbolum">AsılBölüm İçeriği</div>
	</div>
</body>
</html>
```

CSS Kodu
```CSS
* { margin:0px; padding:0px; }
.tasiyici { position:relative; width:100%; max-width:1000px;  margin:auto; }
.solbolum { width:calc(30% - 1px); background:#eee; height:100%;
            border-right: 1px solid #888; float:left; }
.asilbolum { width:70%; background:#ddd; float:right; height:100%; }
.temizle { clear:both; }
```


---


CSS Kodu
```CSS
/* Onceki Ornek ile ayni CSS kodları */
@media all and (max-width: 500px){
	.solbolum { width: 100%; border-right:0px; max-height:200px;
                               border-bottom:1px solid #888; float:none; }
	.asilbolum { width: 100%; float:none; }
}
```
**Bu bölümde 2 nolu referans resim kullanılacak.**


---



HTML Kodu			           							 
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Tam Duyarlı Bloklar</title>
       <meta name="viewport" content="width=device-width">
	<link rel="stylesheet" href="style.css"/>
</head>
<body>
	<div class="blok">Blok 1</div>
	<div class="blok">Blok 2</div>
	<div class="blok">Blok 3</div>
	<div class="blok">Blok 4</div>
</body>
</html>
```

CSS Kodu
```CSS
* { margin:0px; padding:0px; }
.blok{ width:calc(25% - 2px); border:1px dashed #ccc; background:#eee;
	float:left;  min-height:100px; }
@media all and (max-width: 600px){
	.blok {width: calc(50% - 2px); }
}
@media all and (max-width: 360px){
	.blok {width: calc(100% - 2px); }
}
```
**Bu bölümde 3 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Yan Bölüm – Asıl Bölüm (Aç/kapa)</title>
	<link rel="stylesheet" href="style.css"/>
       <meta name="viewport" content="width=device-width">
	<script type="text/javascript" src="script.js"></script>
</head>
<body>
	<div class="tasiyici">
		<div class="ackapa" onclick="ackapa()">Aç/kapa</div>
	     <div class="solbolum">SolBölüm İçeriği</div>
	     <div class="asilbolum">AsılBölüm İçeriği</div>
	</div>
</body>
</html>
```

CSS Kodu			           							 
```CSS
* { margin:0px; padding:0px; }
.tasiyici { position:relative; width:100%; max-width:1000px;  margin:auto; }
.solbolum { width:calc(30% - 1px); background:#eee; height:100%;
            border-right: 1px solid #888; float:left; }
.asilbolum { width:70%; background:#ddd; float:right; height:100%; }
.ackapa { display:none;  position:fixed; top:0px; left:0px;
	     padding:10px;  z-index:99; background:#fff;}
@media all and (max-width: 500px){
	.solbolum  { width: 100%; border-right:0px; max-height:200px;
                   border-bottom:1px solid #888; float:none;
       	      display:none; position:fixed; top:40px; left:0px; }
	.ackapa     { display:block; }
	.asilbolum { width: 100%; float:none; }
}
```

JS Kodu			           								 
```JS
var yanBolumDurum = 0;
var solbolum = document.getElementsByClassName("solbolum");
function ackapa(){
	if(yanBolumDurum == 1){
	    solbolum[0].style.display = "none";
	    yanBolumDurum = 0;
	}else{
          solbolum[0].style.display = "block";
	    yanBolumDurum = 1;
	}
}
```
**Bu bölümde 4 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
<!-- HTML kodları bir önceki örnek ile aynı -->
```
CSS Kodu
```CSS
* { margin:0px; padding:0px; }
.tasiyici { position:relative; width:100%; max-width:1000px;  margin:auto; }
.solbolum { width:calc(30% - 1px); background:#eee; height:100%;
                   border-right: 1px solid #888; float:left; }
.asilbolum { width:70%; background:#ddd; float:right; height:100%; }
.ackapa { display:none;  position:fixed; top:0px; left:0px;
	     padding:10px;  }
@media all and (max-width: 500px){
	.solbolum  { width: 100%; border-right:0px; max-height:200px;
                               border-bottom:1px solid #888; float:none;
		         left:-100%; position:fixed; top:50px;
		         transition:500ms left; }
	.ackapa     { display:block; }
	.asilbolum { width: 100%; float:none; }
}
```
JS Kodu			           								 
```JS
var yanBolumDurum = 0;
var solbolum = document.getElementsByClassName("solbolum");
function ackapa(){
	if(yanBolumDurum){
	    solbolum[0].style.left = "-100%";
	    yanBolumDurum = 0;
	}else{
	    solbolum[0].style.left = "0px";
	    yanBolumDurum = 1;
	}
}
```
**Bu bölümde 6 nolu referans resim kullanılacak.**


---




HTML Kodu
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Navigasyon Menüsü (Aç/kapa)</title>
       <meta name="viewport" content="width=device-width">
	<link rel="stylesheet" href="style.css"/>
	<script type="text/javascript" src="script.js"></script>
</head>
<body>
	<div class="tasiyici">
		<div class="ackapa" onclick="ackapa()">Aç/kapa</div>
	     <div class="nav">
		<ul>
		  <li>Anasayfa</li>
		  <li>Patates Sayfası</li>
		  <li>Domates Sayfası</li>
		  <li>Patlıcan Sayfası</li>
		</ul>
	         <div class="temizle"></div>
                </div>
	     <div class="solbolum">SolBölüm İçeriği</div>
	     <div class="asilbolum">AsılBölüm İçeriği</div>
	</div>
</body>
</html>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px; }
.tasiyici { position:relative; width:100%; max-width:1000px;  margin:auto; }
.solbolum { width:calc(30% - 1px); background:#eee; height:100%;
                   border-right: 1px solid #888; float:left; }
.asilbolum { width:70%; background:#ddd; float:right; height:100%; }
.nav { height:50px; border-bottom:1px solid #eee; }
.nav li { float:left; padding:5px; border:1px dashed #ccc;}
.temizle { clear:both; }
.ackapa { display:none;  position:fixed; top:0px; right:0px;
	     padding:10px; background:#fff; border:1px solid #eee; }
@media all and (max-width: 500px){
	.solbolum  { width: 100%; border-right:0px; min-height:300px;
                               border-bottom:1px solid #888; float:none; }
	.nav { display:none; height:auto; }
	.nav li { display:block; float:none; }
	.ackapa { display:block; }
	.asilbolum { width: 100%; float:none; }
}
```
JS Kodu			           								 
```JS
var navDurum = 0;
var nav = document.getElementsByClassName("nav");
function ackapa(){
	if(navDurum){
	    nav[0].style.display = "none";
	    navDurum = 0;
	}else{
	    nav[0].style.display = "block";
	    navDurum = 1;
	}
}
```
**Bu bölümde 7 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Tek / Çift Kolon Yapısı</title>
       <meta name="viewport" content="width=device-width">
	<link rel="stylesheet" href="style.css"/>
	<script type="text/javascript" src="script.js"></script>
</head>
<body>
	<div class="tasiyici">
		<div class="satir">
			<div class="sutun-sol"><img src="patates.png"/></div>
			<div class="sutun-sag"><p><b>Patates</b> (Solanum tuberosum), patlıcangiller (Solanaceae) familyasından yumruları yenen otsu bitki türüdür………</p></div>
		</div>
		<div class="temizle"></div>
		<div class="satir">
			<div class="sutun-sol"><img src="patlican.png"/></div>
			<div class="sutun-sag"><p><b>Patlıcan</b>, bilimsel adıyla Solanum melongena, Solanaceae familyasına ait olup, ılık iklimlerde tek yıllık……… </p></div>
             </div>
	</div>
</body>
</html>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px; }
.tasiyici { position:relative; width:100%; max-width:1000px;  margin:auto; }
.temizle { clear:both; }
.satir { display:block; }
.sutun-sol  { float:left; width:calc(50% - 2px);
              background:#eee; border:1px dashed #ccc; }
.sutun-sag  { float:right; width:calc(50% - 2px);
              background:#eee; border:1px dashed #ccc; }
/* Örneğin çıktısında media kodu olmadan ve media kodu varken 2 farklı çıktı arasındaki farkları inceleyebilirsiniz. */
@media all and (max-width: 400px){
	.sutun-sol  { float:none; width:calc(100% - 2px); text-align:center; }
	.sutun-sag  { float:none; width:calc(100% - 2px);  text-align:center; }
}
```
**Bu bölümde 8 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Responsive Slider Arayüzü</title>
       <meta name="viewport" content="width=device-width">
	<link rel="stylesheet" href="style.css"/>
	<script type="text/javascript" src="script.js"></script>
</head>
<body>
<div class="sliderTasiyici">
<div class="sliderIc">
	<ul>
	  <li><img src="img/1.jpg" title="Sisli Tahta Yol"/></li>
	  <li><img src="img/2.jpg" title="Pembe Güller ve Çiğ"/></li>
	  <li><img src="img/3.jpg" title="Yeşil Orman Bataklığı"/></li>
	</ul>
	<!-- HTML sayfamız ile aynı klasör içindeki img/ klasöründe 1600x1080 boyutlarında 1-2-3.jpg isimli resim dosyalarımız bulunuyor. -->
	<div id="holder"></div>
	<div class="clear"></div>
	<div class="altBolum">
	  <span id="resimBaslik">Pembe Güller ve Çiğ</span>
	  <span class="begeni"><span class="kalp">&#10084;</span> 1,521 Beğeni</span>
	</div>
<!-- altBolum divi içerisinde, önde bulunan resmin adı ve resmin aldığı beğeni sayısını, resmin geçerli boyutu ile aynı genişlikte sunacağız. -->
</div>
</div>
</body>
</html>
```
CSS Kodu
```CSS
/*
Author: Burak Tokak
Github: https://github.com/BurakTokak/SliderUI-Responsive
Projenin tamamlanmış halini github’da bulabilirsiniz.
*/
* { margin:0px; padding:0px;}
body, html  { font-family:"Open Sans", sans-serif; color:#ddd; }
.sliderTasiyici { width:100%; height:100%; background-size:cover;
                  background-position:center; }
/* sliderTasiyici elementinin arkaplan resmi boyutlandırmasını cover olarak atadık, bu sayede Javascript üzerinde bu div için arkaplan atadığımızda her resim için boş alan kalmadan arkaplan gösterilebilir olacak */

.sliderIc { background-color:rgba(30,30,30,0.90);
            height:calc(100% - 100px); padding:50px; }
.sliderIc ul { position:relative; }
.sliderIc li { list-style:none; width:60%; position:absolute;
               opacity:0.8;}
.sliderIc img { width:100%;
              box-shadow: 0px 0px 15px 0px rgba(20,20,20,0.85); }
/* SliderIc div’i içindeki li elementlerinin genişliklerini 60% değerine eşitledik, div içindeki 3 resim elementi de sliderTasiyici div’i içindei ul elementine 0.6 oranla boyut alacak.*/
.clear { clear:both; }
	.aktif { z-index:99; width:75% !important; opacity:1 !important; }
/* Öne çıkan resmin içinde olacağı li elementine Javascript üzerinde aktif className değeri vereceğiz, burada da aktif list elementinin genişliğini 60%’dan 75%’ye çıkartıyoruz, öne çıkan resim çıktılarda gördüğünüz gibi diğer elementlerden daha büyük.*/

	.aktif img {  box-shadow: 0px 0px 20px 0px rgba(20,20,20,0.85);}
	.aktif-sol { left:20px;  }
	.aktif-sag { right:20px; }
/* Aktif li elementinin sağında ve soğunda olan list elementleri için de aktif-sol ve aktif-sag classNameleri atıyoruz. Bu elementler için Javascript üzerinde boyutlandırma ve konumlandırma yapacağız. */
	.altBolum { padding-top:10px; margin:auto;}
#resimBaslik { float:left; font-size:21px; font-weight:500;  
padding-left:20px; letter-spacing:0.5px; }
	.begeni { float:right; font-weight:bold;
line-height:30px; padding-right:20px; }
	.kalp { color:#d45152; }
	@media all and (max-width: 680px){
#resimBaslik {display:block; float:none; text-align:center;}
.begeni {float: none; text-align:center; display:block; padding-right:0px;}
/* */
	}
	@media all and (max-width: 480px){
		.sliderIc {  height:calc(100% - 20px); padding:10px; }
	/* sliderIc elementi ekran küçüldükçe skaler belirtilmiş padding değerinden dolayı ekranda bıraktığı boş alanı arttırdığından, padding değerini küçültüyoruz ve genişliğini buna göre değiştiriyoruz.*/
	}
	@media all and (max-width: 360px){
.altBolum { width:100% !important;}
#resimBaslik {font-size:20px;}
/* Resmin ismini içinde barındıran element için font boyutunu düşürüyoruz. */
.sliderIc {  height:100%; padding:0px; }
	}
```
JS Kodu			           								 
```JS
var aktif = 1;
var imgList = document.getElementsByTagName("li");
var imgMiktar = imgList.length;
	function boyutlandir(){
	imgList[aktif].className = "aktif";
	document.getElementsByClassName("sliderTasiyici")[0].style.background = "url(" +imgList[aktif].childNodes[0].src + ")";
// CSS’de bahsettiğimiz gibi sliderTasiyici class’lı elementin
// arkaplan resmini aktif olan resim ile değiştiriyoruz.
	imgList[aktif].style.left = "calc(50% - "+ imgList[aktif].clientWidth / 2 +"px)";
	document.getElementById("holder").style.height = imgList[aktif].clientHeight;
	document.getElementsByClassName("altBolum")[0].style.width = imgList[aktif].clientWidth;
// altBolum div’inin genişliğinin aktif resim ile aynı boyutta olmasını
// istediğimizden bahsetmiştik, burada aktif list elementinin genişliğini
// clientWidth ile alarak bunu altBolum div’inin genişliğine atıyoruz.
	if(aktif == 0){
		imgList[imgMiktar].className = "aktif-sol";
		imgList[imgMiktar].style.top = (imgList[aktif].clientHeight - imgList[imgMiktar].clientHeight)/2;
	}else{
		imgList[aktif - 1].className = "aktif-sol";
		imgList[aktif - 1].style.top = (imgList[aktif].clientHeight - imgList[aktif - 1].clientHeight)/2;
	}
	if(aktif == imgMiktar){
		imgList[0].className = "aktif-sag";
		imgList[0].style.top = (imgList[aktif].clientHeight - imgList[0].clientHeight)/2;
	}else{
		imgList[aktif + 1].className = "aktif-sag";
		imgList[aktif + 1].style.top = (imgList[aktif].clientHeight - imgList[aktif + 1].clientHeight)/2;
	}
}
// Kodların üstteki bölümünde aktif list elementinin solundaki ve sağındaki
// list elementlerini belirleyerek uygun olan list elementlerine classları
// atıyoruz, bunun yanında boyutlandırmayı da burada hallediyoruz.
window.onload = boyutlandir;
window.onresize = boyutlandir;
// boyutlandır() fonksiyonunu hem pencere yüklendiğinde hem de pencere boyutu
// değiştirildiğinde yeniden çağırıyoruz. Bu sayede Javascript üzerinde
// halledilen boyuta göre değiştirilmesi gereken elementlerin boyutları
// değişiyor.
```
**Bu bölümde 10 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>Responsive Değiş Tokuş Tekniği</title>
       <meta name="viewport" content="width=device-width">
	<link rel="stylesheet" href="style.css"/>
	<script type="text/javascript" src="script.js"></script>
</head>
<body>
       <div class="normalIcerik">Normal İçerik Buraya</div>
       <div class="responsiveIcerik">Responsive İçerik Buraya</div>
</body>
</html>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px;}
body { background:#f1f1f1; }
.normalIcerik { display:block; }
.responsiveIcerik { display:none; }
	@media all and (max-width: 480px){
.normalIcerik { display:none; }
.responsiveIcerik { display:block; }
	}
```
**Bu bölümde 12 nolu referans resim kullanılacak.**
