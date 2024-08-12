# Python Özeti
Bu doküman, Python'un temel yapı taşlarını ve önemli özelliklerini kapsamaktadır.

## 1. Değişken Tanımlama
Python'da değişken tanımlamak için özel bir anahtar kelime kullanılmaz. Değişkenler dinamik olarak tiplendirilir.

```python
x = 10
y = "Merhaba"
z = 3.14
```

## 2. Veri Tipleri
### Temel Tipler
- **`int`:** Tam sayılar
- **`float`:** Ondalıklı sayılar
- **`str`:** Metinsel veriler
- **`bool`:** Mantıksal değerler (True/False)
- **`None`:** Boş değer

### Karmaşık Tipler
- **`list`:** Sıralı, değiştirilebilir koleksiyonlar
- **`tuple`:** Sıralı, değiştirilemez koleksiyonlar
- **`dict`:** Anahtar-değer çiftleri
- **`set`:** Benzersiz elemanlardan oluşan koleksiyonlar

## 3. Operatörler
- **Aritmetik:** `+`, `-`, `*`, `/`, `//`, `%`, `**`
- **Atama:** `=`, `+=`, `-=`, `*=`, `/=`
- **Karşılaştırma:** `==`, `!=`, `>`, `<`, `>=`, `<=`
- **Mantıksal:** `and`, `or`, `not`

## 4. Fonksiyonlar
### Fonksiyon Tanımlama
```python
def greet(name):
    return f"Merhaba, {name}!"
```

### Lambda Fonksiyonlar
```python
greet = lambda name: f"Merhaba, {name}!"
```

## 5. Kontrol Yapıları
### Koşullar
- **`if...elif...else`**

Örnek:
```python
age = 18
if age >= 18:
    print("Yetişkin")
elif age >= 13:
    print("Genç")
else:
    print("Çocuk")
```

### Döngüler
- **`for`**
- **`while`**

Örnek:
```python
for i in range(5):
    print(i)

fruits = ["elma", "muz", "kiraz"]
for fruit in fruits:
    print(fruit)

i = 0
while i < 5:
    print(i)
    i += 1
```

## 6. Listeler (Lists)
- Temel işlemler: `append()`, `pop()`, `insert()`, `remove()`
- İleri düzey işlemler: List comprehensions

Örnek:
```python
fruits = ["elma", "muz", "kiraz"]
fruits.append("portakal")  # ["elma", "muz", "kiraz", "portakal"]
fruits.pop()  # ["elma", "muz", "kiraz"]

numbers = [1, 2, 3, 4, 5]
squared = [num ** 2 for num in numbers]  # [1, 4, 9, 16, 25]
```

## 7. Sözlükler (Dictionaries)
- Anahtar-değer çiftleri
- `keys()`, `values()`, `items()` metodları

Örnek:
```python
person = {
    "name": "John",
    "age": 30
}
person["job"] = "Developer"  # Yeni anahtar-değer ekleme
del person["age"]  # Anahtar-değer silme

print(person.keys())  # dict_keys(['name', 'job'])
print(person.values())  # dict_values(['John', 'Developer'])
```

## 8. Hata Yönetimi
- **`try...except...finally`:** Hataları yakalama ve yönetme

Örnek:
```python
try:
    result = some_risky_operation()
    print(result)
except Exception as e:
    print(f"Bir hata oluştu: {e}")
finally:
    print("İşlem tamamlandı")
```

## 9. Dosya İşlemleri
- Dosya açma, okuma, yazma ve kapatma

Örnek:
```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)

with open("example.txt", "w") as file:
    file.write("Merhaba, Dünya!")
```

## 10. Modüller ve Paketler
- **import:** Modülleri içe aktarma
- **from...import:** Belirli fonksiyonları içe aktarma

Örnek:
```python
import math
print(math.pi)

from datetime import datetime
print(datetime.now())
```

## 11. Nesne Yönelimli Programlama (OOP)
- Sınıf tanımlama ve nesne oluşturma

Örnek:
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def greet(self):
        return f"Merhaba, ben {self.name}!"

john = Person("John", 30)
print(john.greet())  # "Merhaba, ben John!"
```

## 12. Dekoratörler
- Fonksiyonları değiştirmek veya geliştirmek için kullanılır

Örnek:
```python
def uppercase_decorator(func):
    def wrapper():
        result = func()
        return result.upper()
    return wrapper

@uppercase_decorator
def greet():
    return "merhaba, dünya!"

print(greet())  # "MERHABA, DÜNYA!"
```

## 13. Generators
- Bellek verimliliği için kullanılır

Örnek:
```python
def countdown(n):
    while n > 0:
        yield n
        n -= 1

for number in countdown(5):
    print(number)  # 5, 4, 3, 2, 1
```

## 14. List, Dict, ve Set Comprehensions
- Kısa ve öz koleksiyon oluşturma yöntemleri

Örnek:
```python
numbers = [1, 2, 3, 4, 5]
squares = [x**2 for x in numbers]  # [1, 4, 9, 16, 25]

evens = {x for x in numbers if x % 2 == 0}  # {2, 4}

square_dict = {x: x**2 for x in numbers}  # {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

## 15. Asenkron Programlama
- `async` ve `await` anahtar kelimeleri ile asenkron işlemler

Örnek:
```python
import asyncio

async def main():
    print('Merhaba')
    await asyncio.sleep(1)
    print('Dünya')

asyncio.run(main())
```

@suleymancagirkan
