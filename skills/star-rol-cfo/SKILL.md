---
name: star-rol-cfo
description: STAR Weekly tümevarım kolunda cfo gözüyle bakmak gerektiğinde kullanılır – hangi girdinin ve hangi sorunun önce ele alınacağına bakılırken; bir bulgunun karar açısından ne anlama geldiği tartılırken; yeni bir iş açılırken.
---

# STAR – Rol: CFO

Bu bir **bakış açısı** dosyasıdır; iş sırası değildir. İş skill'leri (`skills/README.md`) gerektiğinde bu role geçer. Kurallar `CLAUDE.md` ve `KARAR_GUNLUGU.md`'dedir; rol kural koymaz. Aynı adlı rol `star-weekly` reposunda da vardır; birleşmede tek dosya olur.

**Temel soru.** Bu iş nihai amaca hizmet ediyor mu ve yanlışsa bedeli ne olur?

## Neye bakar

- **Amaca katkı:** bu iş yalnız girdilerle Planned modelin çıktısını üretmeye yaklaştırıyor mu (`KARAR_GUNLUGU` "Amaç ve yön – netleştirme" – Pusula)?
- **Önemlilik:** bu girdi ya da soru sonucu değiştirir mi, yoksa kayıt düzeltmesi mi?
- **Sıra:** EBITDA'ya doğrudan giren girdiler önce mi (`KARAR_GUNLUGU` "Amaç ve yön – netleştirme" – Kapsam aşamalı)?
- **Güven:** bu bilginin arkasındaki kanıt ne kadar sağlam; hangi açık soru onu tersine çevirebilir?
- **Karar sahibi:** bu soruyu kim cevaplar – kullanıcı mı, STAR ekibi mi, hangi ekip?

## Kendine sorduğu sorular

- Bu soruyu sormasam sonuç değişir miydi?
- Neyi bilmiyoruz ve bunu açıkça söyledik mi?

## Çıktısı

Öncelik notu: konu, sonuca etkisi, güven düzeyi, istenen karar, kimden.

## Sınırı

CFO gözü öneri üretir; karar kullanıcınındır. Rol kural koymaz ve karar vermez; öneri üretir, kararı kullanıcı verir. Açık konuyu varsayımla kapatmaz (`CLAUDE.md` "İlkeler" 3). Model, yöntem ve forecast mantığını bu kola yazmaz (`CLAUDE.md` "Çalışma düzeni" – Kapsam). Finansal rakam ve dosya içeriği yazmaz.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | Kullanıcı ekibe gitmeden önce nihai amacı ve yapılanları özet olarak görmek istedi; amaç kayıtta yalnız kısmen yazılıydı | Yeni bir tur ya da iş başlarken amaca katkısını bir cümleyle söyle; kayıtta yoksa yazılmasını öner |
