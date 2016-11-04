HTML Kodu
```HTML
<html>
<head>
	<meta charset="utf-8" />
	<title>SVG Deneme</title>
       <meta name="viewport" content="width=device-width">
	<link rel="stylesheet" href="style.css"/>
</head>
<body>
   <svg width="200" height="200" viewBox = "0 0 200 200" version = "1.1">
      <line x1 = "0" y1 = "0" x2 = "200" y2 = "200" stroke = "black" stroke-width = "3"/>
   </svg>
</body>
</html>
```
CSS Kodu
```CSS
* { margin:0px; padding:0px; }
```
**Bu bölümde 5 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
   <svg width="200" height="200" viewBox = "0 0 500 500" version = "1.1">
      <line x1 = "0" y1 = "0" x2 = "200" y2 = "200" stroke = "black" stroke-width = "3"/>
   </svg>
```
**Bu bölümde 6 nolu referans resim kullanılacak.**


---


HTML Kodu
```HTML
   <svg width="300" height="200" viewBox = "0 0 300 200" version = "1.1">
       <rect x="20" y="20" width="200" height="50" fill="#ccc"
        stroke="black" stroke-width="1" />
   </svg>
```
**Bu bölümde 7 nolu referans resim kullanılacak.**


---


HTML Kodu
```HTML
   <svg width="300" height="200" viewBox = "0 0 300 200" version = "1.1">
       <rect x="20" y="20" width="200" height="50" fill="rgb(220,220,220)"
        rx="10" ry="10" stroke="#aaa" stroke-width="1" />
   </svg>
```
**Bu bölümde 8 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
   <svg width="300" height="200" viewBox = "0 0 300 200" version = "1.1">
       <rect x="20" y="20" width="70" height="70" fill="#eee"
        rx="100%" ry="100%" stroke="#aaa" stroke-width="1" />
	<circle cx="150" cy="55" r="35" stroke="gray"
        stroke-width="1" fill="#999" />
   </svg>
```
**Bu bölümde 9 nolu referans resim kullanılacak.**


---


HTML Kodu			           							 
```HTML
  <svg xmlns="http://www.w3.org/2000/svg" width="310" height="300">
     <path d="M2,111 h300 l-242.7,176.3 92.7,-285.3 92.7,285.3 z"
      style="fill:#ccc;stroke:#444;stroke-width:2;stroke-linejoin:round"/>
   </svg>
```
**Bu bölümde 10 nolu referans resim kullanılacak.**


---



HTML Kodu
```HTML
<svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 width="100px" height="100px" viewBox="0 0 100 100" enable-background="new 0 0 100 100" xml:space="preserve">
	<line fill="none" stroke="#000000" stroke-miterlimit="10" x1="18.81" y1="11.905" x2="50.698" y2="69.271"/>
	<line fill="none" stroke="#000000" stroke-miterlimit="10" x1="50.698" y1="69.271" x2="83.107" y2="20.224"/>
	<line fill="none" stroke="#000000" stroke-miterlimit="10" x1="83.107" y1="20.224" x2="5.638" y2="53.673"/>
	<line fill="none" stroke="#000000" stroke-miterlimit="10" x1="5.638" y1="53.673" x2="24.702" y2="94.747"/>
	<line fill="none" stroke="#000000" stroke-miterlimit="10" x1="24.702" y1="94.747" x2="92.293" y2="53.673"/>
</svg>
```
**Bu bölümde 15 nolu referans resim kullanılacak.**


---


```HTML
  <svg width="230" height="300" viewBox = "0 0 230 300">
       <rect id="bar1" x="0" y="0" width="20" height="300" fill="rgb(150,150,150)" rx="10" ry="10"/>
       <rect id="bar2" x="30" y="0" width="20" height="300" fill="rgb(150,150,150)" rx="10" ry="10"/>
       <rect id="bar3" x="60" y="0" width="20" height="300" fill="rgb(150,150,150)" rx="10" ry="10"/>
       <rect id="bar4" x="90" y="0" width="20" height="300" fill="rgb(150,150,150)" rx="10" ry="10"/>
       <rect id="bar5" x="120" y="0" width="20" height="300" fill="rgb(150,150,150)" rx="10" ry="10"/>
       <rect id="bar6" x="150" y="0" width="20" height="300" fill="rgb(150,150,150)" rx="10" ry="10"/>
       <rect id="bar7" x="180" y="0" width="20" height="300" fill="rgb(150,150,150)" rx="10" ry="10"/>
       <rect id="bar8" x="210" y="0" width="20" height="300" fill="rgb(150,150,150)" rx="10" ry="10"/>
   </svg>
```

JS Kodu
```JS
function getRandInt(min,max){
    return Math.floor(Math.random()*(max-min+1)+min);
}
//Belirlediğimiz başlangıç ve bitiş değeri arasında bir tam sayı döndüren fonksiyon.

function play(){
	var changeTo;
	//Değişecek yükseklik değerini tutan değişken.
	var i = 1;
	var marginalize = getRandInt(1, 5);
	// ilk rastgele sayıyı atıyoruz, buna göre bu sayı 1 gelirse, hiç bir koşul olmadan yükseklik 100 ve 300 değerleri arasında bir sayı alacak.

	while(i<=8){
	// Elimizde 8 rect elementi olduğundan bunları while içerisinde göstereceğiz.
	if(marginalize == 1){
	changeTo = getRandInt(100, 300);
	//ilk rastgele sayı 1 geldiğinde 100-300 arası rastgele sayı getir.
	}else{
		if(i == 1 || i == 8){
		changeTo = getRandInt(30, 100);
		}else if(i == 2 || i == 7){
		changeTo = getRandInt(80, 170);
		}else if(i == 3 || i == 6){
		changeTo = getRandInt(100, 250);
		}else if(i == 4 || i == 5){
		changeTo = getRandInt(150, 300);
		}

		//Eğer olmazsa, bahsettiğimiz gibi soldaki ve sağdaki rect elementleri daha düşük bir domainde rastgele sayı getirirken, ortalara doğru getirilen sayıların domaini yükseltilecek.
	}

	document.getElementById("bar"+i).height.baseVal.value = changeTo;
	//Değiştirilecek sayı değerleri belirlendikten sonra bar elementlerininin yüksekliğini baseVal.value ile değiştiriyoruz.
	document.getElementById("bar"+i).y.baseVal.value = (150 - changeTo/2);
	//Aynı şekilde elementin y değişkenini elementi her zaman ortada tutacak şekilde, konumlandırıyoruz.
	i++;
	}
}

//play() fonksiyonu, asıl animasyonu yöneten fonksiyonumuz olacak, bu fonksiyonu her çağırdığımızda svg rect elementlerimiz farklı boyutlar alacak.

window.onload = function(){
setInterval(play, 300);
// setInterval ile play metodunu sayfa yüklenmesi tamamlandığında 300ms'de bir çağırıyoruz.
}

```

CSS Kodu
```CSS
svg rect{ transition:300ms linear all; -moz-transition: 300ms linear all;}
```
