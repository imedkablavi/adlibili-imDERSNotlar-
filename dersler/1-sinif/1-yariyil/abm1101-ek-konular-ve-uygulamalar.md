# ABM1101 — Ek Konular ve Uygulamalar

> **Önemli:** Bu dosya, bölümün 2020 müfredatında ABM105 için yayımladığı geçmiş konu listesinden yararlanılarak hazırlandı. Bu başlıkların tamamının 2025 ABM1101 dersinde işlendiği henüz doğrulanmadı. Güncel izlenceyle karşılaştırılana kadar bunları **ek çalışma** olarak değerlendirin.

İlk konu anlatımı ve temel alıştırmalar:
- [ABM1101 ana ders notu](./abm1101-algoritma-ve-programlama-i.md)
- [Temel alıştırmalar ve çözümleri](./abm1101-alistirmalar.md)
- [2020 tarihli geçmiş ders içeriği](./gecmis-ders-icerigi-2020.md)

## 1. İşlevler

İşlev, belirli bir işi yapan ve gerektiğinde programın farklı yerlerinden çağrılabilen kod bölümüdür. Aynı işlem birkaç kez kullanılacaksa kodu tekrar tekrar yazmak yerine işlev oluşturmak daha düzenli olur.

~~~cpp
#include <iostream>

int kareAl(int sayi) {
    return sayi * sayi;
}

int main() {
    int sonuc = kareAl(6);
    std::cout << "Sonuc: " << sonuc << '\n';
    return 0;
}
~~~

Burada kareAl işlevi bir tam sayı alır ve karesini döndürür. return komutu, işlevin ürettiği değeri çağrıldığı yere gönderir.

### Parametre ve geri dönüş değeri

~~~cpp
double ortalamaHesapla(double not1, double not2) {
    return (not1 + not2) / 2.0;
}
~~~

- Parametreler, işlevin dışarıdan aldığı bilgilerdir.
- Geri dönüş türü, işlevin hangi türde değer üreteceğini belirtir.
- void, değer döndürmeyen işlevlerde kullanılır.

## 2. Tek boyutlu diziler

Dizi, aynı türden birden fazla değeri tek isim altında tutar. Dizi elemanlarının sıra numarası sıfırdan başlar.

~~~cpp
#include <iostream>

int main() {
    int notlar[5] = {70, 85, 60, 90, 75};
    int toplam = 0;

    for (int i = 0; i < 5; i++) {
        toplam += notlar[i];
    }

    double ortalama = toplam / 5.0;
    std::cout << "Ortalama: " << ortalama << '\n';
    return 0;
}
~~~

notlar[0] ilk, notlar[4] son elemandır. Beş elemanlı bir dizide notlar[5] kullanmak dizi sınırının dışına çıkar.

## 3. Karakter ve metin işlemleri

Bir karakter değişkeni tek karakter saklar. Bir metin ise birden fazla karakterden oluşur.

~~~cpp
#include <iostream>
#include <string>

int main() {
    std::string metin;
    std::cout << "Bir kelime girin: ";
    std::cin >> metin;

    int sesliSayisi = 0;

    for (char karakter : metin) {
        if (karakter == 'a' || karakter == 'e' ||
            karakter == 'i' || karakter == 'o' ||
            karakter == 'u') {
            sesliSayisi++;
        }
    }

    std::cout << "Sesli harf sayisi: " << sesliSayisi << '\n';
    return 0;
}
~~~

Bu örnek yalnızca İngilizce alfabedeki küçük sesli harfleri sayar. Türkçedeki ı, ö, ü ve büyük harfler için ayrıca düzenleme gerekir. UTF-8 kodlamasında Türkçe harfler birden fazla baytla tutulabildiğinden char üzerinden yapılan basit karşılaştırmalar her zaman yeterli değildir.

## 4. İki boyutlu diziler ve matrisler

İki boyutlu dizi, satır ve sütunlardan oluşan tablo gibi düşünülebilir.

~~~cpp
#include <iostream>

int main() {
    int matris[2][3] = {
        {1, 2, 3},
        {4, 5, 6}
    };

    for (int satir = 0; satir < 2; satir++) {
        for (int sutun = 0; sutun < 3; sutun++) {
            std::cout << matris[satir][sutun] << " ";
        }
        std::cout << '\n';
    }

    return 0;
}
~~~

İlk indis satırı, ikinci indis sütunu gösterir. matris[1][2] değeri 6'dır.

## 5. Özyineleme

Özyineleme, bir işlevin kendi kendisini çağırmasıdır. Her özyinelemeli çözümde iki nokta bulunmalıdır:

1. Çağrıyı durduracak temel durum.
2. Problemi temel duruma yaklaştıran özyinelemeli çağrı.

~~~cpp
#include <iostream>

int faktoriyel(int n) {
    if (n <= 1) {
        return 1;
    }

    return n * faktoriyel(n - 1);
}

int main() {
    int sayi = 5;
    std::cout << faktoriyel(sayi) << '\n';
    return 0;
}
~~~

5! = 5 × 4 × 3 × 2 × 1 = 120.

Temel durum unutulursa işlev kendisini durmadan çağırabilir ve programın çağrı yığını tükenebilir. Negatif değerler için de bu örneğin ayrıca doğrulanması gerekir.

## 6. Arama yöntemleri

### Sıralı olmayan dizide doğrusal arama

Değerler baştan sona kontrol edilir. Aranan değer bulunursa konumu döndürülür.

~~~cpp
#include <iostream>

int dogrusalAra(const int dizi[], int uzunluk, int aranan) {
    for (int i = 0; i < uzunluk; i++) {
        if (dizi[i] == aranan) {
            return i;
        }
    }
    return -1;
}

int main() {
    int sayilar[] = {14, 8, 21, 5, 30};
    int konum = dogrusalAra(sayilar, 5, 21);

    std::cout << "Konum: " << konum << '\n';
    return 0;
}
~~~

21 sayısı dizinin 2 numaralı indisinde bulunur. Bulunamayan değer için -1 döndürülür.

## 7. Sıralama yöntemleri

Aşağıdaki örnek, komşu elemanları karşılaştırıp gerektiğinde yer değiştirerek diziyi küçükten büyüğe sıralar.

~~~cpp
#include <iostream>
#include <utility>

int main() {
    int sayilar[] = {7, 2, 9, 1, 5};
    const int uzunluk = 5;

    for (int i = 0; i < uzunluk - 1; i++) {
        for (int j = 0; j < uzunluk - 1 - i; j++) {
            if (sayilar[j] > sayilar[j + 1]) {
                std::swap(sayilar[j], sayilar[j + 1]);
            }
        }
    }

    for (int i = 0; i < uzunluk; i++) {
        std::cout << sayilar[i] << " ";
    }
    std::cout << '\n';

    return 0;
}
~~~

Beklenen sıra: 1 2 5 7 9.

Bu yöntem kabarcık sıralama olarak bilinir. Küçük örneklerde anlaşılması kolaydır; büyük veri kümelerinde daha verimli yöntemler tercih edilir.

## 8. Dosyaya yazma ve dosyadan okuma

Dosya işlemlerinde fstream başlık dosyası kullanılır.

~~~cpp
#include <fstream>
#include <iostream>
#include <string>

int main() {
    {
        std::ofstream cikti("notlar.txt");
        if (!cikti) {
            std::cerr << "Dosya olusturulamadi.\n";
            return 1;
        }

        cikti << "Algoritma ve Programlama\n";
        cikti << "ABM1101\n";
    }

    std::ifstream girdi("notlar.txt");
    if (!girdi) {
        std::cerr << "Dosya acilamadi.\n";
        return 1;
    }

    std::string satir;
    while (std::getline(girdi, satir)) {
        std::cout << satir << '\n';
    }

    return 0;
}
~~~

Dosya açma işleminin başarılı olup olmadığı kontrol edilmelidir. Dosya yolu geçerli değilse veya yazma izni yoksa işlem başarısız olabilir.

## 9. Bağlı listelere giriş

Bağlı listede her düğüm bir veri ve sonraki düğümün adresini tutar. Bu yapı, elemanların bellekte arka arkaya bulunmasını gerektirmez.

~~~cpp
struct Dugum {
    int veri;
    Dugum* sonraki;
};
~~~

Bu tanım yalnızca düğümün yapısını gösterir. Düğüm ekleme, silme ve belleği serbest bırakma işlemleri ayrıca öğrenilmelidir. Dinamik bellek kullanırken ayrılan alanı uygun zamanda serbest bırakmak gerekir.

## 10. Böl ve yönet yaklaşımı

Büyük bir problemi daha küçük alt problemlere ayırarak çözme yöntemidir. Sıralama ve arama algoritmalarının bazıları bu yaklaşımdan yararlanır. Önce küçük parçaların nasıl çözüleceği belirlenir, ardından sonuçlar birleştirilir.

## Çalışma soruları

Aşağıdaki görevler 2020 geçmiş ders içeriğinde geçen başlıklar için hazırlanmıştır. 2025 ABM1101 kapsamında olup olmadıkları güncel izlenceyle karşılaştırılmalıdır.

1. Beş elemanlı bir dizide en küçük ve en büyük değeri bulan işlev yazın.
2. Bir işlev kullanarak iki sayının en büyüğünü döndürün.
3. Bir metindeki belirli bir karakterin kaç kez geçtiğini bulun.
4. 3×3 matrisin ana köşegenindeki sayıların toplamını hesaplayın.
5. Özyineleme kullanarak Fibonacci dizisinin ilk N terimini üretin.
6. Bir dizideki sayıyı doğrusal aramayla bulun.
7. Bir diziyi kabarcık sıralama ile küçükten büyüğe sıralayın.
8. Bir metin dosyasına beş sayı yazıp dosyadan okuyarak toplamlarını bulun.
9. Tek yönlü bağlı listenin sonuna yeni düğüm ekleyen işlev hazırlayın.
10. Bağlı listedeki tüm düğümleri dolaşıp ekrana yazdırın.

## Kaynak ve kapsam notu

- [2020 ABM105 ders içeriği](./gecmis-ders-icerigi-2020.md)
- [2025 müfredatı](../../../2025-MUFREDATI.md)

Bu konuların 2025'te kesin olarak işlendiğine dair bölüm izlencesi bulunana kadar bu belge ek çalışma niteliğindedir.

**Son gözden geçirme:** 01.11.2026.
