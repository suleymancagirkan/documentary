# PHP Özeti
Bu döküman, PHP programlama dilinin temel yapı taşlarını ve önemli özelliklerini kısaca özetlemektedir.

## 1. Değişken Tanımlama
PHP'de değişkenler $ işareti ile başlar ve dinamik olarak tiplendirilir.

```php
$x = 10;
$y = "Merhaba";
$z = true;
```

## 2. Veri Tipleri
- Skaler Tipler: `int`, `float`, `string`, `bool`
- Bileşik Tipler: `array`, `object`
- Özel Tipler: `resource`, `NULL`

```php
$number = 42;
$text = "PHP";
$fruits = array("elma", "muz", "kiraz");
```

## 3. Operatörler
Aritmetik: `+`, `-`, `*`, `/`, `%`
Karşılaştırma: `==`, `===`, `!=`, `<>`, `!==`, `<`, `>`, `<=`, `>=`
Mantıksal: `&&`, `||`, `!`

```php
$result = ($a > $b) && ($a != $c);
```

## 4. Kontrol Yapıları
```php
if ($age >= 18) {
    echo "Yetişkin";
} else {
    echo "Reşit değil";
}

for ($i = 0; $i < 5; $i++) {
    echo $i;
}

foreach ($fruits as $fruit) {
    echo $fruit;
}
```

## 5. Fonksiyonlar
```php
function greet($name) {
    return "Merhaba, $name!";
}

echo greet("John");  // Çıktı: Merhaba, John!
```

## 6. Diziler
```php
$colors = array("kırmızı", "yeşil", "mavi");
$person = array(
    "ad" => "John",
    "yaş" => 30,
    "meslek" => "geliştirici"
);
```

## 7. Sınıflar ve Nesneler
```php
class Person {
    public $name;
    public function __construct($name) {
        $this->name = $name;
    }
    public function greet() {
        echo "Merhaba, benim adım " . $this->name;
    }
}

$john = new Person("John");
$john->greet();  // Çıktı: Merhaba, benim adım John
```

## 8. Hata Yönetimi
```php
try {
    // Riskli kod
    $result = 10 / 0;
} catch (Exception $e) {
    echo "Hata: " . $e->getMessage();
} finally {
    echo "İşlem tamamlandı";
}
```

## 9. Dosya İşlemleri
```php
$file = fopen("test.txt", "r");
$content = fread($file, filesize("test.txt"));
fclose($file);
```

## 10. Veritabanı İşlemleri (MySQL örneği)
```php
$conn = mysqli_connect("localhost", "username", "password", "database");
$result = mysqli_query($conn, "SELECT * FROM users");
while ($row = mysqli_fetch_assoc($result)) {
    echo $row['name'];
}
mysqli_close($conn);
```

## 11. Süper Globaller
- `$_GET`: GET metodu ile gönderilen verileri içerir
- `$_POST`: POST metodu ile gönderilen verileri içerir
- `$_SESSION`: Oturum verilerini içerir
- `$_COOKIE`: Çerez verilerini içerir
- `$_SERVER`: Sunucu ve çalışma ortamı bilgilerini içerir

## 12. Namespace ve Use
```php
namespace MyApp\Utilities;

use MyApp\Models\User;

class Helper {
    // ...
}
```

@suleymancagirkan
