# ABM1101 — Deneme Sınavı 01

> **Sınav türü:** Özgün çalışma denemesi  
> **Geçmiş sınav mı?** Hayır. Bu sorular bu kütüphane için hazırlanmıştır.  
> **Önerilen süre:** 45 dakika  
> **Toplam:** 100 puan

Bu deneme; algoritma, değişkenler, işleçler, koşullar ve döngüler gibi temel konuları tekrar etmek için hazırlandı. İşlev ve dizilerle ilgili soruların ders kapsamında olup olmadığı öğretim elemanının güncel izlencesinden kontrol edilmelidir.

## A. Çoktan seçmeli sorular

Her soru 5 puandır. Yalnızca bir seçenek doğrudur.

### 1. Bir algoritmanın sonlu olması ne anlama gelir?

A) Her zaman aynı sonucu üretmesi  
B) Bir noktada tamamlanması  
C) Mutlaka C++ ile yazılması  
D) Hiç veri almaması

### 2. Aşağıdakilerden hangisi veri girişi, işlem ve çıktı sırasına uygundur?

A) Sonucu yazdır → sayıları oku → topla  
B) Sayıları oku → topla → sonucu yazdır  
C) Topla → sonucu yazdır → sayıları oku  
D) Sayıları yazdır → oku → bitir

### 3. Aşağıdaki kodun çıktısı nedir?

~~~cpp
int a = 7;
int b = 2;
std::cout << a / b;
~~~

A) 3.5  
B) 3  
C) 4  
D) 2

### 4. 17 % 5 işleminin sonucu nedir?

A) 2  
B) 3  
C) 5  
D) 12

### 5. Bir değişkenin 10 ile 20 arasında, sınırlar dâhil, olup olmadığını hangi ifade kontrol eder?

A) x >= 10 || x <= 20  
B) x > 10 && x < 20  
C) x >= 10 && x <= 20  
D) x == 10 && x == 20

### 6. Aşağıdaki kod kaç kez Merhaba yazar?

~~~cpp
for (int i = 0; i < 4; i++) {
    std::cout << "Merhaba";
}
~~~

A) 3  
B) 4  
C) 5  
D) Sonsuz

### 7. Aşağıdaki kodun çıktısı nedir?

~~~cpp
int x = 3;

if (x > 5) {
    std::cout << "A";
} else {
    std::cout << "B";
}
~~~

A) A  
B) B  
C) AB  
D) Çıktı yok

### 8. break komutunun döngü içindeki görevi nedir?

A) Döngüyü başa döndürmek  
B) O anki turu atlamak  
C) Döngüden çıkmak  
D) Değişkeni sıfırlamak

### 9. Beş elemanlı int dizi[5] dizisinin son geçerli indisi hangisidir?

A) 5  
B) 4  
C) 6  
D) 1

### 10. Bir işlevin return komutu ne yapar?

A) Her zaman ekrana yazı yazar  
B) İşlevden değer döndürür ve işlevi bitirir  
C) Döngüyü sonsuza kadar çalıştırır  
D) Değişkeni siler

## B. Kısa cevaplı sorular

Her soru 10 puandır.

### 11. Algoritma hazırlama

Kullanıcıdan üç sınav notu alıp ortalamasını hesaplayan algoritmayı sözde kodla yazın. Notların 0–100 aralığında olup olmadığını da kontrol edin.

### 12. Döngü izleme

Aşağıdaki kodun ekrana yazdığı değerleri ve toplamı bulun.

~~~cpp
int toplam = 0;

for (int i = 1; i <= 4; i++) {
    toplam += i;
    std::cout << toplam << " ";
}
~~~

### 13. Koşul yazma

Bir sayının hem 3'e hem 5'e tam bölünüp bölünmediğini kontrol eden C++ koşulunu yazın.

### 14. İşlev yazma

İki tam sayıdan büyük olanı döndüren buyukBul adlı işlevi yazın. Sayılar eşitse herhangi birini döndürebilir.

### 15. Dizi uygulaması

Beş tam sayılık bir dizinin elemanlarını dolaşıp toplamını hesaplayan kodu yazın.

## C. Cevap anahtarı

### Çoktan seçmeli

| Soru | Doğru cevap | Açıklama |
|---|---|---|
| 1 | B | Sonlu algoritma belirli sayıda adım sonra tamamlanır. |
| 2 | B | Veri önce alınır, işlem yapılır, sonuç gösterilir. |
| 3 | B | İki operand da tam sayı olduğu için bölümün ondalık kısmı atılır. |
| 4 | A | 17'nin 5'e bölümünden kalan 2'dir. |
| 5 | C | İki sınır da dâhil olduğu için >= ve <= birlikte kullanılır. |
| 6 | B | i, 0'dan 3'e kadar dört değer alır. |
| 7 | B | 3, 5'ten büyük değildir; else kolu çalışır. |
| 8 | C | break, içinde bulunulan döngüyü sonlandırır. |
| 9 | B | Dizi indisleri 0'dan başlar; son indis 4'tür. |
| 10 | B | return işlevi bitirir ve dönüş değerini çağırana verir. |

### 11. sorunun örnek çözümü

~~~text
BAŞLA
    not1, not2, not3 değerlerini oku
    EĞER notlardan biri 0'dan küçük veya 100'den büyükse
        "Geçersiz not" yaz
    DEĞİLSE
        ortalama = (not1 + not2 + not3) / 3
        ortalamayı yaz
    BİTİR
~~~

### 12. sorunun çözümü

- i = 1: toplam 1 olur.
- i = 2: toplam 3 olur.
- i = 3: toplam 6 olur.
- i = 4: toplam 10 olur.

Ekran çıktısı: 1 3 6 10

Son toplam: **10**

### 13. sorunun örnek çözümü

~~~cpp
if (sayi % 3 == 0 && sayi % 5 == 0) {
    std::cout << "Her ikisine de tam bolunur";
} else {
    std::cout << "Her ikisine birden tam bolunmez";
}
~~~

### 14. sorunun örnek çözümü

~~~cpp
int buyukBul(int a, int b) {
    if (a > b) {
        return a;
    }
    return b;
}
~~~

### 15. sorunun örnek çözümü

~~~cpp
int sayilar[5] = {4, 8, 2, 9, 7};
int toplam = 0;

for (int i = 0; i < 5; i++) {
    toplam += sayilar[i];
}

std::cout << toplam;
~~~

Beklenen sonuç: 30.

## Sınavdan sonra

Yanlış cevapları yalnızca ezberlemeyin. Hangi kavramın eksik olduğunu belirleyip ilgili ders notuna dönün. Özellikle tam sayı bölmesi, kalan işlemi, sınır kontrolleri ve döngülerin kaç kez çalıştığı üzerinde tekrar yapın.

**Son güncelleme:** 01.11.2026.
