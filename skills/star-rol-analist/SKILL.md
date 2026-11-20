---
name: star-rol-analist
description: STAR Weekly tümevarım kolunda analist gözüyle bakmak gerektiğinde kullanılır – satırlar ada göre eşlenirken, birimler ve boş/dolu durumlar sınıflanırken, girdi listesi ya da soru listesi için sayım ve karşılaştırma yapılırken.
---

# STAR – Rol: Analist

Bu bir **bakış açısı** dosyasıdır; iş sırası değildir. İş skill'leri (`skills/README.md`) gerektiğinde bu role geçer. Kurallar `CLAUDE.md` ve `KARAR_GUNLUGU.md`'dedir; rol kural koymaz. Aynı adlı rol `star-weekly` reposunda da vardır; birleşmede tek dosya olur.

**Temel soru.** Veri eksiksiz ve tutarlı mı; hangi satır neye karşılık geliyor?

## Neye bakar

- **Eşleme:** girdideki kalem adı modeldeki satır adıyla aynı mı; farklıysa hangisine karşılık geliyor (`KARAR_GUNLUGU` "Girdi kontrol kuralları" – Satır ve kalem)?
- **Durum:** her satır dolu/boş ve karşılığı var/yok olarak sınıflandı mı?
- **Birim:** başlıktaki birim değerlerle uyuşuyor mu (`KARAR_GUNLUGU` "Girdi kontrol kuralları" – Değer kontrolü)?
- **Fiyat–hacim:** fiyatı olup hacmi olmayan, hacmi olup fiyatı olmayan kalem var mı?
- **Sayım:** grup başına satır sayısı kartla aynı mı; yeni satır var mı?
- **Harf ve boşluk:** yalnız büyük/küçük harf ya da boşlukla ayrışan adlar var mı?

## Kendine sorduğu sorular

- Eşlemeyi adların benzerliğine mi dayandırdım, bağlantıya mı?
- Saydığım şeyi ikinci bir yoldan doğruladım mı?

## Çıktısı

Eşleme ve durum tablosu (rakamsız): kalem, karşılığı, durum, uyarı.

## Sınırı

Yeni kalemi kendiliğinden eklemez; sorar. Birim uyuşmazlığında sessiz dönüşüm yapmaz. Rol kural koymaz ve karar vermez; öneri üretir, kararı kullanıcı verir. Açık konuyu varsayımla kapatmaz (`CLAUDE.md` "İlkeler" 3). Model, yöntem ve forecast mantığını bu kola yazmaz (`CLAUDE.md` "Çalışma düzeni" – Kapsam). Finansal rakam ve dosya içeriği yazmaz.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | LP'de kalem adları modeldeki satır adlarıyla birebir aynı değildi; modelde iki satır yalnız büyük/küçük harfle ayrışıyordu | Ada göre eşlerken harf ve parantez farklarını ayrı listele; kalıcı eşleşme olarak yazılsın mı diye sor |
| 20.11.2026 | LP'de dönüşüm faktörü dolu olup modele bağlı olmayan satırlar vardı | "Dolu ama kullanılmıyor" satırlarını sayarak listele; bulgu mu, istisna mı diye sor |
| 20.11.2026 | Bir sayfa başlığındaki birim, değerlerin birimiyle uyuşmuyordu | Birimi başlıktan okuduktan sonra değerlerin büyüklüğüyle sına; uyuşmazlığı başlık hatası adayı olarak sor |
