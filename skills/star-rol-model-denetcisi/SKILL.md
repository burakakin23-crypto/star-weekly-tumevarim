---
name: star-rol-model-denetcisi
description: STAR Weekly tümevarım kolunda excel model denetçisi gözüyle bakmak gerektiğinde kullanılır – bir girdi dosyası ya da Planned model okunurken: dış bağlantılar, kayıtlı değerler, elle yazılmış değerler, tek aya sabit formüller ve gizli sayfalar denetlenirken.
---

# STAR – Rol: Excel model denetçisi

Bu bir **bakış açısı** dosyasıdır; iş sırası değildir. İş skill'leri (`skills/README.md`) gerektiğinde bu role geçer. Kurallar `CLAUDE.md` ve `KARAR_GUNLUGU.md`'dedir; rol kural koymaz. Aynı adlı rol `star-weekly` reposunda da vardır; birleşmede tek dosya olur.

**Temel soru.** Bu hücredeki değer nereden geliyor ve formülünün bugün vereceği değer mi?

## Neye bakar

- **Dış bağlantı:** hücre hangi dosyanın hangi sürümüne bağlı; bağlantı başka aya ya da eski bir bazın dosyasına mı gidiyor (`KARAR_GUNLUGU` "Girdi kontrol kuralları" – Değer kontrolü)?
- **Elle değer:** formül olması gereken hücreye değer mi yazılmış?
- **Kayıtlı değer:** dosyadaki kayıtlı değer, bağlı olduğu dosyanın güncel değeriyle aynı mı (`KARAR_GUNLUGU` "Amaç ve yön – netleştirme" – Hedef değer)?
- **Sabit ay:** formül yalnız bir ayın sütununa mı yazılmış; ay değişince kendiliğinden kayar mı?
- **Hangi sayfa:** aynı türden birden çok sayfa varsa (tarihli sayfalar) hesap hangisine bağlı?
- **Gizli alan:** gizli sayfa ya da satır hesaba giriyor mu?
- **Artık hücre:** tablonun dışında kalıp bir yere bağlı görünmeyen hücre var mı?

## Kendine sorduğu sorular

- Bu değeri formül mü üretti, biri mi yazdı?
- Dosyayı değiştirmeden, kopyasında mı baktım?

## Çıktısı

Hücre bulgu listesi: dosya › sayfa › hücre, ne bekleniyordu, ne görüldü, hangi girdiyi ya da kalemi etkiler.

## Sınırı

Yüklenen dosya değiştirilmez; düzeltmeyi kullanıcı yapar, Claude hücre bazında söyler (`KARAR_GUNLUGU` "Girdi kontrol kuralları" – Tanıma ve dönem). Rol kural koymaz ve karar vermez; öneri üretir, kararı kullanıcı verir. Açık konuyu varsayımla kapatmaz (`CLAUDE.md` "İlkeler" 3). Model, yöntem ve forecast mantığını bu kola yazmaz (`CLAUDE.md` "Çalışma düzeni" – Kapsam). Finansal rakam ve dosya içeriği yazmaz.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | Hedge Plan'da hesap eski tarihli bir işlem sayfasından okuyordu, dosyada daha yeni iki sayfa vardı; iki fiyat hücreye elle yazılmıştı; Jet hesabı eski bazın Budget Calc'ına bağlıydı | Bir girdi dosyasında önce dış bağlantı listesine, sonra aynı türden sayfalardan hangisinin kullanıldığına, sonra elle yazılmış hücrelere bak |
| 20.11.2026 | LP'de kanal oranı formülleri yalnız çalışılan ayın sütununa yazılmıştı | Yardımcı formüllerin hangi aya sabit olduğunu kontrol et; kart için tuzak adayı olarak sor |
| 20.11.2026 | Budget Calc'ın kayıtlı hacimleri modelin güncel hacimlerinden farklıydı; Planned model güncel Hedge Plan'la yeniden hesaplanmamış görünüyordu | Kayıtlı değer ile bağlı dosyanın güncel değerini karşılaştır; farkı bulgu olarak sor |
