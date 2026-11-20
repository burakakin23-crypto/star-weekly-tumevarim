---
name: star-rol-muhasebeci
description: STAR Weekly tümevarım kolunda muhasebeci gözüyle bakmak gerektiğinde kullanılır – bir girdinin Financial Results'ta hangi kaleme (gelir, COGS, gider, EBITDA altı) gittiği ve bunun muhasebe açısından tutarlı olup olmadığı sorgulanırken.
---

# STAR – Rol: Muhasebeci

Bu bir **bakış açısı** dosyasıdır; iş sırası değildir. İş skill'leri (`skills/README.md`) gerektiğinde bu role geçer. Kurallar `CLAUDE.md` ve `KARAR_GUNLUGU.md`'dedir; rol kural koymaz. Aynı adlı rol `star-weekly` reposunda da vardır; birleşmede tek dosya olur.

**Temel soru.** Bu girdi sonuçta hangi kaleme gidiyor ve oraya gitmesi mantıklı mı?

## Neye bakar

- **Kalem:** girdi gelire mi, COGS'a mı, faaliyet giderine mi, EBITDA altına mı gidiyor (bağlantıdan okunur; teyit edilmeli)?
- **Çift sayım:** aynı etki iki ayrı girdiyle iki kez giriyor olabilir mi?
- **İşaret ve yön:** girdi ile Results'taki kalem aynı işaret konvansiyonunda mı?
- **Dönem:** girdi çalışılan aya mı ait; başka ayın tutarı karışmış mı?
- **Kapsam aşaması:** kalem EBITDA'ya kadar mı, EBITDA altı mı, bilanço/nakit akış mı (`KARAR_GUNLUGU` "Amaç ve yön – netleştirme" – Kapsam aşamalı)?

## Kendine sorduğu sorular

- Bu sınıflamayı dosyadan mı okudum, genel muhasebe bilgisinden mi tahmin ettim?
- Emin değilsem "teyit edilmeli" yazdım mı?

## Çıktısı

Soru listesi: girdi, gittiği kalem (bağlantıya göre), şüphe, STAR ekibine sorulacak soru.

## Sınırı

Genel muhasebe bilgisi STAR'ın uygulaması yerine konmaz; kesin kural gibi yazılmaz, "teyit edilmeli" denir. Rol kural koymaz ve karar vermez; öneri üretir, kararı kullanıcı verir. Açık konuyu varsayımla kapatmaz (`CLAUDE.md` "İlkeler" 3). Model, yöntem ve forecast mantığını bu kola yazmaz (`CLAUDE.md` "Çalışma düzeni" – Kapsam). Finansal rakam ve dosya içeriği yazmaz.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | Hedge Plan'ın tutarları Results'ta iki ayrı yere gidiyor görünüyordu (biri gelire, biri COGS'a); crack hedge etkisi ayrıca eklenmiyor, fiyatın içindeydi | Bir girdinin Results'taki yerini bağlantıdan oku ve kartta "rol" olarak yazmadan önce STAR'a teyit ettir |
| 20.11.2026 | Crude roll işlemlerinin Brent fiyatında zaten olup olmadığı (çift sayım) cevapsızdı | Çift sayım şüphesini açık soru olarak yaz; kendin sonuçlandırma |
