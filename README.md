
## Primitive (İlkel) Veri Tipleri:

### String: 

Metin veya karakter dizileri için kullanılır.

```
let message = "Merhaba Dünya!";
```

### Number: 

Sayılar için kullanılır.  
```
let pi = 3.14;
```

### Boolean: 

Doğru veya yanlış değerleri için kullanılır. 
```
let isLogged = true;
```

### Null: 

Hiçbir değer veya yokluk için kullanılır. 

```
let myVariable = null;
```

### Undefined: 

Değer atanmamış değişkenler veya fonksiyonlar için kullanılır.  

```
let myVariable;
```

### Symbol: 

Özelleştirilmiş ve benzersiz tanımlayıcılar için kullanılır. 

```
const mySymbol = Symbol('mySymbol');
```

## Referans (Yönlendirme) Veri Tipleri:

### Object:

Tüm nesneler için kullanılır, fonksiyonlar da dahil olmak üzere. Nesneler, özellikler ve değerler içeren veri yapılarıdır.   

```
let user = { name: "Ahmet", age: 35 };
```

### Array: 

Diziler, benzer veri türlerinin bir listesi olarak kullanılır.  

```
let numbers = [1, 2, 3, 4, 5];
```

### Function: 

Fonksiyonlar, kod bloklarını bir işlev olarak gruplayarak kullanılır. 

```
function calculateSum(a, b) {
  return a + b;
}
```

### Date: 

Tarih ve saat değerleri için kullanılır. 

```
let today = new Date();
```

### RegExp: 

Düzenli ifadeleri temsil etmek için kullanılır. 

```
let pattern = /JavaScript/;
```

### Variables

JavaScript'te değişkenler, veri saklamak veya ileride kullanmak için değer atamak için kullanılır. JavaScript'te değişkenler dinamik olarak tip alır, yani bir değişkenin tipi, değişkenin değeri atanırken otomatik olarak belirlenir.
var anahtar kelimesi, bir değişken tanımlamak için kullanılır. Ancak, "var" değişkenleri, blok kapsamı yerine işlev kapsamı veya global kapsam kullanır. Bu nedenle, "var" değişkenleri, aynı isimde birden fazla değişken tanımlanmasına izin verir ve bu da beklenmeyen sonuçlara yol açabilir.
let anahtar kelimesi, "var" anahtar kelimesinin yerini almıştır. "let" değişkenleri blok kapsamını kullanır, bu nedenle aynı isimdeki bir değişkenin yeniden tanımlanması mümkün değildir. Ayrıca, "let" değişkenleri "undefined" olarak değer alır.
const anahtar kelimesi, "let" anahtar kelimesine benzerdir, ancak "let" ile farklı olarak, bir kez değer atandığında değiştirilemez. "const" değişkenleri, özellikle sabitler veya sabit değerler için kullanışlıdır.

Örneğin,

```
var name = "John"; // var ile değişken tanımlama
let age = 30; // let ile değişken tanımlama
const PI = 3.14159; // const ile sabit tanımlama
```

### Template Literals (şablon dizileri): 

Bir Javascript ifadesini düz bir yazı yazar gibi tek bir satırda yazmamızı sağlayan string çeşidi olarak tanımlanabilir. Template literals, back tick dediğimiz tırnak işaretleri içinde yazılmalıdır. (alt gr + , )

### Shorthand Property Names:(kısayol obje anahtarı isimleri): 

Javascript objesi, key-value (anahtar-değer) sistemiyle çalışan bir veri tipidir. Bir obje oluştururken, değer bir değişkenden geliyorsa, anahtarın açıkça belirtilmesine gerek yoktur. Değişkenin direk olarak objeye girilmesi, değişkenin ismini anahtar olarak, değerini ise değer olarak atar.

### Arrow Functions (oklu fonksiyon ifadeleri): 

Oklu fonksiyon ifadeleri, Javascript'te fonksiyon oluşturmanın yeni bir yöntemidir. En önemli ve sık kullanılan özelliklerinden bir tanesi implicit (üstü kapalı) return özelliğidir. Dikkat edilmesi gereken bir başka farklılık ise, oklu fonksiyon ifadeleri hoist edilmezler, yani bir değişkene atadığınız oklu fonksiyonları, function ifadesiyle oluşturduğunuz fonksiyonlar gibi, oluşturmadan önce çağıramazsınız.

### Object Destructuring

JavaScript'te nesne yıkımı (object destructuring), bir nesnenin özelliklerini ayrı ayrı değişkenlere atama yöntemidir. Bu özellikle, bir nesne yöntemi tarafından döndürülen bir nesnenin belirli özelliklerine erişmek için kullanışlıdır.
Nesne yıkımı, süslü parantezleri kullanarak bir nesnenin özelliklerine erişir. Bu özellikler, yeni değişken isimleriyle eşleştirilir. Aşağıdaki örnekte, bir kişi nesnesinden ad ve yaş özelliklerine erişilir:

```
const person = { name: "John", age: 30 };
const { name, age } = person;
console.log(name); // "John"
console.log(age); // 30
```

Bu örnekte, person adlı bir nesne tanımlanır ve name ve age özellikleri atanır. Ardından, name ve age değişkenleri, nesne yıkımı kullanılarak person nesnesindeki ilgili özelliklerle eşleştirilir.
Nesne yıkımı ayrıca, bir fonksiyon tarafından döndürülen nesneden özellikleri değişkenlere atamak için de kullanılabilir. Aşağıdaki örnekte, getPerson adlı bir fonksiyon, bir kişi nesnesini döndürür ve nesne yıkımı kullanılarak ad ve yaş değişkenlerine atanır:

```
function getPerson() {
  return { name: "John", age: 30 };
}
const { name, age } = getPerson();
console.log(name); // "John"
console.log(age); // 30
```

Bu örnekte, getPerson adlı bir fonksiyon, bir kişi nesnesini döndürür ve nesne yıkımı kullanılarak name ve age değişkenleri nesnenin özellikleriyle eşleştirilir.

### Array Destructuring

JavaScript'te dizi yıkımı (array destructuring), bir dizinin öğelerini ayrı ayrı değişkenlere atama yöntemidir. Bu özellikle, bir fonksiyon tarafından döndürülen bir dizinin belirli öğelerine erişmek için kullanışlıdır.
Dizi yıkımı, köşeli parantezleri kullanarak bir dizinin öğelerine erişir. Bu öğeler, yeni değişken isimleriyle eşleştirilir. Aşağıdaki örnekte, bir dizi oluşturulur ve ilk iki öğesi ayrı değişkenlere atanır:

```
const numbers = [1, 2, 3, 4, 5];
const [first, second] = numbers;
console.log(first); // 1
console.log(second); // 2
```

Bu örnekte, numbers adlı bir dizi tanımlanır ve first ve second değişkenleri, dizinin ilk iki öğesiyle eşleştirilir.
Dizi yıkımı ayrıca, bir fonksiyon tarafından döndürülen diziden öğeleri değişkenlere atamak için de kullanılabilir. Aşağıdaki örnekte, getNumbers adlı bir fonksiyon, bir sayı dizisini döndürür ve dizi yıkımı kullanılarak ilk iki öğe first ve second değişkenlerine atanır:

```
function getNumbers() {
  return [1, 2, 3, 4, 5];
}
const [first, second] = getNumbers();
console.log(first); // 1
console.log(second); // 2
```

Bu örnekte, getNumbers adlı bir fonksiyon, bir sayı dizisini döndürür ve dizi yıkımı kullanılarak first ve second değişkenleri dizinin ilk iki öğesiyle eşleştirilir.

### Ternary Conditional Operators (üç değişkenli koşul operatörleri)

Ternary operatörleri üç adet ifade alır. İlk ifade koşuldur. Koşul true yani doğru olarak hesaplanırsa soru işaretinden sonraki kısım işleme alınır, false yani yanlış olarak hesaplanırsa iki nokta işaretinden sonraki kısım işleme alınır.


### Terimler

### Producing Code:

"producing code" terimi, gerçek işlevselliği sağlayan, bir şeyler yapan ve zaman alan kodun yazılması anlamına gelir ve bir yazılım projesinin temel aşamalarından biridir.

Detay: https://javascript.info/promise-basics

### Consuming Code:

"consuming code" terimi, bir yazılım projesinde başka bir kaynaktan kod kullanmayı ifade eder. Bu, projenin hızlı ve verimli bir şekilde tamamlanmasına yardımcı olabilir ve açık kaynaklı projelerde yaygın bir uygulamadır.
Detay: https://javascript.info/promise-basics

### Implicit return: 

Fonksiyon içinde herhangi başka bir ifade olmaksızın tek bir ifade döndürülüyorsa implicit return özelliği kullanılabilir 

(const topla = (sayi1, sayi2) => sayi1 + sayi2;)(array function)

### Hoist: 

JavaScript'te "Hoisting (Kaldırma)" terimi, bir değişkenin veya fonksiyonun tanımlandığı yere göre etki alanının (scope) en üst düzeye taşınması anlamına gelir. Yani, bir değişken veya fonksiyon tanımlanmadan önce kullanılmışsa, bu tanımlama işlemi kod yürütülmeden önce otomatik olarak yukarı taşınır. Bu sayede, değişkenler ve fonksiyonlar, kodun başında tanımlanmış gibi davranırlar.
Örneğin, aşağıdaki kodda myVariable değişkeni, tanımlanmadan önce kullanılmıştır ancak hata vermez:

```
console.log(myVariable);
var myVariable = "Hello World!";
```

Detay: https://www.w3schools.com/js/js_hoisting.asp

Bu kodun yürütülmesi sırasında, JavaScript motoru değişkenin tanımını, kodun yukarı kısmına (global etki alanına) taşır ve undefined değeri ile başlar. Bu nedenle, console.log(myVariable) ifadesi undefined değerini yazdırır.
Ancak, let ve const anahtar kelimeleriyle tanımlanan değişkenlerde hoisting (kaldırma) meydana gelmez. Bu nedenle, let veya const anahtar kelimeleri kullanıldığında, değişkenin tanımlandığı yerde kullanılmadan önce tanımlanmış olması gerekir. Aksi halde, "ReferenceError: x is not defined" gibi bir hata mesajı alınır.
Thread: JavaScript, tek iş parçacıklı (single-threaded) bir programlama dilidir, bu nedenle JavaScript'te doğrudan Thread (iş parçası) kavramı bulunmaz. Bu, JavaScript'in yalnızca tek bir iş parçası (main thread) üzerinde çalıştığı anlamına gelir. Bu nedenle, JavaScript'te birden fazla işi aynı anda yapmak istediğinizde, örneğin uzun süren bir işlemi arka planda çalıştırmak istediğinizde, bu işlemi asenkron fonksiyonlar veya Web Worker API gibi alternatif yöntemler kullanarak yapabilirsiniz.
Asenkron fonksiyonlar, JavaScript'te bir işlem bitmeden diğer işlemlere devam etmek için kullanılır. Bu sayede, uzun süren bir işlemi gerçekleştirmek için beklemek yerine, işlem gerçekleştirilirken diğer işlemleri yapabilirsiniz. Örneğin, bir dosya veya bir veritabanı üzerinde işlem yaparken, işlem tamamlanana kadar kullanıcının diğer işlemlerini yapmasına izin vermek isteyebilirsiniz.
Web Worker API, JavaScript kodunu birkaç farklı iş parçasında (thread) çalıştırmanızı sağlar. Bu sayede, ana işlemle aynı anda çalışan bir iş parçası oluşturabilirsiniz. Web Worker API, tarayıcılarda kullanılabilen bir özelliktir ve genellikle kullanıcı arayüzü işlemlerini yavaşlatmadan uzun süren işlemleri gerçekleştirmek için kullanılır.
Dependency: JavaScript'te "dependency" terimi, bir JavaScript projesinde kullanılan dışarıdan alınan veya yaratılan diğer modüllere ihtiyaç duyma durumunu ifade eder. Bu modüller, başka bir yerde tanımlanmış fonksiyonlar, sınıflar, değişkenler, paketler vb. olabilir.
Bir JavaScript projesinde, bir modülün veya kütüphanenin diğer modüller tarafından kullanılabilmesi için öncelikle bu modülün projede bir bağımlılık olarak tanımlanması gerekir. Bu bağımlılık, genellikle bir paket yöneticisi aracılığıyla projeye eklenir.
Bir JavaScript projesinin bağımlılıkları, genellikle "package.json" adlı bir dosyada tanımlanır. Bu dosya, projenin bağımlılıklarını ve bağımlılıkların sürümlerini listeler. Bağımlılıklar, "npm" veya "yarn" gibi paket yöneticileri aracılığıyla projeye eklenebilir.
Bağımlılıkların yönetimi, bir projenin çalışması için kritik önem taşır. Eğer bir bağımlılık güncellenirse veya kaldırılırsa, projenin çalışması da etkilenebilir. Bu nedenle, projelerin bağımlılıklarını yönetmek ve güncellemek, geliştirme sürecinde önemli bir adımdır.
Örneğin, bir React projesi geliştiriyorsunuz ve "axios" adlı bir HTTP kütüphanesini kullanarak bir API'den veri çekmek istiyorsunuz. Bu durumda, "axios" kütüphanesi bir bağımlılık olarak projenize eklenir. Bağımlılığı "package.json" dosyasına eklemek için aşağıdaki komutu kullanabilirsiniz:

```
npm install axios --save
```

Bu komut, "axios" kütüphanesini projenize ekler ve "package.json" dosyasına ekler. "--save" parametresi, "axios" kütüphanesinin projenin bağımlılıkları listesine (dependencies) eklenmesini sağlar.
Value:

###  Rest Operator(...): 

Rest Parametresi, fonksiyonlara sınır sayısı olmadan parametre geçmemize olanak verir ve bizim isteğimiz harici kalan tüm öğeleri bir dizide toplar.
Detay: https://www.hakanbaykara.com/blog/javascriptte-rest-ve-spread-operatorleri-kullanimi-ve-farklari/

### Spread Oparator(...): 

Spread Operatörü; String, Array veya Object değişmezlerini genişletmemize yardımcı olur.
Detay: https://www.hakanbaykara.com/blog/javascriptte-rest-ve-spread-operatorleri-kullanimi-ve-farklari/

### Mutable:

Değer oluşturulduğunda, değiştirilebilir.
Detay: https://hakirac.medium.com/javascriptde-immutable-de%C4%9Fi%C5%9Fmez-ve-mutable-de%C4%9Fi%C5%9Fir-mimarisi-1b2883ca7afb

### Immutable: 

Değer oluşturulduğunda, değiştirilemez
Detay: https://hakirac.medium.com/javascriptde-immutable-de%C4%9Fi%C5%9Fmez-ve-mutable-de%C4%9Fi%C5%9Fir-mimarisi-1b2883ca7afb

### Mutate 
doğrudan değiştirmeden

### Render 
Ekrana yazdırma.

### Re-render
Ekrana tekrar yazdırma.

### Immediate Re-Export
Anında yeniden dışa aktarma

### Ternary Conditional Operators
Üç değişkenli koşul operatörleri

### Statement

### Expression

### Declaration

### Component(React)

### Props(React)

### State(React)

### Hooks(React)

### Cleanup Function(useEffect vs. için)

### Component Lifecycle (React)

### Array Destructuring(React):

### Object Destructuring(React):

### Key(React)

JavaScript'te "key" terimi, genellikle React gibi arayüz kitaplıklarında kullanılan bir özelliktir. "key" özelliği, bir listede veya başka bir grup elemanlar arasında benzersiz bir tanımlayıcı olarak kullanılır.
Örneğin, bir React uygulamasında bir liste görüntülemek istediğinizde, her öğe için benzersiz bir "key" özelliği belirlemelisiniz. Bu özellik, React'in liste elemanlarının etkili bir şekilde yeniden oluşturulmasına yardımcı olur.
React, bir öğenin anahtarını değiştirirseniz, öğenin tamamen yeniden oluşturulacağını ve bu nedenle performans sorunlarına neden olabileceğini bilir. Bu nedenle, öğeler arasında benzersiz bir "key" özelliği kullanmak önemlidir.
Örneğin, aşağıdaki kodda "key" özelliği "person.id" olarak belirlenmiştir:

```
{persons.map(person => (
  <div key={person.id}>
    <span>{person.name}</span>
    <span>{person.age}</span>
  </div>
))}
```

Bu örnekte, "persons" adlı bir dizi veri kullanılarak bir liste oluşturulmuştur. Her bir öğe için benzersiz bir "key" özelliği olarak "person.id" kullanılmıştır. Bu özellik, her öğenin benzersiz olarak tanımlanmasını sağlar ve liste elemanlarının yeniden oluşturulmasını etkili bir şekilde yönetir.

### Mount

JavaScript'te "Mount" terimi, genellikle React ve diğer arayüz kitaplıklarında kullanılan bir kavramdır. "Mount" işlemi, bir bileşenin ilk kez arayüze eklenmesi anlamına gelir.
Örneğin, bir React bileşeni, sayfa yüklendiğinde ilk kez "mount" edilir. Bu aşamada, bileşenin hayat döngüsü yöntemleri (lifecycle methods) çağrılır ve bileşen hazırlanır.
React bileşenlerinin hayat döngüsünde, "componentDidMount()" adlı bir yöntem, bileşenin ilk kez "mount" edildiğinde çağrılır. Bu yöntem, bileşenin hazırlık işlemlerinin tamamlandığı anlamına gelir.
Örneğin, aşağıdaki kodda bir React bileşeni "MyComponent" tanımlanmıştır. "componentDidMount()" yöntemi, bileşen "mount" edildiğinde "console.log()" fonksiyonu çağrılarak bir mesaj yazdırır:

```
import React, { Component } from 'react';
class MyComponent extends Component {
  componentDidMount() {
    console.log('MyComponent is mounted!');
  }
  render() {
    return (
      <div>
        <h1>Hello World!</h1>
      </div>
    );
  }
}
export default MyComponent;
```

Tabii, bu örnekte "MyComponent" adlı bir React sınıf bileşeni tanımlanmıştır. Bu bileşen, "Component" adlı üst sınıfı genişletir ve bu sayede React'in özelliklerinden yararlanabilir.
Bileşenin "componentDidMount()" yöntemi, bileşenin "mount" edildiğinde otomatik olarak çağrılır. Bu örnekte, "componentDidMount()" yöntemi, konsola "MyComponent is mounted!" mesajını yazdırır.
Bileşenin "render()" yöntemi, bileşenin arayüzünü tanımlar. Bu örnekte, "render()" yöntemi, bir "div" bileşeni içinde bir "h1" başlığı içeren "Hello World!" metnini döndürür.
Son olarak, "MyComponent" bileşeni, dışa aktarılır ve başka bir dosyada kullanılabilir hale gelir.
Bu örnekte, "Mount" işlemi, React sınıf bileşenlerinin hayat döngüsünde önemli bir yer tutar ve bileşenin arayüze ilk kez eklenmesini ifade eder. "componentDidMount()" yöntemi, bileşen "mount" edildiğinde çağrıldığı için, "Mount" işlemi tamamlanmış demektir ve işlemlere devam edilebilir.

### Unmount: 
"Unmount" işlemi, bir React bileşeninin arayüzden kaldırılmasıdır ve bu işlem sırasında "componentWillUnmount()" yöntemi otomatik olarak çağrılır. Bu yöntem, bileşenin "unmount" işlemi sırasında yapılması gereken temizleme veya sonlandırma işlemlerinin yapılması için kullanılabilir.
Örneğin, bir bileşen "mount" edildiğinde, bir zamanlayıcı başlatılabilir. Bileşen "unmount" edildiğinde, bu zamanlayıcı durdurulmalıdır. Bunun için "componentWillUnmount()" yöntemi kullanılabilir.
İşte, bir React sınıf bileşeninde "Unmount" işleminin nasıl kullanılabileceğiyle ilgili basit bir örnek:

```
import React, { Component } from 'react';
class MyComponent extends Component {
  constructor(props) {
    super(props);
    this.timer = null;
  }
  componentDidMount() {
    this.timer = setInterval(() => {
      console.log('Tick');
    }, 1000);
  }
  componentWillUnmount() {
    clearInterval(this.timer);
  }
  render() {
    return (
      <div>
        <h1>Hello World!</h1>
      </div>
    );
  }
}
export default MyComponent;
```

Bu örnekte, "MyComponent" adlı bir React sınıf bileşeni tanımlanmıştır. Bileşen, "constructor()" yöntemiyle bir "timer" adlı değişkeni "null" olarak başlatır.
Bileşen "mount" edildiğinde, "componentDidMount()" yöntemi çağrılır. Bu yöntem, "setInterval()" fonksiyonunu kullanarak bir zamanlayıcı oluşturur ve her saniye "Tick" mesajını konsola yazdırır. Zamanlayıcı, "this.timer" değişkenine atanan referans ile kaydedilir.
Bileşen "unmount" edildiğinde, "componentWillUnmount()" yöntemi çağrılır. Bu yöntem, "this.timer" değişkeninin var olup olmadığını kontrol eder. Eğer değişken varsa, "clearInterval()" fonksiyonunu kullanarak zamanlayıcıyı durdurur ve "this.timer" değişkenini "null" olarak ayarlar.
Böylece, "Unmount" işlemi sırasında bileşenin "componentWillUnmount()" yöntemi sayesinde, oluşturulan zamanlayıcının durdurulması sağlanmış olur. Bu da bellek sızıntısı ve performans sorunlarının önlenmesine yardımcı olur.

### Initializations: 

```
constructor()
```

```
super()
```
## Matematik Fonksiyonları

JavaScript'te matematik işlemlerini yapmak için kullanabileceğiniz birçok farklı fonksiyon bulunur. Aşağıda, JavaScript'te bulunan tüm matematik fonksiyonları ve örnekleri yer almaktadır:

### Math.abs(x): 

Bir sayının mutlak değerini döndürür.
```
console.log(Math.abs(-5)); // 5
```

### Math.ceil(x): 

Bir sayıyı yukarı yuvarlar.
```
console.log(Math.ceil(3.14)); // 4
```

### Math.floor(x): 

Bir sayıyı aşağı yuvarlar.
```
console.log(Math.floor(3.99)); // 3
```

### Math.round(x):

Bir sayıyı en yakın tam sayıya yuvarlar.
```
console.log(Math.round(3.5)); // 4
```

### Math.min(x, y, z, ...): 

Verilen sayıların en küçüğünü döndürür.
```
console.log(Math.min(1, 2, 3)); // 1
```

### Math.max(x, y, z, ...): 

Verilen sayıların en büyüğünü döndürür.
```
console.log(Math.max(1, 2, 3)); // 3
```

### Math.pow(x, y):

Bir sayının üssünü hesaplar.
```
console.log(Math.pow(2, 3)); // 8
```

### Math.sqrt(x): 

Bir sayının karekökünü hesaplar.
```
console.log(Math.sqrt(16)); // 4
```

### Math.random():

0 ile 1 arasında rastgele bir ondalıklı sayı döndürür.
```
console.log(Math.random()); // 0.5870397381056959
```

### Math.sin(x): 

Bir açının sinüsünü hesaplar.
```
console.log(Math.sin(Math.PI / 2)); // 1
```

### Math.cos(x): 

Bir açının kosinüsünü hesaplar.
```
console.log(Math.cos(Math.PI)); // -1
```

### Math.tan(x):

Bir açının tanjantını hesaplar.
```
console.log(Math.tan(Math.PI / 4)); // 0.9999999999999999
```

### Math.asin(x): 

Bir sayının arcsinüsünü hesaplar.
```
console.log(Math.asin(1)); // 1.5707963267948966
```

### Math.acos(x):

Bir sayının arccosinüsünü hesaplar.
```
console.log(Math.acos(-1)); // 3.141592653589793
```

### Math.atan(x): 

Bir sayının arctanjantını hesaplar.
```
console.log(Math.atan(1)); // 0.7853981633974483
```

## Dize Fonksiyonları

### charAt(index): 

Belirtilen dizindeki karakteri döndürür.
Örnek:
```
const str = 'Merhaba';
console.log(str.charAt(0)); // "M"
```

### concat(str1, str2, ...): 

Bir veya daha fazla dizeyi birleştirir.
Örnek:
```
const str1 = 'Merhaba';
const str2 = 'Dünya';
console.log(str1.concat(' ', str2)); // "Merhaba Dünya"
```

### includes(searchString, position): 

Belirtilen bir alt dizenin orijinal dizide var olup olmadığını kontrol eder.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.includes('Dünya')); // true
console.log(str.includes('dünya')); // false
```

### endsWith(searchString, length): 

Bir dizenin belirtilen alt dizelerle bitip bitmediğini kontrol eder.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.endsWith('Dünya')); // true
console.log(str.endsWith('Merhaba')); // false
```

### indexOf(searchValue, fromIndex): 

Belirtilen bir alt dizinin ilk oluşumunun dizinini döndürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.indexOf('Dünya')); // 8
console.log(str.indexOf('dünya')); // -1
```

### lastIndexOf(searchValue, fromIndex): Belirtilen bir alt dizinin son oluşumunun dizinini döndürür.

Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.lastIndexOf('a')); // 9
console.log(str.lastIndexOf('dünya')); // -1
```

### match(regexp): 

Bir dizedeki bir düzenli ifadeyi arar ve sonuçları döndürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.match(/Dünya/)); // ["Dünya", index: 8, input: "Merhaba Dünya", groups: undefined]
console.log(str.match(/dünya/)); // null
```

### replace(regexp|substr, newSubStr|function): 

Bir dizenin belirli karakterlerini yeni bir dizeyle değiştirir.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.replace('Dünya', 'Mars')); // "Merhaba Mars"
```

### search(regexp): 

Bir dizede belirli bir düzenli ifadeyi arar ve ilk eşleşmenin indeksini döndürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.search(/Dünya/)); // 8
console.log(str.search(/dünya/)); // -1
```

### slice(beginIndex, endIndex): 

Bir dizenin belirli bir kısmını bir başlangıç ve bir bitiş dizini aralığında keser.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.slice(0, 7)); // "Merhaba"
```

### split(separator, limit): Bir dizeyi belirli bir ayırıcı karakterine göre böler ve parçalarını bir diziye koyar.

Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.split(' ')); // ["Merhaba", "Dünya"]
```

### startsWith(searchString, position): 

Bir dizenin belirtilen bir alt dizeyle başlayıp başlamadığını kontrol eder.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.startsWith('Merhaba')); // true
console.log(str.startsWith('Dünya')); // false
```

### substring(indexStart, indexEnd): 

Bir dizenin belirtilen bir dizin aralığındaki karakterlerini döndürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.substring(0, 7)); // "Merhaba"
```

### toLocaleLowerCase(): 

Bir dizenin tüm karakterlerini küçük harfe dönüştürür.
Örnek:
```
const str = 'MERHABA DÜNYA';
console.log(str.toLocaleLowerCase()); // "merhaba dünya"
```

### toLocaleUpperCase(): 

Bir dizenin tüm karakterlerini büyük harfe dönüştürür.
Örnek:
```
const str = 'merhaba dünya';
console.log(str.toLocaleUpperCase()); // "MERHABA DÜNYA"
```

### toLowerCase(): 

Bir dizenin tüm karakterlerini küçük harfe dönüştürür.
Örnek:
```
const str = 'MERHABA DÜNYA';
console.log(str.toLowerCase()); // "merhaba dünya"
```

### toString(): 

Bir dizeyi string veri tipine dönüştürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.toString()); // "Merhaba Dünya"
```

### toUpperCase(): 

Bir dizenin tüm karakterlerini büyük harfe dönüştürür.
Örnek:
```
const str = 'merhaba dünya';
console.log(str.toUpperCase()); // "MERHABA DÜNYA"
```

### trim(): 

Bir dizenin başındaki ve sonundaki boşlukları kaldırır.
Örnek:
```
const str = '   Merhaba Dünya   ';
console.log(str.trim()); // "Merhaba Dünya"
```

### valueOf(): 

Bir dizeyi primitive veri tipine dönüştürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.valueOf()); // "Merhaba Dünya"
```

### Dizi Fonksiyonları

## concat()
```
```

## copyWithin()
```
```
## entries()
```
```

## every()
```
```

## fill()
```
```

## filter()
```
```

## find()
```
```

## findIndex()
```
```

## flat()
```
```

## flatMap()
```
```

## forEach()
```
```

## from()
```
```

## includes()
```
```

## indexOf()
```
```

## isArray()
```
```

## join()
```
```

## keys()
```
```

## lastIndexOf()
```
```

## map()
```
```

## pop()
```
```

## push()
```
```

## reduce()
```
```

## reduceRight()
```
```

## reverse()
```
```

## shift()
```
```

## slice()
```
```

## some()
```
```

## sort()
```
```

## splice()
```
```

## toLocaleString()
```
```

## toString()
```
```

## unshift()
```
```

## values()
```
```

### Zamanlama Fonksiyonları
JavaScript'te kullanabileceğiniz birkaç zamanlama fonksiyonu şunlardır:

## setTimeout()

```
function showAlert() {
  alert("1 saniye sonra gösterildi!");
}
setTimeout(showAlert, 1000);
```

## setInterval()

```
let count = 0;
let intervalId = setInterval(() => {
  console.log(count);
  count++;
}, 1000);
```

## clearTimeout()

```
let timeoutId = setTimeout(() => {
  console.log("Bu mesaj bir saniye sonra yazdırılacak.");
}, 1000);
clearTimeout(timeoutId);
```

## clearInterval()

```
let count = 0;
let intervalId = setInterval(() => {
  console.log(count);
  count++;
  if (count === 5) {
    clearInterval(intervalId);
  }
}, 1000);
```

## requestAnimationFrame()

```
let box = document.getElementById("box");
let position = 0;
function animate() {
  position += 1;
  box.style.left = position + "px";
  requestAnimationFrame(animate);
}
```

## requestAnimationFrame(animate);

```
setImmediate()
setImmediate(() => {
  console.log("Bu mesaj hemen yazdırılacak.");
});
```

## clearImmediate()

```
let immediateId = setImmediate(() => {
  console.log("Bu mesaj hemen yazdırılacak.");
});
clearImmediate(immediateId);

process.nextTick()
console.log("1. adım");
process.nextTick(() => {
  console.log("3. adım");
});
console.log("2. adım");
```

### DOM Manipülasyon Fonksiyonları

## getElementById(): 
Belirtilen id değeri ile eşleşen ilk HTML elemanını döndürür.
```
```

## getElementsByClassName(): 
Belirtilen sınıf adına sahip tüm HTML elemanlarını bir HTMLCollection nesnesi olarak döndürür.
```
```

## getElementsByTagName(): 
Belirtilen etiket adı ile eşleşen tüm HTML elemanlarını bir HTMLCollection nesnesi olarak döndürür.
```
```

## querySelector(): 
CSS seçicisi ile eşleşen ilk HTML elemanını döndürür.
```
```

## querySelectorAll(): 
CSS seçicisi ile eşleşen tüm HTML elemanlarını bir NodeList nesnesi olarak döndürür.
```
```

## createElement(): 
Belirtilen HTML etiketi ile yeni bir HTML elemanı oluşturur.
```
```

## createTextNode(): 
Belirtilen metin içeriği ile yeni bir Text düğümü oluşturur.
```
```

## appendChild(): 
Belirtilen HTML elemanını bir başka HTML elemanının alt öğesi olarak ekler.
```
```

## removeChild(): 
Bir HTML elemanının alt öğesini kaldırır.
```
```

## replaceChild(): 
Bir HTML elemanının alt öğesini başka bir HTML elemanı ile değiştirir.
```
```

## insertBefore(): 
Bir HTML elemanını, belirtilen diğer bir HTML elemanının önüne ekler.
```
```

## setAttribute(): 
Bir HTML elemanına belirtilen nitelik adı ve değerini ekler veya günceller.
```
```

## getAttribute(): 
Belirtilen nitelik adına sahip bir HTML elemanının değerini döndürür.
```
```

## removeAttribute(): 
Bir HTML elemanından belirtilen niteliği kaldırır.
```
```

## classList.add(): 
Bir HTML elemanına belirtilen sınıf adını ekler.
```
```

## classList.remove(): 
Bir HTML elemanından belirtilen sınıf adını kaldırır.
```
```

## classList.toggle(): 
Bir HTML elemanında belirtilen sınıf adını ekler veya kaldırır.
```
```

## style.setProperty(): 
Belirtilen stil özelliğine belirtilen değeri atar veya günceller.
```
```

## style.removeProperty(): 
Belirtilen stil özelliğini kaldırır.
```
```

## addEventListener(): 
Belirtilen olay dinleyicisini bir HTML elemanına ekler.
```
```

## removeEventListener(): 
Belirtilen olay dinleyicisini bir HTML elemanından kaldırır.
```
```

## event.preventDefault(): 
Belirtilen olayın varsayılan davranışını önler.
```
```

## event.stopPropagation(): 
Bir olayın daha fazla elemanlara yayılmasını engeller.
```
```

## event.target: 
Bir olayın hedef HTML elemanını döndürür.
```
```

## event.currentTarget: 
Bir olayı dinleyen HTML elemanını döndürür.
```
```

### Koşullu İfadeler ve Döngüler
### Nesne Fonksiyonları
### Tarayıcı İşlevleri
### Ağ İşlevleri
### Dosya İşlevleri
### Local Storage Fonksiyonları
### JSON Fonksiyonları
### Hata Yakalama ve Ayıklama
### Yapıcı Fonksiyonlar ve Prototipler
### Asenkron Programlama (Promise, Async/Await, Callback)
### RegEx (Düzenli İfadeler) Fonksiyonları
### Fonksiyonlar için Argümanlar ve Değerleri
### Dosya İşlemleri
### Şifreleme ve Güvenlik
### Diğer Özellikler ve Fonksiyonlar
