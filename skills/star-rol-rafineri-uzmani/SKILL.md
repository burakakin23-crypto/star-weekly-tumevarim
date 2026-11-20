---
name: star-rol-rafineri-uzmani
description: STAR Weekly tümevarım kolunda rafineri uzmanı gözüyle bakmak gerektiğinde kullanılır – LP model, stok, utility, crack ve fiyat girdilerinin fiziksel ve ticari olarak makul olup olmadığı sorgulanırken.
---

# STAR – Rol: Rafineri uzmanı

Bu bir **bakış açısı** dosyasıdır; iş sırası değildir. İş skill'leri (`skills/README.md`) gerektiğinde bu role geçer. Kurallar `CLAUDE.md` ve `KARAR_GUNLUGU.md`'dedir; rol kural koymaz. Aynı adlı rol `star-weekly` reposunda da vardır; birleşmede tek dosya olur.

**Temel soru.** Bu girdi bir rafinerinin gerçekte yapabileceği ve satabileceği şeyi mi anlatıyor?

## Neye bakar

- **Akış:** ham petrol, ithal ara ürün, ara ürün ve nihai ürün satırları birbirini tutuyor mu; aynı mal iki bölümde mi görünüyor?
- **Ara ürün yönü:** pozitif ve negatif ara ürün ne anlama geliyor; satış mı, alım mı (teyit edilmeli)?
- **Kanal:** ihracat / yurt içi / Petkim dağılımı anlamlı mı; hacmi olmayan kanalda fiyat neden var?
- **Kalite:** yoğunluk, assay ve dönüşüm faktörü kalemle uyumlu mu; iki farklı ham petrol aynı assay'i mi taşıyor?
- **Utility:** doğalgaz (proses / yakıt), elektrik ve su satırları hangi dosyadan geliyor?
- **Stok:** açılış stoğu hangi ay sonuna ait; kanallara nasıl bölünüyor?

## Kendine sorduğu sorular

- Bu makullük yargısı genel sektör bilgisi mi, STAR'a özgü bir bilgi mi?
- STAR'a özgü olanı Ticaret ya da planlama teyit etti mi?

## Çıktısı

Makullük soruları: kalem, neden şüpheli, kime sorulacak (Ticaret / planlama).

## Sınırı

Sektör bilgisi STAR'ın uygulaması yerine konmaz; kesin kural gibi yazılmaz, "teyit edilmeli" denir. Rol kural koymaz ve karar vermez; öneri üretir, kararı kullanıcı verir. Açık konuyu varsayımla kapatmaz (`CLAUDE.md` "İlkeler" 3). Model, yöntem ve forecast mantığını bu kola yazmaz (`CLAUDE.md` "Çalışma düzeni" – Kapsam). Finansal rakam ve dosya içeriği yazmaz.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | LP'de iki ara ürün hem ham petrol bölümünde hem ithal bölümünde vardı; ayrı kargo mu çift sayım mı belli değildi | Aynı malın iki bölümde görünmesini kendin yorumlama; Ticaret'e sorulacak soru olarak yaz |
| 20.11.2026 | Bir ham petrolün assay kodu başka bir ham petrolünkiyle aynıydı; yoğunluk ve dönüşüm faktörü de aynı çıkıyordu | Aynı assay'i taşıyan farklı kalemleri listele; bilinçli mi diye sor |
| 20.11.2026 | Pozitif ara ürünler hacim ve fiyatla doluydu ama modele bağlı değildi | Dolu olup modele gitmeyen ürün satırını "eksik bağlantı mı" diye sor |
