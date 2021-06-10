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