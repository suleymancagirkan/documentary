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

### Döngüler
- **`for`**
- **`while`**
- **`do...while`**
- **`for...in`**
- **`for...of`**

## 6. Diziler (Arrays)
- Temel işlemler: `push()`, `pop()`, `shift()`, `unshift()`
- İleri düzey işlemler: `map()`, `filter()`, `reduce()`, `forEach()`

## 7. Nesneler (Objects)
- Özellik ekleme/çıkarma
- `Object.keys()`, `Object.values()`, `Object.entries()`

## 8. ES6+ Özellikleri
- **Destructuring:** Nesneleri ve dizileri parçalara ayırma
- **Spread ve Rest Operatörleri:** `...`
- **Template Literals:** Şablon dizgileri
- **Promises ve Async/Await:** Asenkron işlemler için

## 9. DOM Manipülasyonu
- Element seçme: `getElementById()`, `querySelector()`
- Olay dinleyicileri: `addEventListener()`
- İçerik değiştirme: `innerHTML`, `textContent`

## 10. Modüller
- **Export:** Fonksiyon veya değişkenleri dışa aktarma
- **Import:** Dışa aktarılan öğeleri içe aktarma

## 11. Hata Yönetimi
- **`try...catch`:** Hataları yakalama ve yönetme

## 12. JSON İşlemleri
- **`JSON.stringify()`:** Nesneyi JSON dizgisine çevirme
- **`JSON.parse()`:** JSON dizgisini nesneye çevirme
