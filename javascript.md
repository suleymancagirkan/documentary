# JavaScript Özeti
Bu döküman, JavaScript'in temel yapı taşlarını ve önemli özelliklerini kapsamaktadır.


## 1. Değişken Tanımlama
- **`var`:** Fonksiyon kapsamlı, eski yöntem. Yeniden tanımlanabilir ve atanabilir.
- **`let`:** Blok kapsamlı, yeniden atanabilir ancak tanımlanamaz.
- **`const`:** Blok kapsamlı, yeniden atanamaz ve tanımlanamaz.

```javascript
var x = 10;
let y = 20;
const z = 30;
```

## 2. Veri Tipleri
### Primitive Tipler
- **`string`:** Metinsel veriler
- **`number`:** Sayısal veriler
- **`boolean`:** Mantıksal değerler (true/false)
- **`null`:** Bilinçli olarak boş değer
- **`undefined`:** Tanımlanmamış değer
- **`symbol`:** Benzersiz tanımlayıcılar
- **`bigint`:** Büyük tam sayılar

### Karmaşık Tipler
- **`Object`:** Nesneler (Array, Function, Date, RegExp, vb.)

## 3. Operatörler
- **Aritmetik:** `+`, `-`, `*`, `/`, `%`, `++`, `--`
- **Atama:** `=`, `+=`, `-=`, `*=`, `/=`
- **Karşılaştırma:** `==`, `===`, `!=`, `!==`, `>`, `<`, `>=`, `<=`
- **Mantıksal:** `&&`, `||`, `!`

## 4. Fonksiyonlar
### Fonksiyon Bildirimi
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}
```

### Anonim Fonksiyon (Function Expression)
```javascript
const greet = function(name) {
  return `Hello, ${name}!`;
};
```

### Arrow Fonksiyon
```javascript
const greet = (name) => `Hello, ${name}!`;
```

## 5. Kontrol Yapıları
### Koşullar
- **`if...else`**
- **`switch`**

Örnek:
```javascript
let age = 18;
if (age >= 18) {
    console.log("Yetişkin");
} else {
    console.log("Reşit değil");
}

let fruit = "elma";
switch (fruit) {
    case "elma":
        console.log("Bu bir elma");
        break;
    case "muz":
        console.log("Bu bir muz");
        break;
    default:
        console.log("Bilinmeyen meyve");
}
```

### Döngüler
- **`for`**
- **`while`**
- **`do...while`**
- **`for...in`**
- **`for...of`**

Örnek:
```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}

let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}

let arr = [1, 2, 3];
for (let item of arr) {
    console.log(item);
}
```

## 6. Diziler (Arrays)
- Temel işlemler: `push()`, `pop()`, `shift()`, `unshift()`
- İleri düzey işlemler: `map()`, `filter()`, `reduce()`, `forEach()`

Örnek:
```javascript
let fruits = ["elma", "muz", "kiraz"];
fruits.push("portakal");  // ["elma", "muz", "kiraz", "portakal"]
fruits.pop();  // ["elma", "muz", "kiraz"]

let numbers = [1, 2, 3, 4, 5];
let doubled = numbers.map(num => num * 2);  // [2, 4, 6, 8, 10]
let evens = numbers.filter(num => num % 2 === 0);  // [2, 4]
```

## 7. Nesneler (Objects)
- Özellik ekleme/çıkarma
- `Object.keys()`, `Object.values()`, `Object.entries()`

Örnek:
```javascript
let person = {
    name: "John",
    age: 30
};
person.job = "Developer";  // Özellik ekleme
delete person.age;  // Özellik çıkarma

console.log(Object.keys(person));  // ["name", "job"]
console.log(Object.values(person));  // ["John", "Developer"]
```

## 8. ES6+ Özellikleri
- **Destructuring:** Nesneleri ve dizileri parçalara ayırma
- **Spread ve Rest Operatörleri:** `...`
- **Template Literals:** Şablon dizgileri
- **Promises ve Async/Await:** Asenkron işlemler için

Örnek:
```javascript
// Destructuring
let [a, b] = [1, 2];
let {name, age} = {name: "John", age: 30};

// Spread Operatörü
let arr1 = [1, 2, 3];
let arr2 = [...arr1, 4, 5];  // [1, 2, 3, 4, 5]

// Template Literals
let name = "John";
console.log(`Merhaba, ${name}!`);

// Async/Await
async function fetchData() {
    let response = await fetch('https://api.example.com/data');
    let data = await response.json();
    console.log(data);
}
```

## 9. DOM Manipülasyonu
- Element seçme: `getElementById()`, `querySelector()`
- Olay dinleyicileri: `addEventListener()`
- İçerik değiştirme: `innerHTML`, `textContent`

Örnek:
```javascript
let button = document.getElementById('myButton');
let div = document.querySelector('.myDiv');

button.addEventListener('click', function() {
    div.innerHTML = '<p>Butona tıklandı!</p>';
});
```

## 10. Modüller
- **Export:** Fonksiyon veya değişkenleri dışa aktarma
- **Import:** Dışa aktarılan öğeleri içe aktarma

Örnek:
```javascript
// math.js
export function sum(a, b) {
    return a + b;
}

// main.js
import { sum } from './math.js';
console.log(sum(5, 3));  // 8
```

## 11. Hata Yönetimi
- **`try...catch`:** Hataları yakalama ve yönetme

Örnek:
```javascript
try {
    let result = someRiskyOperation();
    console.log(result);
} catch (error) {
    console.error("Bir hata oluştu:", error.message);
} finally {
    console.log("İşlem tamamlandı");
}
```

## 12. JSON İşlemleri
- **`JSON.stringify()`:** Nesneyi JSON dizgisine çevirme
- **`JSON.parse()`:** JSON dizgisini nesneye çevirme

Örnek:
```javascript
let person = {name: "John", age: 30};
let jsonString = JSON.stringify(person);
console.log(jsonString);  // '{"name":"John","age":30}'

let parsedPerson = JSON.parse(jsonString);
console.log(parsedPerson.name);  // "John"
```

@suleymancagirkan
