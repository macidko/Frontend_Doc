# ****Aldığım notları yazdığım, yeni öğrendiklerimi geçirdiğim ve ihtiyacım olursa dönüp bakacağım yer.****

## Değişken (Variable):
Değerlerin depolanması için kullanılan yapıdır. JavaScript'te değişkenler var, let ve const anahtar kelimeleri ile tanımlanabilir.
```
let firstName = "John";
```
Burada let, const ve var anahtar kelimeleri ile sırasıyla değişkenler tanımlanmıştır. let ve const blok kapsamına sahipken, var ise fonksiyon veya global kapsama sahip olabilir. firstName deği

## Fonksiyon (Function):
JavaScript'te fonksiyonlar birer nesnedir. Kod bloklarını paketler ve bir işlevi gerçekleştirmek için kullanılır. Fonksiyonlar, parametreleri alabilir ve geri dönüş değeri üretebilirler.
```
function helloWorld() {
  console.log("Hello, World!");
}

helloWorld();
```
## Dizi (Array):
JavaScript'te bir dizi birden fazla değerin depolanması için kullanılır. Diziler, [] işaretleri arasına değerlerin virgülle ayrılması ile tanımlanır.
```
let numbers = [1, 2, 3, 4, 5];
console.log(numbers); // [1, 2, 3, 4, 5]
```

## Nesne (Object):
JavaScript'te bir nesne, özelliklerin (properties) ve yöntemlerin (methods) bir arada depolandığı bir yapıdır. Nesneler {} işaretleri ile tanımlanır.
```
const obje = {
  isim: 'Ahmet',
  soyisim: 'Yılmaz',
  yas: 30,
  adres: {
    sehir: 'Ankara',
    ilce: 'Çankaya',
    postaKodu: 06500
  }
};

console.log(obje);
```

## Sınıf (Class):
Sınıf, nesnelerin şablonlarını tanımlar. JavaScript'te sınıflar ES6 sürümünden itibaren kullanılmaktadır.
```
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }

  getArea() {
    return this.width * this.height;
  }
}

// Rectangle sınıfından bir nesne oluşturun
const rect1 = new Rectangle(5, 10);

// getArea() yöntemini çağırın
console.log(rect1.getArea()); // 50 yazdırır

```
## Metod (Method):
Bir nesnenin özelliklerine erişmek veya işlem yapmak için kullanılan fonksiyonlara metod denir.

JavaScript'te bir yöntem (method), bir nesne tarafından desteklenen ve o nesneyle ilgili bir işlemi gerçekleştiren işlevsel bir kod parçasıdır. Bir yöntem, bir nesne örneği üzerinde çağrılabilir ve o nesne örneği için bir işlem yapar.

Bir JavaScript yöntemi, bir fonksiyonun bir özelliğinin bir parçası olarak tanımlanır ve genellikle bir nesne örneği üzerinde çağrılır. Yöntemler, nesne özellikleri gibi "this" anahtar kelimesini kullanarak nesne özelliklerine erişebilir ve bu özellikleri değiştirebilir.

Örneğin, aşağıdaki örnekte, "person" adlı bir nesne tanımlıyoruz ve "sayHello" adlı bir yöntem ekliyoruz:
```
let person = {
  name: "Ahmet",
  age: 30,
  sayHello: function() {
    console.log(`Merhaba, benim adım ${this.name} ve ben ${this.age} yaşındayım.`);
  }
};

// sayHello() yöntemini çağırın
person.sayHello(); // "Merhaba, benim adım Ahmet ve ben 30 yaşındayım." yazdırır
```
Yukarıdaki örnekte, "sayHello" yöntemi, "person" nesne örneği üzerinde çağrılır ve nesne özelliklerine erişir (this.name ve this.age) ve bir mesaj oluşturur.

## Parametre (Parameter):
JavaScript'te parametreler, fonksiyonlara aktarılan verilerdir. Fonksiyonlar, parametrelerin kullanılması yoluyla belirli bir işlevi yerine getirirler.

Parametreler, bir fonksiyonun tanımında parantez içinde belirtilir ve fonksiyonun çağrılmasında argümanlar olarak geçirilirler. Argümanlar, fonksiyonun işlevini gerçekleştirmesi için gereken verilerdir.

Aşağıdaki örnekte, bir fonksiyon iki parametre alır ve bu parametreleri kullanarak basit bir hesaplama yapar:
```
function multiply(num1, num2) {
  return num1 * num2;
}

let result = multiply(5, 10);
console.log(result); // 50 yazdırır
```
Yukarıdaki örnekte, "multiply" adlı bir fonksiyon tanımlıyoruz ve bu fonksiyon "num1" ve "num2" adlı iki parametre alıyor. Bu parametreler, fonksiyon çağrısında argümanlarla eşleştirilir. Fonksiyon, parametreler aracılığıyla verilen argümanları kullanarak bir işlem gerçekleştirir ve sonucu döndürür.

"Fonksiyonlar" adlı bir konuda daha örnekler ve detaylı açıklamalar yer almaktadır, buraya da bakabilirsiniz.

## Argüman (Argument):
JavaScript'te argümanlar, bir fonksiyonun çağrılması sırasında fonksiyona geçirilen değerlerdir. Bu değerler, fonksiyonun işlevini gerçekleştirmesi için gerekli olan verilerdir.

Argümanlar, bir fonksiyonun parantez içinde belirtilen parametrelerle eşleştirilir. Fonksiyon parametreleri ile argümanlar arasındaki eşleştirme sırasına göre belirlenir. Örneğin, bir fonksiyonun üç parametresi varsa ve fonksiyon çağrısı sırasında sadece iki argüman geçirilirse, fonksiyonun ilk iki parametresi, geçirilen argümanlarla eşleştirilir ve üçüncü parametre "undefined" olarak atanır.

Aşağıdaki örnekte, "multiply" adlı bir fonksiyon tanımlıyoruz ve bu fonksiyon iki argüman alıyor:
```
function multiply(num1, num2) {
  return num1 * num2;
}

let result = multiply(5, 10);
console.log(result); // 50 yazdırır
```
Yukarıdaki örnekte, "multiply" fonksiyonunu çağırırken iki argüman geçiriyoruz: 5 ve 10. Bu argümanlar, fonksiyonun "num1" ve "num2" parametreleri ile eşleştirilir ve fonksiyon, bu parametreler aracılığıyla çarpma işlemini gerçekleştirir ve sonucu döndürür.

"Fonksiyonlar" adlı bir konuda daha örnekler ve detaylı açıklamalar yer almaktadır, buraya da bakabilirsiniz.

## Operatör (Operator):
İki veya daha fazla değeri birleştirmek, karşılaştırmak veya işlemek için kullanılan sembollerdir.

Aritmetik operatörler:
Toplama (+): Sayıları toplar veya stringleri birleştirir.
Çıkarma (-): Sayılardan bir sayıyı diğerinden çıkarır.
Çarpma (*): Sayıları çarpar.
Bölme (/): Bir sayıyı diğerine böler.
Mod (%) : İlk sayıyı ikinci sayıya böler ve kalanı döndürür.
```
let num1 = 10;
let num2 = 3;

console.log(num1 + num2); // 13
console.log(num1 - num2); // 7
console.log(num1 * num2); // 30
console.log(num1 / num2); // 3.3333333333333335
console.log(num1 % num2); // 1
```

Karşılaştırma operatörleri:

Eşitlik (==): İki değer eşit ise true döndürür.
Katı eşitlik (===): İki değer hem tür hem de değer açısından eşit ise true döndürür.
Eşit değil (!=): İki değer farklı ise true döndürür.
Katı eşit değil (!==): İki değer hem tür hem de değer açısından farklı ise true döndürür.
Büyüktür (>): Sol taraftaki sayı sağ taraftakinden büyükse true döndürür.
Küçüktür (<): Sol taraftaki sayı sağ taraftakinden küçükse true döndürür.
Büyük eşit (>=): Sol taraftaki sayı sağ taraftakinden büyük veya eşitse true döndürür.
Küçük eşit (<=): Sol taraftaki sayı sağ taraftakinden küçük veya eşitse true döndürür.
```
let num1 = 10;
let num2 = 3;
let str1 = "10";

console.log(num1 == str1); // true
console.log(num1 === str1); // false
console.log(num1 != num2); // true
console.log(num1 !== str1); // true
console.log(num1 > num2); // true
console.log(num1 < num2); // false
console.log(num1 >= num2); // true
console.log(num1 <= num2); // false
```

Mantıksal operatörler:

Ve (&&): İki koşulun da doğru olması durumunda true döndürür.
Veya (||): En az bir koşulun doğru olması durumunda true döndürür.
Değil (!): Koşulun tersini döndürür.
```
let num1 = 10;
let num2 = 3;
let str1 = "10";

console.log(num1 > num2 && num1 == str1); // true
console.log(num1 > num2 || num1 < num2); // true
console.log(!(num1 > num2)); // false
```
Atama operatörleri:

Eşittir (=): Değer ataması yapar.
Toplama eşittir (+=): Değişkenin değerine bir sayı ekler ve sonucu tekrar değişkene atar.
Çıkarma eşittir (-=): Değişkenin değerinden bir sayı çıkarır ve sonucu tekrar değişkene atar.
Çarpma eşittir (*=): Değişkenin değerini bir sayıyla çarpar ve sonucu tekrar değişkene atar.
Bölme eşittir (/=): Değişkenin değerini bir sayıya böler ve sonucu tekrar değişkene atar.
```
let num1 = 10;

num1 += 5; // num1 = num1 + 5;
console.log(num1); // 15

num1 -= 3; // num1 = num1 - 3;
console.log(num1); // 12

num1 *= 2; // num1 = num1 * 2;
console.log(num1); // 24

num1 /= 4; // num1 = num1 / 4;
console.log(num1); // 6
```
Bitişik operatörler:

Arttır (++) : Değişkenin değerini 1 arttırır.
Azalt (--) : Değişkenin değerini 1 azaltır.
```
let num1 = 10;

console.log(num1++); // 10
console.log(num1); // 11

console.log(++num1); // 12

console.log(num1--); // 12
console.log(num1); // 11

console.log(--num1); // 10
```
Diğer operatörler:

Ternary (?:) : İf-else yapısının kısaltılmış halidir.
Virgül (,) : Birden fazla ifadeyi birleştirir ve son ifadenin değerini döndürür.
```
let num1 = 10;
let num2 = 3;

let max = (num1 > num2) ? num1 : num2;
console.log(max); // 10

let sum = (num1 += 2, num2 += 2, num1 + num2);
console.log(sum); // 17
```
Bit operatörleri:

AND (&) : İki sayının ikilik tabandaki karşılıklarındaki bitlerin her ikisinde de 1 olan bitleri 1 olarak belirler.
OR (|) : İki sayının ikilik tabandaki karşılıklarındaki bitlerin herhangi birinde 1 olan bitleri 1 olarak belirler.
XOR (^) : İki sayının ikilik tabandaki karşılıklarındaki bitlerin sadece birinde 1 olan bitleri 1 olarak belirler.
NOT (~) : Bir sayının ikilik tabandaki karşılığını alır ve her biti tersine çevirir.
Left Shift (<<) : Bir sayının ikilik tabandaki karşılığını belirtilen sayı kadar sola kaydırır ve boşlukları 0 ile doldurur.
Right Shift (>>) : Bir sayının ikilik tabandaki karşılığını belirtilen sayı kadar sağa kaydırır ve boşlukları en sol bitin değerine göre doldurur.
Zero-fill Right Shift (>>>) : Bir sayının ikilik tabandaki karşılığını belirtilen sayı kadar sağa kaydırır ve boşlukları 0 ile doldurur.
```
let num1 = 10; // 1010 (ikilik tabanda)
let num2 = 5; // 0101 (ikilik tabanda)

let and = num1 & num2; // 0000
console.log(and); // 0

let or = num1 | num2; // 1111
console.log(or); // 15

let xor = num1 ^ num2; // 1111
console.log(xor); // 15

let not = ~num1; // -11 (ikilik tabanda)
console.log(not); // -11

let leftShift = num1 << 2; // 101000 (ikilik tabanda)
console.log(leftShift); // 40

let rightShift = num1 >> 1; // 0101 (ikilik tabanda)
console.log(rightShift); // 5

let zeroFillRightShift = num1 >>> 1; // 0101 (ikilik tabanda)
console.log(zeroFillRightShift); // 5
```
Diğer operatörler:

Delete : Bir nesne özelliğini veya bir dizinin elemanını siler.
Typeof : Bir değerin veri türünü belirler.
Void : Bir ifadeyi değer döndürmeden işler.
In : Bir özelliğin bir nesne içinde var olup olmadığını belirler.
Instanceof : Bir nesnenin belirli bir sınıfın örneği olup olmadığını belirler.

```
// typeof operatörü
let num = 5;
let str = "Hello";
console.log(typeof num); // "number"
console.log(typeof str); // "string"

// delete operatörü
let obj = { name: "John", age: 30 };
delete obj.age;
console.log(obj); // { name: "John" }

let arr = [1, 2, 3];
delete arr[1];
console.log(arr); // [1, undefined, 3]

// in operatörü
console.log("name" in obj); // true
console.log(1 in arr); // true

// instanceof operatörü
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

const person1 = new Person("Alice", 25);

console.log(person1 instanceof Person); // true
console.log(person1 instanceof Object); // true
```

## Koşul ifadesi (Conditional statement):
Belirli bir koşulun sağlanıp sağlanmadığını kontrol ederek, farklı kod bloklarının çalıştırılmasını sağlayan ifadelerdir. JavaScript'te if-else, switch-case gibi koşul ifadeleri bulunmaktadır.

## Döngü (Loop):
Belirli bir kod bloğunun, belirli bir koşul sağlanana kadar veya belirli bir sayıda kez çalıştırılmasını sağlayan yapılardır. JavaScript'te for, while, do-while gibi döngü yapıları bulunmaktadır.

## Callback fonksiyonu (Callback function):
Bir fonksiyonun, başka bir fonksiyona argüman olarak geçirilmesidir. Bu, fonksiyonların modülerliğini artırır.

## DOM (Document Object Model):
Web sayfalarının, HTML, XML ve XHTML gibi belge türlerinin birer nesne olarak temsil edildiği bir platformdır.

## İç içe fonksiyonlar (Nested functions):
Bir fonksiyon içinde tanımlanan ve o fonksiyon tarafından çağrılan fonksiyonlardır.

## Rekürsif fonksiyon (Recursive function):
Kendi kendini çağıran bir fonksiyondur.

## Kalıtım (Inheritance):
Bir sınıfın özelliklerinin ve metodlarının başka bir sınıf tarafından kullanılmasını sağlayan yapıdır.

## Get ve set fonksiyonları (Getters and setters):
Nesne özelliklerine değer atamak ve okumak için kullanılan özel fonksiyonlardır.

## Promise zincirleri (Promise chaining):
Birbirine bağlı promise'ların ardışık şekilde kullanılmasıdır.

## IIFE (Immediately Invoked Function Expression):
Fonksiyonu tanımladıktan sonra hemen çağırmak için kullanılan bir yapıdır.

## Strict modu (Strict mode):
JavaScript kodunun daha sıkı bir şekilde yorumlanmasını sağlayan bir yapıdır.

## Generatör fonksiyon (Generator function):
İçinde yield ifadesi bulunan fonksiyonlardır ve bu sayede asenkron işlemleri yönetmek için kullanılır.

## Async/await:
Asenkron işlemleri yönetmek için kullanılan bir yapıdır ve promise'ların daha okunaklı bir şekilde kullanılmasını sağlar.

## Fetch API:
Sunucudan veri almak için kullanılan bir arayüzdür ve XMLHttpRequest (XHR) yerine tercih edilir.

## Local Storage:
Web sayfasında veri saklamak için kullanılan bir mekanizmadır.

## Session Storage:
Oturum (session) boyunca veri saklamak için kullanılan bir mekanizmadır.

## Cookies:
Kullanıcının bilgisayarında saklanan küçük metin dosyalarıdır ve web sayfasının durumunu takip etmek için kullanılır.

## Regular Expression (Regex):
Belirli bir kalıba uygun olan metinleri seçmek için kullanılan bir dil ve yapısıdır.

## Template literals:
Bir dize içinde değişkenleri veya ifadeleri yerleştirmek için kullanılan yapıdır.

## Destructuring assignment:
Nesnelerin veya dizilerin özelliklerine veya elemanlarına tek seferde erişmek için kullanılan yapıdır.

## Asynchronous programming:
Asenkron işlemleri yönetmek için kullanılan bir yaklaşımdır ve zaman alıcı işlemlerin ana işlemi engellemeden yapılmasını sağlar.

## Event loop:
JavaScript'in asenkron işlemleri yönetmek için kullandığı bir yapıdır ve callback fonksiyonlarının sırayla işletilmesini sağlar.

## Scope:
Değişkenlerin ve fonksiyonların erişilebilirlik alanlarını tanımlar.

## Hoisting:
Değişkenlerin ve fonksiyonların tanımlarının, kodun yukarıya doğru kaldırılması yoluyla işlendiği bir yapıdır.

## Closures:
Bir fonksiyonun içinde tanımlanan fonksiyonlar, dış fonksiyondaki değişkenlere erişebilir ve bu değişkenleri koruyabilir.

## Callback hell:
Çok sayıda callback fonksiyonunun birbirine bağlı şekilde kullanıldığı, kodun okunaklılığını azaltan bir yapıdır.

## Debugging:
Kodun hatalarını bulmak ve düzeltmek için kullanılan bir süreçtir.

## Transpiling:
Yeni JavaScript özelliklerini eski tarayıcılarda da kullanabilmek için, yeni kod

## ES6 Modules:
ECMAScript 6 ile birlikte tanıtılan modül sistemi, JavaScript dosyalarını modüller halinde kullanmayı sağlar.

## Babel:
Yeni JavaScript özelliklerini eski tarayıcılarda da kullanabilmek için kullanılan bir transpiler'dır.

## Webpack:
JavaScript uygulamalarının modüler şekilde paketlenmesi için kullanılan bir araçtır.

## Virtual DOM:
React'ta kullanılan bir teknolojidir ve değişikliklerin öncelikle bir sanal DOM üzerinde yapılıp daha sonra gerçek DOM'a yansıtılmasını sağlar.

## Redux:
JavaScript uygulamalarında durum yönetimi için kullanılan bir kütüphanedir.

## JSX:
React uygulamalarında kullanılan, JavaScript ve HTML benzeri bir sözdizimi sunan bir yapıdır.

## Web Workers:
Web sayfalarında işlemlerin paralel şekilde yapılmasını sağlayan bir arayüzdür.

## Service Workers:
Web sayfalarının arka planda çalışarak çevrimdışı da çalışmasını sağlayan bir arayüzdür.

## IndexedDB:
Tarayıcının yerel veritabanıdır ve web sayfalarında veri saklamak için kullanılır.

## WebGL:
Web sayfalarında 3D grafikler oluşturmak için kullanılan bir arayüzdür.

## WebRTC:
Tarayıcılar arasında gerçek zamanlı iletişim kurmak için kullanılan bir arayüzdür.

## Accessibility:
Web sayfalarının tüm kullanıcılar için erişilebilir olmasını sağlamak için yapılan çalışmalardır.

## SEO (Search Engine Optimization):
Web sayfalarının arama motorları tarafından daha iyi indekslenebilmesi için yapılan çalışmalardır.

## Progressive Web Apps (PWA):
Web uygulamalarının, geleneksel mobil uygulamalar gibi davranmasını ve özellikler sunmasını sağlayan bir yapıdır.

## Single-page Application (SPA):
Web sayfalarının tek bir HTML sayfasında yüklenip, daha sonra JavaScript aracılığıyla içeriklerin dinamik olarak yüklenmesini sağlayan bir yapıdır.

## API (Application Programming Interface):
Bir yazılımın diğer yazılımlarla iletişim kurmasını sağlayan bir arayüzdür.

## CRUD (Create, Read, Update, Delete):
Veritabanı işlemlerinin temel işlemlerini ifade eder.

## Git:
Sürüm kontrolü için kullanılan bir yazılımdır ve kodun değişikliklerinin takibi ve geri alınması gibi işlemleri yap

## NPM (Node Package Manager):
Node.js projelerinde paket yönetimi için kullanılan bir araçtır.

## Yarn:
NPM alternatifi bir paket yöneticisidir.

## Linter:
Kod kalitesini artırmak ve hataları önceden tespit etmek için kullanılan bir araçtır.

## Unit Test:
Kodun küçük birimlerindeki işlevlerin doğruluğunu test etmek için kullanılan bir test türüdür.

## Integration Test:
Birkaç birim arasındaki etkileşimi test etmek için kullanılan bir test türüdür.

## End-to-End (E2E) Test:
Bir uygulamanın tüm fonksiyonlarının doğru çalıştığını kontrol etmek için kullanılan bir test türüdür.

## Continuous Integration (CI):
Kodun sürekli olarak test edilmesi ve birleştirilmesi için kullanılan bir süreçtir.

## Continuous Deployment (CD):
Kodun otomatik olarak üretim ortamına dağıtılması için kullanılan bir süreçtir.

## Agile:
Yazılım geliştirme sürecinde esnek bir yaklaşımı ifade eder ve müşteri geri bildirimleri doğrultusunda sık sık yeni özelliklerin eklenmesini ve geliştirilmesini sağlar.

## Scrum:
Agile yaklaşımın bir uygulama şeklidir ve bir ekip içinde çalışan üyelerin bir araya gelerek projeyi yönettiği bir süreçtir.

## Kanban:
Agile yaklaşıma dayalı bir proje yönetim yöntemidir ve projenin durumunu görsel olarak takip etmeyi sağlar.

## Waterfall:
Yazılım geliştirme sürecinde, bir adımın tamamlanmasının ardından diğer adıma geçilir ve geri dönüş yapılmaz.

## Spiral:
Yazılım geliştirme sürecinde, proje ilerledikçe yapılan analiz ve tasarım çalışmalarının tekrarlanması üzerine kurulu bir yaklaşımdır.

## MVP (Minimum Viable Product):
Bir ürünün en temel özelliklerini içeren ve müşteri geri bildirimleri doğrultusunda geliştirilen bir prototip aşamasıdır.

## Design Pattern:
Tekrar eden yazılım problemlerine karşı genel çözümler sunan yazılım tasarımı prensipleridir.

## SOLID:
Yazılım geliştirme prensiplerinin birleştirilmesiyle oluşan bir dizi ilkedir. S:
Tek Sorumluluk İlkesi (Single Responsibility Principle), O:
Açık/Kapalı İlkesi (Open/Closed Principle), L:
Liskov Yerine Geçme İlkesi (Liskov Substitution Principle), I:
Arayüz Ayrımı İlkesi (Interface Segregation Principle), D:
Bağımlılığı Tersine Çevirme İlkesi (Dependency Inversion Principle)

## REST (Representational State Transfer):
Web servislerinde kullanılan bir mimaridir ve HTTP protokolünü kullanarak kaynakların (resource) durumunu (state) yönetir.

## Template literals:
Bir dize içinde değişkenleri veya ifadeleri yerleştirmek için kullanılan yapıdır.

## Destructuring assignment:
Nesnelerin veya dizilerin özelliklerine veya elemanlarına tek seferde erişmek için kullanılan yapıdır.

## XML (Extensible Markup Language):
Veri aktarımı için kullanılan bir formattır ve metin tabanlı bir işaret dili kullanır.

## Type coercion:
JavaScript'te, bir veri türünün otomatik olarak başka bir veri türüne dönüştürülmesi anlamına gelir.

## Map:
JavaScript'te, her bir öğe ile bir değer çifti olan bir dizi veri yapısıdır.



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

JavaScript'te değişkenler, veri saklamak veya ileride kullanmak için değer atamak için kullanılır. 
JavaScript'te değişkenler dinamik olarak tip alır, yani bir değişkenin tipi, değişkenin değeri atanırken otomatik olarak belirlenir.

## var 
anahtar kelimesi, bir değişken tanımlamak için kullanılır. Ancak, "var" değişkenleri, blok kapsamı yerine işlev kapsamı veya global kapsam kullanır. Bu nedenle, "var" değişkenleri, aynı isimde birden fazla değişken tanımlanmasına izin verir ve bu da beklenmeyen sonuçlara yol açabilir.

```
var name = "John"; // var ile değişken tanımlama
```

## let 
anahtar kelimesi, "var" anahtar kelimesinin yerini almıştır. "let" değişkenleri blok kapsamını kullanır, bu nedenle aynı isimdeki bir değişkenin yeniden tanımlanması mümkün değildir. Ayrıca, "let" değişkenleri "undefined" olarak değer alır.

```
let age = 30; // let ile değişken tanımlama
```

## const 
anahtar kelimesi, "let" anahtar kelimesine benzerdir, ancak "let" ile farklı olarak, bir kez değer atandığında değiştirilemez. "const" değişkenleri, özellikle sabitler veya sabit değerler için kullanışlıdır.

```
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

JavaScript'de Rest Operator (...) , bir dizi parametreyi tek bir değişkene toplamak veya bir diziyi başka bir diziye eklemek gibi işlemler yapmak için kullanılır.

Rest operatorü, bir fonksiyona değişken sayıda argüman geçirirken kullanılabilir. Fonksiyon parametreleri, rest operatörü ile tanımlandığında, fonksiyona geçirilen tüm argümanlar bir dizi olarak toplanır.

Örneğin, aşağıdaki örnekte rest operatörü kullanılarak bir fonksiyona değişken sayıda parametre geçirilir:

const sebzeler = ['havuç', 'brokoli', ...meyveler];

console.log(sebzeler); // ['havuç', 'brokoli', 'elma', 'armut', 'muz']

Yukarıdaki örnekte, ...meyveler ifadesi, meyveler dizisinin elemanlarını tek tek ayırarak sebzeler dizisine ekler. Sonuç olarak, sebzeler dizisi, önce 'havuç' ve 'brokoli' olmak üzere iki sebze ve ardından meyveler dizisinin elemanları olan 'elma', 'armut' ve 'muz' şeklinde bir dizi haline gelir.

### Spread Oparator(...): 

JavaScript'de Spread Operator (...) bir dizi veya nesne ifadesinin öğelerini ayrıştırmak için kullanılır.

Dizi öğeleri için, Spread Operator, bir dizi ifadesinin tüm öğelerini ayırır ve bunları farklı bir dizi içine yerleştirir. Örneğin:

const numbers = [1, 2, 3];
const moreNumbers = [4, 5, 6];
const allNumbers = [...numbers, ...moreNumbers];

console.log(allNumbers); // [1, 2, 3, 4, 5, 6]
Burada, numbers ve moreNumbers dizileri, Spread Operator (...) kullanarak allNumbers dizisinde birleştirilir.

Nesne özellikleri için, Spread Operator, bir nesne ifadesindeki özellikleri başka bir nesneye kopyalamak için kullanılır. Örneğin:

const person = { name: "John", age: 30 };
const newPerson = { ...person, city: "Istanbul" };

console.log(newPerson); // { name: "John", age: 30, city: "Istanbul" }
Burada, person nesnesi, Spread Operator (...) kullanarak newPerson nesnesine kopyalanır ve yeni bir city özelliği eklenir.

### Mutable:
(Object, Array, Map, Set)

JavaScript'te bir değişkenin değerini değiştirebiliyorsanız, o değişken değiştirilebilirdir veya "mutable" olarak adlandırılır. Bu, örneğin bir dizi veya nesne gibi veri türleri için geçerlidir. Örneğin, bir diziye yeni bir öğe ekleyebilir veya bir nesnenin özelliklerini değiştirebilirsiniz ve bu değişiklikler doğrudan orijinal nesneyi etkiler.

Örneğin, aşağıdaki kodda bir diziyi değiştiriyoruz:

let myArray = [1, 2, 3];
myArray.push(4);
console.log(myArray); // [1, 2, 3, 4]

myArray dizisine push() yöntemi kullanarak 4 değerini ekledik. Bu, dizinin orijinal halini değiştirdi ve [1, 2, 3, 4] olarak güncellendi. Bu, dizi değiştirilebilir olduğu için mümkündür.

### Immutable: 
(String, Number, Boolean, null, undefined, Symbol)

JavaScript'te, bazı veri tipleri değiştirilemez (immutable) olarak adlandırılır, yani bir kez oluşturulduktan sonra değiştirilemezler. Bu özellik, programlama dilinin güvenli ve tutarlı kalmasını sağlar. Aşağıda, JavaScript'te değiştirilemez olan bazı veri tipleri listelenmiştir:

String: Bir kez oluşturulduktan sonra, bir dize (string) değiştirilemez. Bunun yerine, var olan bir dizenin bölümleri kopyalanarak yeni bir dize oluşturulabilir.
Örnek:
let str1 = "JavaScript";
let str2 = str1.slice(0,4) + " is fun!";
console.log(str2); // "Java is fun!"

Number: Bir sayı (number) değiştirilemezdir. Bunun yerine, var olan bir sayının matematiksel işlemler sonucunda elde edilen yeni bir sayı oluşturulabilir.
Örnek:

let num1 = 10;
let num2 = num1 + 5;
console.log(num2); // 15

Boolean: Bir boolean değiştirilemezdir. Bunun yerine, var olan bir boolean'ın değeri, mantıksal işlemler sonucunda elde edilen yeni bir boolean ile değiştirilebilir.
Örnek:
let bool1 = true;
let bool2 = !bool1;
console.log(bool2); // false
Symbol: Bir sembol (symbol) değiştirilemezdir. Her sembol benzersizdir ve bir kez oluşturulduktan sonra değiştirilemez.
Örnek:

let sym1 = Symbol("foo");
let sym2 = Symbol("foo");
console.log(sym1 === sym2); // false
Bu değiştirilemez veri tipleri, genellikle bir nesne içinde saklanarak kullanılır. Nesneler, özelliklerin ve değerlerin bir koleksiyonudur ve nesnelerin kendileri değiştirilebilir olsa da, nesne içindeki özellikler değiştirilemez olabilir.

### Mutate 

JavaScript'te "mutate" kelimesi, bir değişkenin değerinin değiştirilmesi anlamına gelir. Yani, bir değişkenin içeriği değiştirildiğinde, bu değişken "mutate" edilir. Bu, özellikle mutable veri tipleri (örneğin, dizi veya nesne) ile ilgili bir kavramdır, çünkü bu tür veri tiplerinin içeriği doğrudan değiştirilebilir. Immutable veri tipleri (örneğin, string veya number) ise değiştirilemezdir, bu nedenle değerleri değiştirilemez ve "mutate" edilemez.

### Render 

JavaScript'te "render", bir web sayfası veya uygulamanın görsel arayüzünün oluşturulması veya güncellenmesi sürecidir. Genellikle React, Vue veya Angular gibi JavaScript çerçevelerinde kullanılır.

Render işlemi, belirli bir duruma (state) ve/veya belirli bir veri kaynağına (props) dayanarak, bir bileşenin veya bir sayfanın HTML, CSS ve JavaScript kodunu oluşturur. Bu kod daha sonra web tarayıcısı tarafından yorumlanarak, kullanıcıların görüntüleyebileceği bir web sayfası olarak sunulur.

Render işlemi, kullanıcının etkileşimleriyle birlikte, sayfa veya uygulama içindeki bileşenlerin durumlarının değişmesiyle de tetiklenebilir. Bu durumda, render işlemi otomatik olarak yenilenir ve sayfa veya uygulama görüntüsü güncellenir.

### Re-render

React.js gibi bir kütüphane veya framework kullanılarak geliştirilen web uygulamalarında, bir bileşen (component) belirli bir durumda (state) olabilir. Bu durum, kullanıcının etkileşimi veya başka bir olay tarafından tetiklenebilir ve bileşenin yeniden render edilmesi gerekebilir. Bu yeniden render işlemi, bileşenin arayüzünün güncellenmesini sağlar ve yeni duruma göre yeniden oluşturulur. Bu sürece re-rendering denir.

Örneğin, bir sayfadaki bir bileşen, bir butona tıklama gibi bir kullanıcı etkileşimi sonrasında yeniden render edilebilir ve belirli bir duruma geçebilir. Bu durumda, bileşenin state'indeki değişikliklere göre, React bileşenleri arayüzünü yeniden oluşturur ve günceller.

### Immediate Re-Export

JavaScript'te "Immediate Re-Export", modüllerin yeniden kullanılabilirliğini artırmak için kullanılan bir modüller sistemidir.

Bu sistemde, bir modülün içeriği başka bir modül tarafından yeniden kullanılabilecek şekilde hızlıca yeniden ihraç edilebilir. Bu yöntem, gerekli fonksiyonları ve verileri içeren ayrı bir dosya oluşturmak yerine, daha küçük, yeniden kullanılabilir parçalar halinde kod yazmanızı sağlar.

Örneğin, bir "helperFunctions.js" dosyası oluşturabilirsiniz ve bu dosyadaki işlevleri başka bir modülde yeniden kullanmak isteyebilirsiniz. Bunun yerine, "helperFunctions.js" dosyasını yeniden ihraç edebilirsiniz ve diğer modülde doğrudan kullanabilirsiniz. Bu, kodunuzu daha modüler hale getirir ve tekrar kullanılabilirliğini artırır.


### Ternary Conditional Operators

Ternary conditional operators, bir koşulun doğru veya yanlış olduğunu kontrol eden bir ifade tipidir. Bu ifade, bir koşul ifadesi, bir doğru ifadesi ve bir yanlış ifadesi içerir.

Kısaca şu şekilde yazılabilir:

koşul ? doğru ifade : yanlış ifade;

Burada koşul ifadesi, kontrol edilecek koşulu ifade eder. Eğer bu koşul doğru ise, doğru ifade çalıştırılır, aksi takdirde yanlış ifade çalıştırılır.

Örneğin:
let sayi = 10;
let sonuc = sayi > 0 ? "Sayı pozitif" : "Sayı negatif veya sıfır";
console.log(sonuc); // Sayı pozitif
Bu örnekte, sayi > 0 koşulu kontrol edilir. Bu koşul doğru olduğu için, sonuc değişkenine "Sayı pozitif" atanır ve console.log ifadesi ile sonuç ekrana yazdırılır.

### Statement

JavaScript'te statement (ifade) bir işlemi tanımlayan ve uygulayan bir kod satırıdır. JavaScript programları birçok farklı statement kullanır.

Örneğin, atama işlemi yapan statement (ifade) şu şekildedir:

let x = 5;

Fonksiyon çağırma statement'i (ifade) ise şu şekildedir:

console.log("Hello, World!");

Bir döngü (loop) oluşturma statement'i (ifade) şu şekildedir:

for (let i = 0; i < 10; i++) {
  console.log(i);
}
Bu örneklerde gördüğümüz gibi, statement'ler farklı amaçlar için kullanılabilir ve JavaScript programlarında çok sık kullanılırlar.

### Expression

JavaScript'te expression (ifade), bir değerin üretildiği ve bir işlemi gerçekleştirdiği kod bloğudur. Bir expression, bir değişkene atanabilir, bir fonksiyonun argümanı olarak kullanılabilir veya bir kontrol yapısının içinde kullanılabilir.

Örnek olarak, aşağıdaki expressionlar mevcuttur:

3 + 4
"Hello " + "world"
true && false
(function() { return "Merhaba dünya"; })()
Bu ifadelerin her biri, bir değer döndüren bir işlemi gerçekleştirir. Örneğin, ilk ifade "3 + 4" toplama işlemi gerçekleştirir ve sonucu "7" döndürür. İkinci ifade, iki string ifadeyi birleştirir ve sonucu "Hello world" string'ini döndürür.

Bir değişkenin değerini tanımlamak, bir fonksiyonun geri dönüş değerini belirlemek, bir dizi veya nesne öğesinin değerini almak veya bir işlemi gerçekleştirmek gibi birçok durumda expressionlar kullanılabilir.

### Declaration

JavaScript'te bir deklarasyon, değişken, sabit veya fonksiyonun tanımlanmasıdır. Bu, ilgili değişkenin veya fonksiyonun kullanılabilmesi için bir isim ataması yapar.

Örneğin, bir değişkenin deklarasyonu aşağıdaki gibi olabilir:
let x;
Bu deklarasyon, x adında bir değişkenin tanımlandığını ve kullanılabileceğini belirtir. Ancak bu deklarasyon, değişkenin bir değer atanması veya başlatılması anlamına gelmez.

Bir fonksiyonun deklarasyonu ise aşağıdaki gibi olabilir:

function myFunction() {
  // fonksiyon kodları
}

Bu deklarasyon, myFunction adında bir fonksiyonun tanımlandığını ve kullanılabileceğini belirtir. Bu fonksiyon, çağrıldığında fonksiyon kodlarını çalıştıracaktır.

Kısacası, bir deklarasyon, bir değişkenin veya fonksiyonun tanımlandığını belirtir ve ilgili adın kullanılabilmesi için bir atama yapar.

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
