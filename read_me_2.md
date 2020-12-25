# Vue.Js Tutorial
## :exclamation: 1- Vue.js Basit Kurulum
:pushpin: ***Html Sayfası***
````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
  <p>{{title}}</p>
</div>
````
:pushpin: JavaScript Sayfası
````javascript
new Vue({
	el: "#app",
	data: {
	    title: "Merhaba Vue Js",
    },
});
````
---
## :exclamation: 2- Süsülü Panatez `{{ }}` İçerisinde Fonksiyon Tanımlamak ! 
:pushpin: Html Sayfası 
````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
  <p>{{hello()}}</p>
</div>
````
:pushpin: JavaScript Sayfası
````javascript
new Vue({
    el : "#app",
    data : {
        title : "Merhaba Vue Js ",
        },
    methods: {
  	    hello : function()
        return "Merhaba, İyi Günler"
    }
  }
});
````
---
## :exclamation: 3- Instances İçerisinde Bir Property'e Başka Bir Property'den Ulaşmaya Çalışmak !     —     this. Anahtar Kelimesini Kullanmak! 
:pushpin: Html Sayfası 
````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
  <p>{{hello()}}</p>  
</div>
````
:pushpin: JavaScript Sayfası
````javascript
new Vue({
    el : "#app",
    data : {
        title : "Merhaba Vue Js ",
	},
  methods: {
    hello : function(){
    return this.title;
    }
  }
});
````
---
## :exclamation: 4- Attribute Bind İşlemi 
> Etiket içerisinde  interplution kullanarak bir veri yazdırabiliyoruz, fakat `<a href="{{ link }}"> Link </a>` gibi attribute içerisinde
interplution kullanarak dinamik bir veri buraya akaramayız.  Yapmamız gerekenler ise ==v-bind==(bağlamak) anahtar sözcüğü  ile Vue'yu href
isimli attribute'a bağla diyoruz. Ayrıca  `{{` link }} 'deki `{{  }}` süslü paranezleri de siliyoruz.

:pushpin: Html Sayfası 
````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
  <p> {{hello()}} <a href="link"> Link</a> </p>
</div>
````
:pushpin: JavaScript Sayfası
````javascript
new	Vue({
    el : "#app",
    data : {
        title : "Merhaba Vue Js ",
        message : "Hoşgeldiniz",
        link : "https://www.google.com"
	},
  methods: {
  	hello : function(){
        return this.title + this.message;
    }
  }
});
````
---
## :exclamation: 5- v-once Directive Kullanımı 
> v-once şunun için kullanılır; tanımlandığı yerde değişikliğe izin verirken, kullanılmadığı yerde herhangi bir değişikliğe sebep olmaz. ==v-once== kısacası ilk render'dn sonra Html üzerinde verinin data içerisinde ne ise öyle kalmasını sağlayan bir dirctive'dir

:pushpin: Html Sayfası 
````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
    <p v-once> {{ title }} </p>
    <p> {{hello()}} <a href="link"> Link</a> </p>
    
</div>
````

:pushpin: JavaScript Sayfası

````javascript
new	Vue({
    el : "#app",
    data : {
        title : "Merhaba Dünya",
        message : "Hoşgeldiniz",
        link : "https://www.google.com"
	},
    methods: {
        hello : function(){
        this.title = "Merhaba!!!"
        return this.title;
    }
  }
});
````
---
## :exclamation: 6- Event Objesinden Event Verisini Almak
> Alert Butonu Gösterme

:pushpin: Html Sayfası 

````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
    <button v-on:click="showAlert">Alert Göster</button>  
</div>
````

:pushpin: JavaScript Sayfası

````javascript
new Vue({
  el: "#app",
  methods: {
    showAlert: function () {
      alert();
    }
  }
});
````
---
> Koordinatları Gösterme

:pushpin: Html Sayfası 

````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
    <p v-on:mousemove="updateCoords"> Koordinatlar: {{ x }},{{ y }} </p>
</div>
````

:pushpin: JavaScript Sayfası

````javascript
new Vue({
  el: "#app",
  data: {
    x: 0,
    y: 0
  },
  methods: {
    updateCoords: function (event) {
      this.x = event.clientX;
      this.y = event.clientY;
    }
  }
});
````
---
## :exclamation: 7- HTML Kodlarını Vue.Js Üzerinden ekrana Basmak
> v-html ile properti'deki linki string olarak göstermeden normal link olarak render ettirebiliriz.

:pushpin: Html Sayfası 

````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
    <p v-once> {{ title }} </p>
    <p> {{hello()}} <a href="link"> Link</a> </p>
    <p v-html="bloglink"></p> 
</div>
````

:pushpin: JavaScript Sayfası

````javascript
new Vue({
  el: "#app",
  data: {
    title: "Merhaba Dünya",
    message: "Hoşgeldiniz",
    link: "https://www.google.com",
    bloglink: "<a href='https://www.google.com'> Link</a>"
  },
  methods: {
    hello: function () {
      this.title = "Merhaba!!!"
      return this.title;
    }
  }
});
````
---
## :exclamation: 8- Vue.Js İle Event Dinleme

:pushpin: Html Sayfası 

````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
    <button v-on:click="showAlert">Alert Göster</button> 
</div>
````

:pushpin: JavaScript Sayfası

````javascript
new Vue({
  el: "#app",
  methods: {
    showAlert: function () {
      alert();
    }
  }

});
````
---
:pushpin: Html Sayfası 
-
````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
    <button v-on: click="counter++">Arttır</button>
      <button v-on: click="increaseCounter">Azalt</button>
      <p> {{ counter }} </p> 
</div>
````

:pushpin: JavaScript Sayfası

````javascript
new Vue({
  el: "#app",
  data: {
    counter: 0
  },
  methods: {
    increaseCounter: function () {
      this.counter--;
    }
  }
}
````
---
## :exclamation: 9- input'un içerisine yazılan karakteri algılama

:pushpin: Html Sayfası 

````html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
  <input type="text" v-on:input="changeTitle">
  <p>{{ description }}</p>
</div>
````
:pushpin: JavaScript Sayfası
````javascript
new Vue({
  el: "#app",
  data: {
    title : "Merhaba !!!",
    description : "Bu bir açıklamdır!"
  },
  methods: {
    changeTitle: function () {
      alert();
    }
  }
});
````
---





