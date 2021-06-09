# Javascript Dokümantasyon


- [JS Nedir?](#JS-Nedir?)
- [Modern JS Nedir?](#Modern-JS-Nedir?)
- [EcmaScript 6 Bilinmesi Gerekenler](#EcmaScript-6-Bilinmesi-Gerekenler)
  - [Spread Operatör](#Spread-Operatör)
  - [Array.map() Operatör](#Map-Operatör)
  - [Array.Filter Operatör](#Filter-Operatör)
  - [Object.assign](#Object-assign-[])
  - [Template Literals](#Template-Literals)
- [Babel Nedir?](#Babel-Nedir?)
- [Pollyfill Nedir?](#Pollyfill-Nedir?)
- [ESlint Nedir?](#Eslint-Nedir?)
- [Prettier Nedir?](#Prettier-Nedir?)
- [Webpack Nedir?](#Webpack-Nedir?)


## JS-Nedir?
Web tarafında çalışan dinamik programlama dilidir. Tarayıcı içerisinde bulunan engine (motor) ile çalıştırılır.

## Modern JS Nedir?
Node.js, npm, ve js kütüphanelerinin olması modern js'in kullanımını artırdı.
Node.js yapısı: js kodlarını makine kodlarına çevirir.
Node.js'den önce yazdığımız kodlar sadece tarayıcı içindeki js motorları ile anlaşılır hale getiriliyordu.
Node.js js kodlarının sadece tarayıcı içinde değil dışarıdan da çalışabilir hale gelmesini sağladı. Js'i artık server tabanlı uygulamalarda da kullanmamıza olanak sağladı.


![alt text](https://github.com/UgurMamak/react-documentation/blob/master/js/images/1.png)


## Değişken Tipleri

#### Primitive Types

    string let name="uğur"
    number let age="22"
    bolean let isActive=true
    null  let job=null
    console.log(typeof variableName) 

#### Reference Types- Objects

    //array
    let names=['Ali','Ahmet','Can'];
    
    //object
    let address={
	    city:"Kocaeli",
	    country:"Türkiye"
    }
    
    var calcAge=function(){
	    return 5;
    }

**NOT**

    num=10;
    num.toFixed(2)//10.00 virgülden sonraki 2 basamak demek
    
    num2=10.15452
    num2.toPrecision(5)//10.154 
    
    //parseInt , parseFloat
    parseInt("10")
    parseFloat("10.5")

NaN: Not a Number //sayısal değere çeviremez demek.

    a >= b
    a<= b **// = her zaman sağ tarafta olmalı**


## EcmaScript 6 Bilinmesi Gerekenler
Ecmascript javascript dilinin standartlaştırılmış sürümünün adıdır.

### Spread Operatör
yaymak anlamına gelir. kopyalayarak kullanır.

    foo(...operate); şeklinde kullanılır.
    
 
**Fonksiyonlara parametre olarak array geçmek gereken durumlarda kullanılabilir.**
 Birden fazla parametre alan bir fonksiyona parametre olarak elimizde bulunan bir arrayi geçmek istediğimizde aşağıdaki şekilde apply kullanmak gerekiyordu [4].
 
    function myFunction(x, y, z) { }  
    var array1 = [0, 1, 2];  
    myFunction.apply(null, array1);
spread operatörü ile bu kullanıma gerek kalmadı.

    myFunction(...array1);

 **Başka arraylari de dahil ederek yeni array oluşturulan durumlarda kullanılabilir.**
  
    var data = [3,4];  
    var newData = [1,2, ...data, 5,6]; //1,2,3,4,5,6 şeklinde olur.

 **Bir arrayden kopya array oluşturmak**
Bir array'i kopyalamak için slice metodu kullanılıyordu. yenisinde kullanım şu şekilde
    
    var arr = [1, 2, 3];  
    var arr2 = [...arr]; // like arr.slice()  
    arr2.push(4);
 

**Math fonksiyonunda kullanmak**

    let numbers = [9, 4, 7, 1];  
    Math.min(...numbers); // 1

 **NodeList’ten dönen değeri diziye çevirmek**

    [...document.querySelectorAll('div')]

### Map Operatör
Array üzerinde gezinme ve işlem yapabilmek için kullanılır. 

> Map array'in kopyasını alarak üzerinde işlem yapar. Foreach direk array üzerinde çalışır.

    const array1 = [1, 4, 9, 16];
    
    // pass a function to map
    const map1 = array1.map(x => x * 2);
    
    console.log(map1);
    // expected output: Array [2, 8, 18, 32]


### Filter Operatör
data içerisinde filtreleme yapmak için kullanılır.

    const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
    const result = words.filter(word => word.length > 6);
    console.log(result);
    // expected output: Array ["exuberant", "destruction", "present"]

### Object assign []
Objectleri birbiri üzerine kopyalanmasını sağlayan fonksiyondur.

Object.assign(hedef_nesne, ..._kaynak_nesneler_)
Object.assign(kopyalandığı yer, kopyalanan data)

    var obj1 = { a: 1 };
    var obj2={b:2}
    Object.assign(obj1,obj2);
    console.log(obj1); // {a: 1, b: 2}
<br>

    const personel = {name: "Uğur", surname: "Mamak"};  
    const personel2 = personel;  
    personel2.name = "Uğur2";  
    console.log(personel);  { name: ‘Uğur2’, surname: ‘Mamak’ }
    console.log(personel2);{ name: ‘Uğur2’, surname: ‘Mamak’ }

> nesneleri birbirine eşitleyerek atama işlemi yapabiliriz. Fakat bu şekilde kullanım olursa yukarıdaki gibi personel2'nin değerini değiştirdiğimizde personel değişkeninin de değeri değişir. Çünkü **Javascript’te array ve object tipleri referanstır.** Yani değişkenler, bilgilerin bellekteki adreslerini tutarlar.


####  Template Literals

ES6 ile gelen bir özelliktir. (``) işareti ile tırnak işaretleriyle tek tek uğraşmak yerine en dışta bu sembol kullanılır. içeride değişkenleri  ${variable veya işlemler} şeklinde kullanabiliriz.

**NOTLAR**

find:array içinde tek değer arıyorsak kullanabiliriz.
filter:array içerisinde birden fazla değer arıyorsak filter kullanabiliriz.

map ile foreach arasındaki fark map var olan arrayi kopyalar ve kopya üstünde çalışırken foreach kopyalamadan direk array üzerinde çalışır.

browser tarafında çalışan ve nodejs ile çalışan kodlar arasındaki fark browser tarafında yüklü olan window objectdir. Browserda engine dışında window objesi var. DOM yapısını kullanarak herhangi bir etikete erişebiliyoruz.



## Babel Nedir?
https://medium.com/hepsiburadatech/babel-nas%C4%B1l-%C3%A7al%C4%B1%C5%9F%C4%B1r-f1b4a68c8120  (ek kaynak aşağıdakilerden ayrı)

Javascript kodunu browserlar calistirir. Tıpkı html ve css gibi. Bugünkü browserlar(Chrome, Firefox, İnternet Explorer vs.) javascript’in es5 sürümünü biliyorlar.

ES6 bütün tarayıcılarda uyumlu olmadığı için bütün tarayıcılarda uyumlu olan ES5'e dönüştürerek kodların çalışabilir olmasını sağlayan açık kaynak kodlu javascript  transcompilerdır (Js derleyicisidir).

ES6 standardını ES5 standardına çevirmeyi sağlar. 

Sadece ES6 kullanmamızı sağlamakla kalmaz. Aynı zamanda polyfill desteği ile ES7, JSX gibi başka standartları kullanmamıza imakn sunar.
(https://medium.com/hepsiburadatech/babel-nas%C4%B1l-%C3%A7al%C4%B1%C5%9F%C4%B1r-f1b4a68c8120)
 
    npm i babel-cli babel-preset-es2015 --save 
    
    start:"babel-node index.js --preset es2015" (package.json'da scripts içine yazılır.)

### Pollyfill Nedir?
https://medium.com/bili%C5%9Fim-hareketi/babel-polyfilling-nedir-nas%C4%B1l-%C3%A7al%C4%B1%C5%9F%C4%B1r-46b4cd08c634

Babel kodu derlerken  onu dönüştürür. Pollyfilling, tarayıcıya yeni işlevler ekliyor.

Eğer kodunuzda polyfilling kullanmanız gerekiyorsa kurulum için:

    npm install babel-polyfill


## Eslint Nedir?

Js kodunda bulunan sorunlu kalıpları tanımlamak için statik bir kod analiz aracıdır.
Hataların altını kırmızı ile çizer. Aynı zamanda belirlenen standartlara uymayan kodlarında altını çizer.

.eslintrc adlı bir yapılandırma dosyası ile belirlenen yönergeler dahilinde sorunlu kod bloklarını bulur ve uyarır.

custom eslint yazabilirsin veya büyük firmaların standartlarında yazmak istiyorsan onlarıda kullanabilirsin (google, facebook, airbnb gibi...)


Airbnb'nin sunduğu ESLint kuralları React için üst düzey standart olarak kabul edilir.

**Kurulum**

İlk adımda projeye geliştirme paketleri(dev-dependency) kurmak gerekmektedir. 
.eslintrc dosyası oluşturulmalı

    npm install eslint --save-dev
    
Bir tane oluşturmak için eslint --init komutunu çalıştırabiliriz. daha fazla bilgi için [awesome-eslint](https://github.com/dustinspecker/awesome-eslint) incele.


Kodumuzda kullanmak için komut satırında eslint . yazmak yeterlidir. Daha verimli olması açısından package.json içerisinde aşağıdaki gibi bir kullanım yapmalıyız.

    "scripts": { "lint": "eslint .", "lint:fix": "eslint --fix ." } }


örnek yapılandırma

    { "env": { "browser": true, "jest": true, "es6": true }, "plugins": ["import"], "extends": "eslint:recommended", "parserOptions": { "ecmaVersion": 2018, "sourceType": "module" }, "rules": { "no-console": "warn", "no-eval": "error", "import/first": "error" } }


https://gurolayanlar.com/eslint-prettier-ile-daha-guclu/

## Prettier Nedir?

Belirtilen stillere göre kod formatlayıcı olarak kullanılır.

    npm install prettier --save-dev
    
_.prettierrc_dosyası oluşturulur.

https://gurolayanlar.com/eslint-prettier-ile-daha-guclu/

## Webpack Nedir?
"Module Bundler"(Modül paketleyicisi) Yazdığımız kodları düzenler, Proje altındaki tüm dosyaları tek bir dosya altında birleştirir.

    module.exports = {  
	    entry: './app.js',  
	    output: {  
		    filename: 'bundle.js'  
	    }  
    }
    
**NOT**
Daha hızlı yeniden oluşturma için yalnızca src içindeki dosyalar webpack tarafından işlenir. Herhangi bir js ve css dosyasını src içine koymanız gerekir, aksi taktirde webpack bunları görmez.

**Webpack'teki temel kavramlar**

-   Entry (başlangıç noktası)
-   Output (çıktı dosyası)
-   Loaders (yükleyiciler)
-   Plugins (eklentiler)
-   Mode (PROD ve DEV modları)
-   Browser Compatibility (tarayıcı uyumluluğu) şeklindedir.
- 
https://webpack.js.org/ (yapısı ve görevleri için inceler)
https://devnot.com/2021/webpack-nedir-webpacke-detayli-bir-bakis/


## Scope(Let-const-var)

scope: yazdığımız değişkenin hangi kod parçası tarafından ulaşılabilir olup olmamasıyla alakalıdır. 

**Global Scope**
Tüm fonksiyonlar ve bloklar(if, for, switch gibi...) global scope'a erişebilmektedir.

    var name="Uğur"
    function logName(){
    //name'e burda da oluşabiliriz.
    }
    if(){
    //name'e erişilebilir.
    }
    
***Local Sope***

**function'lar kendi scope'larını oluşturur.** içinde tanımlanan dışarıda kullanılamaz.

**block'lar yeni scope oluşturmaz.** kendi içinde tanımlanan değerler dışarıda da geçerlidir. (var için geçerlidir.)

**ES6'ı ile gelen let ve const block scope oluşturur.**

 - Değişken bir fonksiyon içinde tanımlanırsa local scope olur. Eğer
   fonksiyonun dışında tanımlanırsa global scope olur. Tüm fonksiyonlar
   kendi içinde yeni bir scope oluşturur.
 - if, switch, for, while gibi döngü ifadeleri fonksiyonların yaptığı
   gibi scope oluşturmazlar.
 - **Var** anahtar sözcüğünün aksine, **let** ve **const** anahtar sözcükleri if ve for gibi blok ifadelerinin içinde kendi kendine
   Scope oluştururlar.
 - let ve const block scope'tur block içinde tanımlanan değerleri sadece
   o scope aralığında geçerlidir.
 - var global scopetur. 
 - let ve const local scope(block scope'tur)

**NOTLAR**

primitive tipler(ilkel tipler) value type'dır.
Objeler, fonksiyonlar ise referans type olur. https://tr.javascript.info/primitives-methods (oku)

es5'de class oluşturulamaz.
es6'da class tanımlaması yapılabiliyor.

**stopPropagation()**

içden dışa gerçekleşen event olaylarında en içteki nesnenin eventi tetiklenirse en dıştaki nesnelerin eventi'de tektiklenir bu olaya event bubling denir. Bunu engellemek için **stopPropagation()** methodu kullanılır.


**NOTLAR**

 - hasOwnProperty: objemizde belirtilen özelliğin olup olmadığınu kontrol ederek boolean bir değer döner.
 - Object'ler RAM'de tutulur.
 - JS'de primitive tip haricindeki her şey bir object türündedir.
 
 **pure function**
 Aynı girdiler için her zaman aynı çıktıları üreten fonksiyonlara denir. Parametre olarak gelen girdiler üzerinde herhangi bir değişiklik yapılmaz. Yani fonksiyonun yan etkileri yoktur. Bütün olaylar fonksiyon içinde gerçekleşir Dış bağlantıları yoktur.