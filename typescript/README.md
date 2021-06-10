- [TypeScript Nedir](#TypeScript-Nedir)
- [Neden TypeScript](#Neden-TypeScript)
- [TypeScript-Bileşenleri](#TypeScript-Bileşenleri)
- [Kurulum](#Kurulum)


# TypeScript Nedir
Js'in bazı yapısal eksiklikleri vardı. Nesne tabanlı dillerin sunduğu tip kontrolü, sınıflar gibi yapılar bulunmuyordu, dinamik olmasından dolayı derleme aşaması yoktu ve hata kontrolü zor yapılıyordu. Typescript bu eksiklikleri gidermek ve javascript'i büyük projelerde daha etkili şekilde kullanmak için tasarlanmıştır.

Programlama dili değildir. Çalışabilir ortama gittiğinde js haline dönüştürülür. 

İstemci veya sunucu ortamında çalışabilen JavaScript programları yazmak için kullanılabilir. 
TS JS'in genişletilmiş bir versiyonudur.
Tüm JS kütüphanelerini kullanabilir.
[kaynak](https://devnot.com/2019/typescript-nedir/)

# Neden TypeScript
Derleme:Js yorumlamalı(interpreted) bir dildir, derleme aşaması yoktur. TS dönüştürücüsü derleme aşamasında hata denetimi sağlar.
Nesne Yönelimli Programalama: Sınıflar, interfaceler modüller, inheritance vb. özellikleri destekler.

Güçlü Statik Tipler: TS'de isteğe bağlı olarak veri tipi tanımalaması yapılabilir.
Kolay okunabilirlik
[kaynak](https://devnot.com/2019/typescript-nedir/)

## NOT

**Statik programlama dilleri**:
Her değişkenin tipi önceden belirtiliyor olmasıdır. YAni string bir değer tanımlıyorken başına string, sayi tanımlıyorken int,double gibi tipleri yazmamız gerekiyor.
Böylece program çalışmadan önce bu tiplerin neler olduğunu bilir ve bir hata yaptıysak bizi uyarır.
C,C++,C#,Java,Scala

**Dinamik programlama dilleri**
Değişken tiplerinin programın çalışma anında belirlendiği dillerdir. Yani ne string ne de int, doble gibi herhangi bir değişken tipi belirtmemize gerek yoktur.
Programın çalışma anına kadar herhangi br hat5a var mı göremeyiz.
Lisp, Perl, Ruby, Python, Javascript
[kaynak](https://www.kadir.xyz/yazi/65/statik-ve-dinamik-programlama-dillerinin-farklari)

# TypeScript-Bileşenleri
Dil:Kendi söz dizimi, anahtar kelimeleri ve tip tanımlamaları vardır.
Derleyici: TS'de yazılan kodu JS'deki karşılığına dönüştürür.
TLS(TypeScript Dil Servisi):Editörlerde kullanılması için otomatik tamamlama, kod biçimlendirme, renklendirme, vb. gibi tipik düzenleyici işlemlerini destekler.
[kaynak](https://devnot.com/2019/typescript-nedir/)

# Kurulum
    npm i -g typescript
    tsc --version
    
   
   
//************* 
# Düzenle**

ts dosyası js derleyicisi tarafından tanınmaz. Bu yüzden ts dosyasını compiler aracılığıyla js dosyası haline getirmeliyiz.
cmd ekranında **tsc dosyaName.ts** yazarak compiler edebiliriz.

## Types
js'de hata vermez Ts'de verir.

    let number=5;
    number='a';
    //hata vermez çünkü let a; any olarak belirtilmiş herhangi bir type alabilir .
    let a;
    a=5;
    a='a';
    a=true;
    
    let a:number=5;
    let b:string='a';
    let c:boolean=true;
    let d:any;
    let e:number[]=[1,2,3]
    let f:Array<number>[1,2,3,]
    let g:any[]=[1,'a',true]
    let h:[string,number,boolean]=['a',5,true]

e=f 
g'de ki gibi array type'ını belirtmeden de array oluşturabiliriz.

    enum Payment{kredi,havale,eft}
    
    let kredi=Payment.kredi;//0 indis numaralarını tutar.
    let havale=Payment.havale;//1
    let eft=Payment.eft;//2

## Type Assertions(Tür Dönüşümü)

    let message='Hello world';
    message.length; //başlangıçta değer ataması yaparak string türünde olduğunu belirtmiş olduk. Bu sayede length  çalışabiliyor.

<br>

    let message;
    message='Hello world'
    message.length; //bu şekilde olunca length çalışmaz. çünkü başlangıçta message değişkenin type'ı **any** olarak gözükür.

<br>


    let message;
    message='Hello world';

let count=(<string>message).length; 
let a=(message as string).length; //değişkeni any olarak tanımladıysak bu iki şekilde tür dönüşümü yaparak length özelliğini kullanabiliriz.

## Functions

    functions getAverage(a,b,c){
    const result=(a+b+c)/3;
    return 'result':+result;
    }
    getAverage(10,20,30);

yukarıdaki şekilde yaptığımızda fonksiyon çalışır fakat fonksiyona parametre olarak string değer verdiğimizde derleyince hata alırız. 
Programlama aşamasında hatayı görebilmek için 
functions getAverage(a:number,b:number,c?:number):string
{}
şeklinde tanımlama yaparak programlama aşaamasında hatayı görebileceğiz.
en sondaki **string** 'in anlamı fonksiyonun string bir değer return edeceği anlamına gelir.

c? işaretinin anlamı fonksiyon 2 veya 3 paametre alabilir anlamına gelir yani c değeri parametre olarak gelebilir veya gelmeyebilir anlamına geliyor.

functions getAverage(...a:number[]):string // gelen parametre sayısı belirsiz ise bu şekilde kullanabiliriz.

const getAverage=():void=>{
} //arrow function şeklinde tanımlama yapabiliriz. void return değeri olmayacağını gösterir.

## Interface
new keyword'ü kullanılmaz.
Bir sınıfın ne yapması gerektiğini belirtir. nasıl yapması gerektiğini değil
Default olarak tüm interface üyeleri abstract ve public olarak tanımlanır.
içerisinde yalnızca metodların imzaları yer alır, içi dolu metot bulundurmazlar.

## Access Modifiers

default olarak public'dir.

## NOT
fonksiyonlar interface ve class içerisinde metot olarak tanımlanır.