# Proje Yürütme Planı

## Hedef

2025 ve sonrası müfredatındaki tüm dersler için öğrencinin tek bir yerden konu anlatımı, İngilizce kaynak, video, uygulama, alıştırma ve doğrulanmış sınav materyaline ulaşmasını sağlamak.

## Aşamalar

### Aşama 0 — Müfredat doğrulama
**Durum: Tamamlandı (ilk envanter).**

- [x] Resmî 2025 PDF bulundu ve incelendi.
- [x] Yeni önerilen ders kodları esas alındı.
- [x] Zorunlu ve seçmeli dersler ayrıldı.
- [x] Dördüncü sınıftaki iki iş yeri eğitimi yerleşimi not edildi.
- [ ] Ders listesi ve ders içerikleri sayfasıyla her dersin haftalık içeriğini tek tek eşleştir.

### Aşama 1 — Kaynak haritası
**Durum: İlk liste hazır; ders bazında derinleştirilecek.**

- [x] Üniversite kaynakları eklendi.
- [x] Temel matematik, programlama, ağ ve adli bilişim kaynakları eklendi.
- [ ] Her ders için 1–3 ana kaynak ve konu bazında yardımcı kaynak seç.
- [ ] Videoların dilini, seviyesini, güncelliğini ve erişim şartını doğrula.
- [ ] Kırık bağlantıları ve eski sürümleri takip et.

### Aşama 2 — Ders başına içerik oluşturma

Her ders için [Ders Notu Şablonu](templates/COURSE-TEMPLATE.md) kullanılacaktır.

1. Dersin amacı ve öğrenme çıktıları.
2. Haftalık/konu bazlı öğrenme sırası.
3. Türkçe açıklamalar ve İngilizce terim sözlüğü.
4. İngilizce kitap, dokümantasyon ve video bağlantıları.
5. Kod, komut, şekil veya örnek olaylar.
6. Uygulama/lab adımları ve güvenli test verileri.
7. Özgün alıştırmalar ve açıklamalı cevaplar.
8. Doğrulanmış geçmiş sınav bağlantıları.
9. Kaynakça ve son gözden geçirme tarihi.

### Aşama 3 — Öncelik sırasıyla pilot dersler

Önerilen ilk üretim sırası:

1. ABM1101 — Algoritma ve Programlama-I
2. ABM1102 — Algoritma ve Programlama-II
3. ABM2105 — Veri Yapıları
4. ABM2101 — Bilgisayar Ağları
5. ABM2103 — Bilişim Suçları ve Önleyici Tedbirler
6. ABM2104 — Web Uygulama Güvenliği
7. ABM2107 — Veritabanı Yönetim Sistemleri
8. ABM3101 — Elektronik Deliller
9. ABM3102 — Dosya Sistem Analizi
10. ABM3103 — Mobil Adli Bilişim
11. ABM3104 — Adli Bilişim İncelemeleri
12. ABM3108 — Veri Kurtarma Teknikleri

Bu sıra, dört yıllık kataloğun kapsamını değiştirmez; yalnızca ilk yayın için bağımlılıkları ve temel alanları öncelemektedir.

### Aşama 4 — Sınav arşivi

- Sınav türü, tarih/dönem ve ders kodu kaydedilir.
- Gerçek sınav olduğu doğrulanmayan dosya geçmiş sınav olarak sunulmaz.
- Kaynağı belirsiz paylaşımlar UNVERIFIED olarak işaretlenir ve doğrulanmadan yayımlanmaz.
- Özgün pratik sorular, geçmiş sınavlardan ayrı tutulur.
- Cevap anahtarı varsa çözüm, gerekçe ve kontrol eden kişi/tarih bilgisi eklenir.

Ayrıntı: [EXAM-ARCHIVE.md](EXAM-ARCHIVE.md).

### Aşama 5 — Uygulama laboratuvarları

Öncelikli laboratuvar konuları:

- C++ algoritma ve veri yapıları
- Wireshark ile ağ trafiği okuma
- SQL ve veritabanı uygulamaları
- Web güvenliği için kontrollü eğitim laboratuvarları
- Disk imajı, hash doğrulama ve write-blocker kavramları
- Autopsy / The Sleuth Kit ile örnek disk incelemesi
- Dosya sistemi ve veri kurtarma
- Mobil adli bilişim kavramları ve yasal test imajları

Her laboratuvar için hedef, gereken yazılım, güvenli veri seti, adımlar, beklenen çıktı ve sonuç kontrolü bulunmalıdır. Gerçek kişilere veya izinsiz sistemlere ait veriler kullanılmaz.

### Aşama 6 — Gözden geçirme ve sürekli bakım

- Ders içeriği en az bir teknik kaynakla çapraz kontrol edilir.
- Komutlar ve kod örnekleri mümkünse test edilir.
- Kaynak bağlantıları dönemsel kontrol edilir.
- Hukuk, güvenlik standartları ve yazılım dokümantasyonu değişikliklerinde ilgili notlar güncellenir.
- Öğrenci katkıları PR üzerinden incelenir.

## Ders yayın kontrol listesi

Bir ders PUBLISHED durumuna geçmeden önce:

- [ ] Müfredat kodu ve ders adı doğrulandı.
- [ ] Ders amacı ve kapsamı açık.
- [ ] Konu sıralaması ders içeriğiyle uyumlu.
- [ ] Türkçe açıklama özgün ve anlaşılır.
- [ ] İngilizce teknik terimler doğru kullanılmış.
- [ ] Kaynaklar bağlantı ve güncellik kontrolünden geçti.
- [ ] En az bir uygulama veya örnek mevcut.
- [ ] Alıştırmalar ve cevapları kontrol edildi.
- [ ] Geçmiş sınav etiketi kanıta dayanıyor.
- [ ] Telif ve gizlilik kontrolü yapıldı.
- [ ] Son gözden geçirme tarihi eklendi.

## İlerleme durumları

PLANNED → SOURCES-COLLECTED → DRAFT → REVIEW → PUBLISHED

Gerektiğinde NEEDS-UPDATE durumuna alınır.

## İlk kilometre taşları

| Milestone | Çıktı | Bitiş koşulu |
|---|---|---|
| M1 | Tam ders kataloğu | 4 yıl ve seçmeli havuzlar kataloglandı |
| M2 | Kaynak rehberi | Her çekirdek ders için kaynak araştırma kuyruğu |
| M3 | İlk pilot ders | Bir ders şablona göre baştan sona yazıldı |
| M4 | Sınav arşivi | Doğrulama ve etiket standardı uygulandı |
| M5 | İlk laboratuvar | Tekrarlanabilir ve güvenli uygulama yayımlandı |
| M6 | Bakım süreci | Katkı ve güncelleme akışı tanımlandı |

**Plan tarihi:** 2026-11-01.
