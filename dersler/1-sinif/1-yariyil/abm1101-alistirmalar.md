# ABM1101 — Alıştırmalar ve Çözümleri

Bu sorular çalışma amacıyla hazırlanmıştır. **Hiçbiri geçmiş sınav sorusu olarak sunulmamaktadır.** Önce kendiniz çözmeye çalışın. Bir soruda zorlanırsanız doğrudan koda geçmek yerine girdileri, işlemleri ve beklenen çıktıyı kâğıt üzerinde belirleyin.

## A. Algoritma kurma

### Soru 1 — İki sayının toplamı

Kullanıcıdan iki tam sayı alın. Toplamlarını hesaplayıp ekrana yazdıracak algoritmayı yazın.

**Çözüm:**

~~~text
BAŞLA
    a değerini oku
    b değerini oku
    toplam = a + b
    toplamı yaz
BİTİR
~~~

### Soru 2 — Tek mi, çift mi?

Girilen bir tam sayının tek mi çift mi olduğunu belirleyin.

**Çözüm:**

~~~text
BAŞLA
    sayıyı oku
    EĞER sayı mod 2 = 0 İSE
        "Çift" yaz
    DEĞİLSE
        "Tek" yaz
BİTİR
~~~

Kontrol: 14 için kalan 0, 17 için kalan 1 olmalıdır.

### Soru 3 — Üç sayıdan en büyüğü

Kullanıcıdan üç sayı alın. En büyük olanı bulun.

**Çözümün mantığı:** İlk sayıyı en büyük kabul edin. İkinci sayı bundan büyükse en büyük değerini güncelleyin. Aynı işlemi üçüncü sayı için de yapın.

~~~cpp
#include <iostream>

int main() {
    int a, b, c;
    std::cin >> a >> b >> c;

    int enBuyuk = a;

    if (b > enBuyuk) {
        enBuyuk = b;
    }

    if (c > enBuyuk) {
        enBuyuk = c;
    }

    std::cout << "En buyuk: " << enBuyuk << '\n';
    return 0;
}
~~~

Örnek girdi: 12 28 19  
Beklenen çıktı: 28

## B. Koşul ve işlem alıştırmaları

### Soru 4 — Not kontrolü

0 ile 100 arasında bir not girilsin. 60 ve üzeri için “Başarılı”, altı için “Başarısız” yazdırılsın. Aralık dışındaki değerler reddedilsin.

**Çözüm:**

~~~cpp
#include <iostream>

int main() {
    int notDegeri;
    std::cin >> notDegeri;

    if (notDegeri < 0 || notDegeri > 100) {
        std::cout << "Gecersiz not\n";
    } else if (notDegeri >= 60) {
        std::cout << "Basarili\n";
    } else {
        std::cout << "Basarisiz\n";
    }

    return 0;
}
~~~

### Soru 5 — Basit hesap makinesi

İki sayı ve bir işlem karakteri (+, -, *, /) alın. Seçilen işlemin sonucunu gösterin. Sıfıra bölme durumunu kontrol edin.

**Çözüm:**

~~~cpp
#include <iostream>

int main() {
    double a, b;
    char islem;

    std::cout << "Iki sayi ve islem girin: ";
    std::cin >> a >> islem >> b;

    switch (islem) {
        case '+':
            std::cout << a + b;
            break;
        case '-':
            std::cout << a - b;
            break;
        case '*':
            std::cout << a * b;
            break;
        case '/':
            if (b == 0) {
                std::cout << "Sifira bolme yapilamaz";
            } else {
                std::cout << a / b;
            }
            break;
        default:
            std::cout << "Gecersiz islem";
    }

    std::cout << '\n';
    return 0;
}
~~~

Örnek girdi: 12 / 3  
Beklenen çıktı: 4

### Soru 6 — Artık yıl kontrolü

Bir yılın artık yıl olup olmadığını bulun. 400'e tam bölünen yıllar artık yıldır. 100'e tam bölünen ancak 400'e bölünmeyen yıllar artık yıl değildir. Diğer yıllarda 4'e bölünme kontrol edilir.

**Çözüm:**

~~~cpp
#include <iostream>

int main() {
    int yil;
    std::cin >> yil;

    bool artikYil =
        (yil % 400 == 0) ||
        (yil % 4 == 0 && yil % 100 != 0);

    if (artikYil) {
        std::cout << "Artik yil\n";
    } else {
        std::cout << "Artik yil degil\n";
    }

    return 0;
}
~~~

Kontrol örnekleri: 2000 artık yıldır, 1900 değildir, 2024 artık yıldır.

## C. Döngü alıştırmaları

### Soru 7 — 1'den N'ye kadar toplam

Pozitif bir N sayısı alın. 1'den N'ye kadar olan sayıların toplamını bulun.

**Çözüm:**

~~~cpp
#include <iostream>

int main() {
    int n;
    std::cin >> n;

    if (n < 1) {
        std::cout << "Pozitif bir sayi girin\n";
        return 1;
    }

    int toplam = 0;

    for (int i = 1; i <= n; i++) {
        toplam += i;
    }

    std::cout << "Toplam: " << toplam << '\n';
    return 0;
}
~~~

N = 5 için işlem 1 + 2 + 3 + 4 + 5 şeklindedir. Beklenen sonuç 15'tir.

### Soru 8 — Çarpım tablosu

1 ile 10 arasındaki sayıların çarpım tablosunu ekrana yazdırın.

**Çözüm:**

~~~cpp
#include <iostream>

int main() {
    for (int i = 1; i <= 10; i++) {
        for (int j = 1; j <= 10; j++) {
            std::cout << i << " x " << j
                      << " = " << i * j << '\n';
        }
    }

    return 0;
}
~~~

Dış döngü hangi sayının tablosunun yazılacağını, iç döngü ise o tablodaki çarpanları belirler.

### Soru 9 — Sayının basamakları toplamı

Pozitif bir tam sayının rakamları toplamını bulun.

**Çözüm:**

~~~cpp
#include <iostream>

int main() {
    int sayi;
    std::cin >> sayi;

    if (sayi < 0) {
        std::cout << "Negatif olmayan bir sayi girin\n";
        return 1;
    }

    int toplam = 0;

    while (sayi > 0) {
        toplam += sayi % 10;
        sayi /= 10;
    }

    std::cout << "Basamaklar toplami: " << toplam << '\n';
    return 0;
}
~~~

Örnek: 527 sayısı için 5 + 2 + 7 = 14. Bu çözüm 0 girildiğinde de doğru biçimde 0 verir.

### Soru 10 — Asal sayı kontrolü

Girilen sayının asal olup olmadığını belirleyin.

**Çözüm:**

~~~cpp
#include <iostream>

int main() {
    int n;
    std::cin >> n;

    bool asal = (n >= 2);

    for (int i = 2; i * i <= n && asal; i++) {
        if (n % i == 0) {
            asal = false;
        }
    }

    if (asal) {
        std::cout << "Asal sayi\n";
    } else {
        std::cout << "Asal degil\n";
    }

    return 0;
}
~~~

1 asal değildir. 2 asaldır. 9 asal değildir çünkü 3'e tam bölünür.

## D. Biraz daha düşünmeyi gerektiren sorular

### Soru 11 — Pozitif, negatif ve sıfır sayısı

Kullanıcıdan 10 tam sayı alın. Kaç tanesinin pozitif, kaç tanesinin negatif ve kaç tanesinin sıfır olduğunu bulun.

**Çözüm:**

~~~cpp
#include <iostream>

int main() {
    int pozitif = 0;
    int negatif = 0;
    int sifir = 0;

    for (int i = 0; i < 10; i++) {
        int sayi;
        std::cin >> sayi;

        if (sayi > 0) {
            pozitif++;
        } else if (sayi < 0) {
            negatif++;
        } else {
            sifir++;
        }
    }

    std::cout << "Pozitif: " << pozitif << '\n';
    std::cout << "Negatif: " << negatif << '\n';
    std::cout << "Sifir: " << sifir << '\n';

    return 0;
}
~~~

### Soru 12 — Ortalama ve en büyük not

Öğrenciden 5 not alın. Notların ortalamasını ve en büyük notu bulun. Her notun 0–100 aralığında olmasını sağlayın.

**Çözüm:**

~~~cpp
#include <iostream>

int main() {
    double toplam = 0;
    int enBuyuk = -1;

    for (int i = 1; i <= 5; i++) {
        int notDegeri;
        std::cout << i << ". not: ";
        std::cin >> notDegeri;

        if (notDegeri < 0 || notDegeri > 100) {
            std::cout << "Gecersiz not.\n";
            return 1;
        }

        toplam += notDegeri;

        if (notDegeri > enBuyuk) {
            enBuyuk = notDegeri;
        }
    }

    std::cout << "Ortalama: " << toplam / 5 << '\n';
    std::cout << "En buyuk not: " << enBuyuk << '\n';

    return 0;
}
~~~

## E. Kendi başına çöz

Aşağıdaki soruların çözümü bilerek eklenmedi. Önce algoritmasını hazırlayın, ardından C++ kodunu yazıp farklı girdilerle sınayın.

1. Girilen sayının pozitif, negatif veya sıfır olduğunu belirleyin.
2. 1 ile 100 arasındaki 3'e ve 5'e tam bölünen sayıları yazdırın.
3. Girilen sayının faktöriyelini hesaplayın. Negatif girişleri reddedin.
4. Girilen sayının tersini bulun. Örneğin 482 için 284.
5. İki sayı arasındaki bütün çift sayıları yazdırın.
6. Kullanıcı 0 girene kadar sayı almaya devam edin ve girilen sayıların toplamını hesaplayın.
7. Bir ürünün fiyatı ve indirim oranını alıp indirimli fiyatını hesaplayın. Geçersiz oranları reddedin.
8. Kullanıcıdan alınan bir karakterin sesli harf olup olmadığını kontrol edin. Büyük ve küçük harfleri düşünün.

## Çalışmanı nasıl kontrol edeceksin?

Her programı en az şu durumlarda dene:

- Normal bir girdi.
- Sıfır gibi özel bir girdi.
- İzin verilen en küçük değer.
- İzin verilen en büyük değer.
- Geçersiz bir girdi.

Bir sorunun yalnızca bir örnekle doğru sonuç vermesi, bütün durumlarda doğru çalıştığını göstermez.

**Son güncelleme:** 01.11.2026.
