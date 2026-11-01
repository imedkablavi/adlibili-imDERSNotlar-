# ABM1101 — Algoritma ve Programlama-I

| Bilgi | Açıklama |
|---|---|
| Sınıf / yarıyıl | 1. sınıf / 1. yarıyıl |
| Ders türü | Zorunlu |
| 2025 müfredatındaki kod | ABM1101 |
| Önceki kod | ABM1001 |
| Teori / uygulama | 3 saat / 2 saat |
| Yerel kredi | 4 |
| AKTS | 5 |
| İçerik durumu | İlk ders notu hazırlandı; izlence eşleştirmesi bekliyor |
| Son gözden geçirme | 01.11.2026 |

> **Kapsam notu:** Üniversitenin 2025 müfredat belgesi ders kodunu, saatini ve kredisini doğruluyor. Bölümün bu ders için yayımladığı güncel haftalık konu çizelgesine şu an erişilemedi. Bu yüzden aşağıdaki konu sırası, birinci sınıf düzeyinde hazırlanmış bir çalışma planıdır; üniversitenin resmî haftalık izlencesi olarak gösterilmemelidir. **2025 müfredat PDF'si programlama dilini belirtmiyor.** Bu ilk sürümde C++ örnekleri kullanıldı; bölümün güncel izlencesi veya öğretim elemanının duyurusu başka bir dil gösterirse örnekler ona göre değiştirilecek.

## 1. Bu ders neden var?

Bir program yazmaya başlamadan önce çözülmesi gereken problemi anlamak gerekir. Bilgisayar, ne istediğimizi kendiliğinden tahmin etmez. Ona hangi verileri alacağını, bu veriler üzerinde hangi işlemleri yapacağını ve sonucu nasıl göstereceğini adım adım anlatırız.

Bu derste iki beceri birlikte gelişir:

- Bir problemi küçük ve anlaşılır adımlara ayırmak.
- Hazırlanan çözümü bir programlama diliyle bilgisayara yaptırmak.

Örneğin üç sınav notunun ortalamasını hesaplamak basit görünebilir. Yine de programın önce üç notu alması, toplamı hesaplaması, üçe bölmesi ve sonucu göstermesi gerekir. Notlardan biri yanlış girilmişse ne olacağı da düşünülmelidir. Programlama, bu kararları önceden verebilme işidir.

## 2. Dersin sonunda kazanılması beklenen beceriler

Aşağıdaki maddeler çalışma hedefidir. Resmî öğrenme çıktıları yayımlandığında onlarla karşılaştırılacaktır.

1. Verilen bir problemi girdi, işlem ve çıktı olarak ayırmak.
2. Çözüm için sonlu ve anlaşılır bir algoritma hazırlamak.
3. Basit akış şemalarını okuyup çizebilmek.
4. Değişken, veri türü, sabit ve operatör kavramlarını kullanmak.
5. Klavyeden veri alıp ekrana sonuç yazdırmak.
6. Koşul ve döngülerle programın akışını yönetmek.
7. Yazılan programı farklı örneklerle sınamak.
8. Sözdizimi, çalışma zamanı ve mantık hatalarını birbirinden ayırmak.

## 3. Çalışmaya başlamadan önce

### Gerekli araçlar

C++ örneklerini çalıştırmak için bir metin düzenleyici ve C++ derleyicisi gerekir. Hangi geliştirme ortamının kullanılacağı öğretim elemanının yönlendirmesine göre seçilmelidir.

**Linux üzerinde derleyici kontrolü:**

~~~bash
g++ --version
~~~

Derleyici kurulu değilse dağıtımın paket yöneticisinden GNU C++ derleyicisi kurulabilir. Değişmez sistem kullanan dağıtımlarda kurulum yöntemi farklı olabilir; sistemin kendi yönergesi izlenmelidir.

**Windows üzerinde:** Visual Studio Community veya MinGW-w64 gibi bir C++ derleyicisi kullanılabilir. Yalnızca kod düzenleyicisini kurmak yeterli değildir; kodu derleyecek araç da bulunmalıdır.

Bir dosyayı program olarak çalıştırmak için önce derlemek gerekir. Örneğin dosyanın adı main.cpp ise:

~~~bash
g++ -std=c++17 -Wall -Wextra -pedantic main.cpp -o program
./program
~~~

Buradaki C++17 seçimi örnek çalışma ortamı içindir. Dersin öğretim elemanı farklı bir standart veya derleyici isterse onun talimatı esas alınır.

## 4. Algoritma nedir?

Algoritma, bir problemi çözmek için belirli bir sırayla uygulanan sonlu adımlar bütünüdür. Bir tarifte malzemelerin hangi sırayla kullanılacağı yazdığı gibi, algoritmada da bilgisayara yaptırılacak işlemler sıralanır.

İyi hazırlanmış bir algoritmanın temel özellikleri şunlardır:

- **Açıklık:** Her adım ne yapılacağını belli etmelidir.
- **Sonluluk:** İşlemler sonsuza kadar sürmemeli, bir noktada bitmelidir.
- **Doğruluk:** Geçerli girdiler için beklenen sonucu üretmelidir.
- **Girdi ve çıktı:** Kullanacağı veriler ve üreteceği sonuç belli olmalıdır.
- **Uygulanabilirlik:** Adımlar gerçekten yapılabilir işlemlerden oluşmalıdır.

### Örnek: İki sayının toplamı

Problem: Kullanıcıdan iki tam sayı alınacak ve toplamları gösterilecek.

Önce girdileri belirleyelim:

- Birinci sayı.
- İkinci sayı.

İşlem:

- İki sayı toplanır.

Çıktı:

- Toplam değeri.

Algoritma:

1. Başla.
2. Birinci sayıyı oku.
3. İkinci sayıyı oku.
4. İki sayıyı topla.
5. Toplamı ekrana yaz.
6. Bitir.

Bu adımlar koddan bağımsızdır. Aynı çözüm C++, Python veya başka bir dille uygulanabilir.

## 5. Sözde kod ve akış şeması

### Sözde kod

Sözde kod, algoritmayı programlama dilinin bütün yazım kurallarına bağlı kalmadan anlatmanın yoludur. Henüz C++ sözdizimiyle uğraşmadan çözümün mantığını kontrol etmeyi sağlar.

İki sayıyı toplama örneği:

~~~text
BAŞLA
    sayi1 değerini oku
    sayi2 değerini oku
    toplam = sayi1 + sayi2
    toplam değerini yaz
BİTİR
~~~

Sözde kod için tek bir zorunlu yazım biçimi yoktur. Önemli olan, adımların herkes tarafından aynı şekilde anlaşılmasıdır.

### Akış şemasında kullanılan şekiller

| Şekil | Görevi |
|---|---|
| Oval | Başlangıç veya bitiş |
| Dikdörtgen | İşlem |
| Paralelkenar | Veri girişi veya çıktı |
| Eşkenar dörtgen | Koşul ve karar |
| Ok | İşlem sırasının yönü |

Akış şeması çizerken okların nereye gittiği açık olmalıdır. Karar kutusundan çıkan yollar Evet/Hayır ya da Doğru/Yanlış şeklinde adlandırılabilir.

### Örnek: Sayının tek mi çift mi olduğunu bulma

~~~text
BAŞLA
    sayıyı oku
    EĞER sayı mod 2 = 0 İSE
        "Çift" yaz
    DEĞİLSE
        "Tek" yaz
    BİTİR
~~~

Buradaki mod işlemi bölme işleminden kalanı verir. 8 sayısının 2'ye bölümünden kalan 0 olduğu için sayı çifttir.

## 6. İlk C++ programı

~~~cpp
#include <iostream>

int main() {
    std::cout << "Merhaba Dunya!" << '\n';
    return 0;
}
~~~

Kodun parçaları:

- **iostream:** Ekrana yazma ve klavyeden veri alma işlemlerinde kullanılan başlık dosyasıdır.
- **main:** Program çalıştığında ilk girilen ana işlevdir.
- **std::cout:** Ekrana çıktı gönderir.
- **\n:** Bir alt satıra geçer.
- **return 0:** Programın normal biçimde tamamlandığını bildirir.

C++ dilinde komutların sonunda çoğunlukla noktalı virgül kullanılır. Açılan süslü parantezlerin de doğru yerde kapatılması gerekir.

## 7. Değişkenler ve veri türleri

Değişken, program çalışırken değer saklamak için ayrılan isimlendirilmiş alandır. Örneğin öğrencinin yaşı, sınav notu veya dosya sayısı bir değişkende tutulabilir.

~~~cpp
#include <iostream>
#include <string>

int main() {
    int dosyaSayisi = 12;
    double ortalamaBoyut = 24.5;
    char durumKodu = 'A';
    bool incelemeTamamlandi = false;
    std::string dosyaAdi = "ornek.txt";

    std::cout << "Dosya sayisi: " << dosyaSayisi << '\n';
    std::cout << "Ortalama boyut: " << ortalamaBoyut << '\n';
    std::cout << "Durum: " << durumKodu << '\n';
    std::cout << "Tamamlandi mi? " << incelemeTamamlandi << '\n';
    std::cout << "Dosya adi: " << dosyaAdi << '\n';

    return 0;
}
~~~

Sık kullanılan veri türleri:

| Tür | Ne tutar? | Örnek |
|---|---|---|
| int | Tam sayı | 25 |
| double | Ondalıklı sayı | 18.75 |
| float | Daha düşük duyarlıklı ondalıklı sayı | 3.5f |
| char | Tek karakter | 'A' |
| bool | Doğru veya yanlış | true |
| string | Metin | "rapor.txt" |

Değişken adları ne sakladığını anlatmalıdır. sayi, notOrtalamasi veya dosyaSayisi gibi adlar, x1 ve a2 gibi gelişigüzel adlardan daha kolay okunur.

### Sabitler

Program boyunca değişmemesi gereken değerler sabit olarak tanımlanabilir:

~~~cpp
const int MAKSIMUM_NOT = 100;
~~~

Bir sınav notunun üst sınırı gibi değişmemesi gereken değerler için sabit kullanmak, yanlışlıkla değer değiştirilmesini önler.

## 8. Klavyeden veri alma ve ekrana yazma

C++ dilinde klavyeden veri almak için std::cin, ekrana yazmak için std::cout kullanılır.

~~~cpp
#include <iostream>

int main() {
    int yas;

    std::cout << "Yasinizi girin: ";
    std::cin >> yas;

    std::cout << "Girdiginiz yas: " << yas << '\n';
    return 0;
}
~~~

Birden fazla değer aynı satırda alınabilir:

~~~cpp
int a, b;
std::cin >> a >> b;
~~~

Kullanıcı 12 18 girerse ilk değer a değişkenine, ikinci değer b değişkenine aktarılır.

Burada önemli bir ayrıntı var: std::cin >> metin şeklinde kullanıldığında boşluğa gelince okumayı durdurur. Boşluk içeren tam bir satır okunacaksa std::getline kullanılır. Bu konu daha sonra örneklerle genişletilebilir.

## 9. Operatörler

Operatörler, değerler üzerinde işlem yapmamızı sağlar.

### Aritmetik operatörler

| Operatör | İşlem | Örnek |
|---|---|---|
| + | Toplama | 8 + 2 = 10 |
| - | Çıkarma | 8 - 2 = 6 |
| * | Çarpma | 8 * 2 = 16 |
| / | Bölme | 8 / 2 = 4 |
| % | Bölümden kalan | 9 % 2 = 1 |

**Dikkat:** İki tam sayı birbirine bölündüğünde sonuç da tam sayı türündeyse ondalık kısım kaybolur.

~~~cpp
int sonuc1 = 5 / 2;          // 2
double sonuc2 = 5.0 / 2.0;  // 2.5
~~~

### Karşılaştırma operatörleri

- == : Eşit mi?
- != : Eşit değil mi?
- > : Büyük mü?
- < : Küçük mü?
- >= : Büyük veya eşit mi?
- <= : Küçük veya eşit mi?

Tek eşittir işareti atama yapar; çift eşittir işareti karşılaştırma yapar. Bu ikisi sık karıştırılır.

### Mantıksal operatörler

| Operatör | Anlamı |
|---|---|
| && | Ve |
| || | Veya |
| ! | Değil |

Örneğin bir notun 0 ile 100 arasında olup olmadığını kontrol etmek için:

~~~cpp
if (notDegeri >= 0 && notDegeri <= 100) {
    std::cout << "Gecerli not";
}
~~~

## 10. Koşul yapıları

Programın her durumda aynı işlemi yapması gerekmez. Bazen bir koşula göre farklı yola gitmelidir.

~~~cpp
#include <iostream>

int main() {
    int notDegeri;

    std::cout << "Notu girin: ";
    std::cin >> notDegeri;

    if (notDegeri < 0 || notDegeri > 100) {
        std::cout << "Gecersiz not";
    } else if (notDegeri >= 60) {
        std::cout << "Basarili";
    } else {
        std::cout << "Basarisiz";
    }

    return 0;
}
~~~

Program önce notun geçerli olup olmadığını kontrol eder. Geçersiz bir değer varsa başarı değerlendirmesine geçmez.

Koşullarda sınır değerleri düşünmek gerekir. Örneğin başarı sınırı 60 ise 59, 60 ve 61 değerleri ayrı ayrı denenmelidir.

### switch yapısı

Bir değişkenin belirli değerlerine göre seçim yapılacaksa switch kullanılabilir:

~~~cpp
int secim = 2;

switch (secim) {
    case 1:
        std::cout << "Ekle";
        break;
    case 2:
        std::cout << "Listele";
        break;
    case 3:
        std::cout << "Cikis";
        break;
    default:
        std::cout << "Gecersiz secim";
}
~~~

break yazılmazsa program sonraki case bölümüne geçebilir. Bu nedenle her case'in ne zaman biteceği bilinmelidir.

## 11. Döngüler

Döngüler, belirli işlemleri tekrar tekrar yazmak yerine bir koşula bağlı olarak çalıştırmamızı sağlar.

### for döngüsü

Tekrar sayısı belli olduğunda kullanışlıdır.

~~~cpp
for (int i = 1; i <= 5; i++) {
    std::cout << i << '\n';
}
~~~

Bu örnekte ekrana 1, 2, 3, 4 ve 5 yazılır.

### while döngüsü

Tekrar sayısı önceden belli olmayabilir. Döngü, koşul doğru olduğu sürece çalışır.

~~~cpp
int sayi = 1;

while (sayi <= 5) {
    std::cout << sayi << '\n';
    sayi++;
}
~~~

Döngü içinde sayi değerini artırmasaydık koşul sürekli doğru kalır ve program bitmeyen bir döngüye girebilirdi.

### do-while döngüsü

Bu yapıda koşul sona geldiğinde kontrol edilir. Bu nedenle döngü gövdesi en az bir kez çalışır.

~~~cpp
int secim;

do {
    std::cout << "1-Devam  0-Cikis: ";
    std::cin >> secim;
} while (secim != 0);
~~~

### break ve continue

- break, içinde bulunulan döngüyü sona erdirir.
- continue, döngünün o turundaki kalan işlemleri atlayıp sonraki tura geçer.

Bu komutları kullanmadan önce döngünün normal koşulla bitip bitmeyeceği düşünülmelidir.

## 12. İç içe döngüler

Bir döngünün içinde başka bir döngü bulunabilir. Örneğin çarpım tablosu hazırlanırken dış döngü satırları, iç döngü sütunları oluşturabilir.

~~~cpp
#include <iostream>

int main() {
    for (int i = 1; i <= 5; i++) {
        for (int j = 1; j <= 5; j++) {
            std::cout << i * j << "\t";
        }
        std::cout << '\n';
    }

    return 0;
}
~~~

İç içe döngülerde toplam tekrar sayısı artar. İki döngünün de 5 kez çalıştığı bu örnekte içteki işlem toplam 25 kez yürütülür.

## 13. Konuların çalışma sırası

Aşağıdaki sıra, öğrencinin konuları birbirinin üzerine kurarak öğrenmesi için hazırlanmıştır. Bölümün resmî haftalık planı değildir.

| Hafta | Çalışma konusu | Uygulama |
|---|---|---|
| 1 | Problem çözmeye giriş, algoritma | İki sayının toplamını adımlara ayırma |
| 2 | Sözde kod ve akış şeması | Tek-çift kontrolü |
| 3 | C++ programının yapısı, derleme | İlk programı çalıştırma |
| 4 | Değişkenler ve veri türleri | Not ve ortalama hesaplama |
| 5 | Girdi, çıktı ve operatörler | Basit hesap makinesi |
| 6 | Koşul yapıları | Üç sayıdan en büyüğünü bulma |
| 7 | Mantıksal ifadeler ve switch | Menü hazırlama |
| 8 | İlk konuların tekrarı | Ara sınav çalışması |
| 9 | for ve while döngüleri | 1'den N'ye kadar toplam |
| 10 | do-while ve iç içe döngüler | Çarpım tablosu |
| 11 | Döngülerle problem çözme | Asal sayı ve basamak hesabı |
| 12 | Fonksiyonlara giriş | Tekrarlanan işlemi ayrı işlevde yazma |
| 13 | Dizilere giriş (ders izlencesinde bulunuyorsa) | Not listesini işleme |
| 14 | Genel tekrar ve küçük uygulama | Menü tabanlı not hesaplama |

12. ve 13. haftalardaki fonksiyon ve dizi konuları, dersin güncel izlencesinde yer aldığı doğrulandıktan sonra kesin plana alınacaktır. Dersin öğretim elemanı bu konuları ABM1102'ye bırakmışsa burada yalnızca ön bilgi olarak tutulur.

## 14. Sık karşılaşılan hatalar

| Hata | Neden | Ne yapılmalı? |
|---|---|---|
| Noktalı virgül unutmak | C++ komut sonunu bekler | Hata mesajındaki satırı kontrol et |
| = ile == işaretlerini karıştırmak | Atama ve karşılaştırma farklıdır | Koşulun içinde çift eşittir kullan |
| Değişkene değer vermeden kullanmak | Değişkenin başlangıç değeri belirsiz olabilir | Tanımlarken ilk değerini belirle |
| 5 / 2 sonucunu 2.5 beklemek | Tam sayı bölmesi yapılır | İşleme ondalıklı tür kat |
| Döngü değişkenini artırmamak | Koşul değişmez ve döngü bitmeyebilir | Döngünün ilerleme adımını kontrol et |
| Sadece tek örnekle denemek | Sınır durumları gözden kaçar | Küçük, büyük, sıfır ve geçersiz değerleri dene |

## 15. Bir programı nasıl sınamalı?

Programın çalışması tek başına doğru olduğu anlamına gelmez. Beklenen sonucu verdiğinden emin olmak için farklı girdiler denenmelidir.

Örneğin 0 ile 100 arasında not alan bir program için:

| Girdi | Beklenen durum |
|---|---|
| 75 | Geçerli not |
| 60 | Başarı sınırında |
| 59 | Geçerli ama başarısız |
| 0 | Geçerli alt sınır |
| 100 | Geçerli üst sınır |
| -1 | Geçersiz |
| 101 | Geçersiz |

Hataları üç grupta düşünmek yararlı olur:

- **Yazım hatası:** Kodun dil kurallarına uymaması; derleyici genellikle hata bildirir.
- **Çalışma zamanı hatası:** Program çalışırken ortaya çıkan sorun.
- **Mantık hatası:** Program çalışır ama yanlış sonuç üretir.

Özellikle mantık hatasını bulmak zor olabilir. Çünkü derleyici, programın yanlış hesap yaptığını her zaman anlayamaz.

## 16. Küçük uygulama: Not ortalaması hesaplama

~~~cpp
#include <iostream>

int main() {
    double vize, finalNotu;

    std::cout << "Vize notunu girin: ";
    std::cin >> vize;

    std::cout << "Final notunu girin: ";
    std::cin >> finalNotu;

    if (vize < 0 || vize > 100 ||
        finalNotu < 0 || finalNotu > 100) {
        std::cout << "Notlar 0 ile 100 arasinda olmali.\n";
        return 1;
    }

    double ortalama = vize * 0.40 + finalNotu * 0.60;

    std::cout << "Ortalama: " << ortalama << '\n';

    if (ortalama >= 60) {
        std::cout << "Basarili\n";
    } else {
        std::cout << "Basarisiz\n";
    }

    return 0;
}
~~~

Bu örnekte vize %40, final %60 alınmıştır. Bu oran yalnızca kodlama örneğidir; üniversitenin veya dersin gerçek değerlendirme oranı olduğu anlamına gelmez. Gerçek oranlar dersin öğretim elemanı tarafından açıklanan ölçme-değerlendirme bilgisine göre değiştirilmelidir.

## 17. Alıştırmalar

Alıştırmalar ve çözümleri ayrı dosyada tutulur:

[ABM1101 — Alıştırmalar ve Çözümleri](./abm1101-alistirmalar.md)

Önce soruları çözmeye çalışın; ardından çözüm bölümünü kontrol edin. Kodları yalnızca okumak yerine kendiniz yazıp çalıştırın.

## 18. Ders kaynakları

Önce Türkçe kaynaklarla çalışın:

1. **Fahri Vatansever — Algoritma Geliştirme ve Programlamaya Giriş, 16. Baskı (2025).** Algoritma, akış şeması ve farklı dillerde çözümlü örnekler içerir. [Yayınevi sayfası](https://www.seckin.com.tr/kitap/algoritma-gelistirme-ve-programlamaya-giris-akis-diyagramlariyla-birlikte-6-ayri-programlama-dilinde-c-c-c-java-matlab-ve-python-cozulmus-problemler-fahri-vatansever-s-p-836218431).
2. **BTK Akademi — C++ ile Programlamaya Giriş.** Türkçe video eğitimi. Kayıt/giriş gerekebilir. Kurs daha ileri konulara da geçtiği için bu derste yalnızca temel programlama konularına karşılık gelen bölümlerden yararlanılmalı. [Eğitim sayfası](https://www.btkakademi.gov.tr/portal/tr/course/20172).
3. **Kavax — C++ Dersleri: 1 Saatte Tamamen C++ Öğren.** İlk program, değişkenler, girdi, matematiksel işlemler, koşullar ve döngülere hızlı bir giriş sağlar. Videoda değişkenler 25:14, kullanıcıdan veri alma 35:57, koşullar 52:28 ve döngüler 01:04:29 civarında başlar. Tek başına dersin tamamı için yeterli değildir. [Videoyu izle](https://www.youtube.com/watch?v=Hz6Sug8fbH4).

**Üniversite kaynakları:**

- [2025 Adli Bilişim Mühendisliği müfredatı](https://abmtf.firat.edu.tr/subdomain_files/abmtf.firat.edu.tr/files/2511/2025%20Ders%20M%C3%BCfredat%C4%B1%C4%B1.pdf)
- [Bölümün ders içerikleri sayfası](https://abmtf.firat.edu.tr/page/3315)
- [Bölümün ders listesi](https://abmtf.firat.edu.tr/page/3310)

## 19. Henüz doğrulanması gerekenler

- Bölümün ABM1101 için yayımladığı güncel haftalık izlence.
- İlk dönemde kullanılan programlama dili ve sürümü.
- Öğretim elemanının önerdiği ders kitabı ve ders notları.
- Laboratuvarda kullanılan geliştirme ortamı.
- Vize, final ve uygulama değerlendirme oranları.
- Bu derse ait gerçek geçmiş sınav soruları.

Bu bilgiler gelmeden tahminle resmî konu listesi veya sınav arşivi oluşturulmayacaktır.

## Son güncelleme

- 01.11.2026 — Dersin resmî müfredat bilgileri eklendi; ilk Türkçe konu anlatımı, çalışma sırası, örnek kod ve kaynaklar hazırlandı.
- Sonraki adım — Bölümün haftalık ders içeriğiyle konu sırasını karşılaştırıp eksikleri düzeltmek.
