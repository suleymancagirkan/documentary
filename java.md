# Java Özeti
Bu döküman, Java programlama dilinin temel yapı taşlarını ve önemli özelliklerini kapsamaktadır.

## 1. Değişken Tanımlama
Java'da değişkenler, tip belirtilerek tanımlanır.

```java
int x = 10;
double y = 20.5;
String name = "John";
final int MAX_VALUE = 100; // sabit (değişmez) değişken
```

## 2. Veri Tipleri
Java'da iki ana veri tipi kategorisi vardır:

### Primitive Tipler
- `byte`, `short`, `int`, `long`: Tam sayılar
- `float`, `double`: Ondalıklı sayılar
- `boolean`: Mantıksal değer (true/false)
- `char`: Karakter

### Referans Tipleri
- `String`: Metin
- Diziler
- Sınıflar ve Arayüzler

```java
int number = 42;
String text = "Hello, Java!";
int[] numbers = {1, 2, 3, 4, 5};
```

## 3. Operatörler
- Aritmetik: `+`, `-`, `*`, `/`, `%`, `++`, `--`
- Karşılaştırma: `==`, `!=`, `>`, `<`, `>=`, `<=`
- Mantıksal: `&&`, `||`, `!`
- Atama: `=`, `+=`, `-=`, `*=`, `/=`

```java
int a = 5, b = 3;
boolean result = (a > b) && (a != b);
```

## 4. Kontrol Yapıları
### Koşullar
- `if`, `else if`, `else`
- `switch`

```java
int age = 18;
if (age >= 18) {
    System.out.println("Yetişkin");
} else {
    System.out.println("Reşit değil");
}

String fruit = "elma";
switch (fruit) {
    case "elma":
        System.out.println("Bu bir elma");
        break;
    case "muz":
        System.out.println("Bu bir muz");
        break;
    default:
        System.out.println("Bilinmeyen meyve");
}
```

### Döngüler
- `for`
- `while`
- `do-while`
- `for-each`

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}

int[] numbers = {1, 2, 3, 4, 5};
for (int num : numbers) {
    System.out.println(num);
}
```

## 5. Diziler (Arrays)
Java'da diziler, aynı türden elemanları saklayan veri yapılarıdır.

```java
int[] numbers = new int[5];
numbers[0] = 1;
numbers[1] = 2;

String[] fruits = {"elma", "muz", "kiraz"};
```

## 6. Sınıflar ve Nesneler
Java, nesne yönelimli bir programlama dilidir. Sınıflar, nesneler için şablonlardır.

```java
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void sayHello() {
        System.out.println("Merhaba, ben " + name);
    }
}

Person person = new Person("John", 30);
person.sayHello();
```

## 7. Metotlar
Metotlar, belirli bir işlevi yerine getiren kod bloklarıdır.

```java
public int sum(int a, int b) {
    return a + b;
}

int result = sum(5, 3);  // result = 8
```

## 8. Kalıtım (Inheritance)
Kalıtım, bir sınıfın başka bir sınıfın özelliklerini ve davranışlarını miras almasıdır.

```java
public class Animal {
    public void eat() {
        System.out.println("Hayvan yemek yiyor");
    }
}

public class Dog extends Animal {
    public void bark() {
        System.out.println("Köpek havlıyor");
    }
}

Dog dog = new Dog();
dog.eat();  // "Hayvan yemek yiyor"
dog.bark(); // "Köpek havlıyor"
```

## 9. Arayüzler (Interfaces)
Arayüzler, sınıfların uygulaması gereken metotları tanımlar.

```java
interface Runnable {
    void run();
}

class Car implements Runnable {
    public void run() {
        System.out.println("Araba çalışıyor");
    }
}
```

## 10. Exception Handling
Java'da hatalar try-catch blokları ile yönetilir.

```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Sıfıra bölme hatası: " + e.getMessage());
} finally {
    System.out.println("İşlem tamamlandı");
}
```

## 11. Collections Framework
Java Collections Framework, veri yapılarını yönetmek için kullanılır.

```java
import java.util.*;

List<String> list = new ArrayList<>();
list.add("elma");
list.add("muz");

Map<String, Integer> map = new HashMap<>();
map.put("elma", 1);
map.put("muz", 2);
```

## 12. Generics
Generics, tip güvenli koleksiyonlar ve sınıflar oluşturmak için kullanılır.

```java
public class Box<T> {
    private T content;

    public void set(T content) {
        this.content = content;
    }

    public T get() {
        return content;
    }
}

Box<Integer> intBox = new Box<>();
intBox.set(10);
int value = intBox.get();  // value = 10
```

@suleymancagirkan
