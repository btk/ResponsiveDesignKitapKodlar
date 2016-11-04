
.htaccess Kodu
```HTML
<ifModule mod_gzip.c>
 mod_gzip_on Yes
 mod_gzip_dechunk Yes
 mod_gzip_item_include file \.(html?|txt|css|js|php|pl)$
 mod_gzip_item_include mime ^application/x-javascript.*
 mod_gzip_item_include mime ^text/.*
 mod_gzip_item_exclude rspheader ^Content-Encoding:.*gzip.*
 mod_gzip_item_exclude mime ^image/.*
 mod_gzip_item_include handler ^cgi-script$
</ifModule>
```
- Bu kodu şu adresten kopyalayabilirsiniz: https://goo.gl/WVrJm3


---


HTML Kodu
```HTML
<body>
<div>
	<ul id="listeTasiyici">
	</ul>
	<input type="text" id="yeniMalzeme" placeholder="Yeni Malzeme"/> <button onclick="ekle()">Ekle</button>
</div>
</body>
```

JS Kodu
```JS
	var malzemeSayisi = 2;
//Halihazırda HTML içinde 2 elemanımız bulunuyor.
		function ekle(malzeme){
			if(!malzeme){
			malzeme = document.getElementById("yeniMalzeme").value;
			}
			// Burada ekleme fonksiyonu ek olarak bir string alıyor
			// Bu sayede hem buton ile hem de fonksiyonu çağırarak
			// Yeni malzeme ekleyebileceğiz.
			if(!malzeme){
				alert("Yeni malzeme boş olamaz");
				// Malzemenin boş olma durumu kontrolü
			}else{
				var listem = document.getElementById("listeTasiyici");
				malzemeSayisi++;
				// Global değişken malzemeSayisi'nı artırıyoruz.
				listem.innerHTML += "<li id='malzeme-"+malzemeSayisi+"'>"+malzeme+"<span onclick='kaldir("+malzemeSayisi+")'> (Kaldır)</span</li>"
				// listeTasiyici elementi içine yeni elementi ekliyoruz.
				// Bu elementi eklerken silmek için kullanacağımız
				// span elementini de bu yordam ile eklemekteyiz.
			}
			document.getElementById("yeniMalzeme").value = "";
			// son olarak yeniMalzeme inputunun içini boşaltıyoruz.
		}

		function kaldir(id){
			var elem = document.getElementById("malzeme-"+id);
			document.getElementById("listeTasiyici").removeChild(elem);
			// silinecek elementi objeye çeviriyor ve parent
			// obje üzerinden removeChild metodu ile elementi siliyoruz.
			malzemeSayisi--;
			// Global değişken olan malzemeSayisi'nı2 Azaltıyoruz.
		}

		window.onload = function(){
			ekle("Patates");
			ekle("Domates");
			// Sayfa yüklemesi tamamlandığında fonksiyon çağırarak
			// elemetlerimizi ekliyoruz.
		}
```
**2 referans numaralı görsel burada kullanılacak (Olabildiğince büyük)**


---


HTML Kodu
```HTML
<body>
<div>
	<ul id="listeTasiyici">
	</ul>
	<input type="text" id="yeniMalzeme" placeholder="Yeni Malzeme"/> <button onclick="alisverisListesi.ekle()">Ekle</button>
</div>
</body>
```
JS Kodu 	
```JS
		var alisverisListesi = {
			malzeme: ["Patates", "Domates"],
//malzemelerin listesini bir array içinde tutarak
//bu array üstünde olan her değişiklikle güncelleme işlemi yapacağız
			init: function(){
				this.cacheElement();
				this.guncelle();
			},
// obje oluşturulduğunda yapılacaklar fonksiyonu
// içerisinde cache elementleri oluşturup güncelleme yapıyoruz
			cacheElement: function(){
				this.tasiyici = document.getElementById("listeTasiyici");
				this.input = document.getElementById("yeniMalzeme");
			},
// cacheElement fonksiyonunda elementlerin DOM yapısını
// belleğe alarak birden fazla kez kullanacağız.
			guncelle: function(){
				this.tasiyici.innerHTML = "";
				var i = 0;
				while(i < this.malzeme.length){
				this.tasiyici.innerHTML += "<li>"+this.malzeme[i]+" (<span onclick='alisverisListesi.kaldir("+i+")'>Kaldır</span>)</li>";
				i++;
				}
			},
// her array değişikliğinde çağırılacak render fonksiyonu
			ekle: function(yeniMalz){
				if(!yeniMalz){
				var inpValue = this.input.value;
				}else{
				var inpValue = yeniMalz;
				}
				this.malzeme.push(inpValue);
				this.input.value = "";
				this.guncelle();
			},
			kaldir: function(i){
				this.malzeme.splice(i, 1);
				this.guncelle();
			}
		};
		window.onload = function(){
			alisverisListesi.init();
		 }
```
*Bu kod, son örneğimiz ile hem görsel hem de pratik olarak aynı sonucu verecektir.*


---


JS Kodu 			           	
```JS
		window.onload = function(){
			console.time('Klasik JS Test');
			test();
			console.timeEnd('Klasik JS Test');
			}

			function test(){
				i = 0;
				while(i < 10000){
				kaldir(1);
				kaldir(2);
				ekle("Patlıcan");
				ekle("Yeşil Soğan");
				i++;
				}
			}
```


---


JS Kodu
```JS
		window.onload = function(){
			alisverisListesi.init();
			console.time('Modül JS Test');
			test();
			console.timeEnd('Modül JS Test');
		 }

		 function test(){
				i = 0;
				while(i < 10000){
			alisverisListesi.kaldir(0);
			alisverisListesi.kaldir(0);
			alisverisListesi.ekle("Patlıcan");
			alisverisListesi.ekle("Yeşil Soğan");
				i++;
				}
			}
```


---


JS Kodu 			           							 
```JS
		var alisverisListesi = {
			malzeme: ["Patates", "Domates"],
			bekliyor: 0,
			init: function(){
				this.cacheElement();
				this.guncelle();
			},
			cacheElement: function(){
				this.tasiyici = document.getElementById("listeTasiyici");
				this.input = document.getElementById("yeniMalzeme");
			},
			guncelle: function(){
				clearTimeout(this.bekliyor);
				this.bekliyor = setTimeout(function(){
				alisverisListesi.guncelleBeklet();

				}, 1);
			},
			guncelleBeklet: function(){
				this.tasiyici.innerHTML = "";
				var i = 0;
				while(i < this.malzeme.length){
				this.tasiyici.innerHTML += "<li>"+this.malzeme[i]+" (<span onclick='alisverisListesi.kaldir("+i+")'>Kaldır</span>)</li>";
				i++;
				}
			},
			ekle: function(yeniMalz){
				if(!yeniMalz){
				var inpValue = this.input.value;
				}else{
				var inpValue = yeniMalz;
				}
				this.malzeme.push(inpValue);
				this.input.value = "";
				this.guncelle();
			},
			kaldir: function(i){
				this.malzeme.splice(i, 1);
				this.guncelle();
			}
		};
		window.onload = function(){
			alisverisListesi.init();
			console.time('Modül Verimli JS Test');
			test();
			console.timeEnd('Modül Verimli JS Test');
		 }

		 function test(){
				i = 0;
				while(i < 10000){
			alisverisListesi.kaldir(0);
			alisverisListesi.kaldir(0);
			alisverisListesi.ekle("Patlıcan");
			alisverisListesi.ekle("Yeşil Soğan");
				i++;
				}
			}
```
