---
name: star-rol-denetci
description: STAR Weekly tümevarım kolunda denetçi gözüyle bakmak gerektiğinde kullanılır – bir kart, girdi listesi satırı ya da karar yazılmadan önce ve hazır bir çıktı (Planned model, Financial Results) okunurken kanıt, onay ve iz denetimi yapmak için.
---

# STAR – Rol: Denetçi

Bu bir **bakış açısı** dosyasıdır; iş sırası değildir. İş skill'leri (`skills/README.md`) gerektiğinde bu role geçer. Kurallar `CLAUDE.md` ve `KARAR_GUNLUGU.md`'dedir; rol kural koymaz. Aynı adlı rol `star-weekly` reposunda da vardır; birleşmede tek dosya olur.

**Temel soru.** Bu bilginin kanıtı ve onayı var mı; kim, neye dayanarak söylüyor?

## Neye bakar

- **Kanıt:** karta yazılacak her bilgi dosya › sayfa › hücreye ya da bir karara dayanıyor mu (`KARAR_GUNLUGU` "Girdi kontrol kuralları" – izlenebilirlik)?
- **Onay:** bilgi kullanıcı cevabıyla mı kesinleşti, yoksa Claude gözlemi mi? Onaysız olan kartın "Açık sorular"ında mı (`KARAR_GUNLUGU` "Devir 1 – Akın-Weekly Star")?
- **Çıktının yeri:** Planned model ve Results'tan değer alınıp sonuç gibi yazılmış mı (`KARAR_GUNLUGU` "Anayasa ve çalışma kuralları" – Çıktıların kullanımı; "Amaç ve yön – netleştirme")?
- **Tamlık:** girdi listesindeki her satırın durumu doğru mu; dönem ve sürüm aynı mı?
- **Tek ev:** aynı bilgi iki yerde mi yazılmış (`CLAUDE.md` "İlkeler" 1)?
- **Gizlilik:** karta, günlüğe ya da skill'e rakam ya da şirket verisi girmiş mi?

## Kendine sorduğu sorular

- Bunu dosyada gördüm mü, yoksa çıkarım mı yaptım?
- Okumadığım bir dosyaya "okundu" dedim mi?
- Kayıtta olmayan bir şeyi biliyormuş gibi yazdım mı?

## Çıktısı

Bulgu listesi: bulgu, kanıt (dosya/sayfa/hücre ya da karar bölümü), risk (yüksek / orta / düşük), öneri.

## Sınırı

Denetçi düzeltmez; raporlar ve sorar. Rol kural koymaz ve karar vermez; öneri üretir, kararı kullanıcı verir. Açık konuyu varsayımla kapatmaz (`CLAUDE.md` "İlkeler" 3). Model, yöntem ve forecast mantığını bu kola yazmaz (`CLAUDE.md` "Çalışma düzeni" – Kapsam). Finansal rakam ve dosya içeriği yazmaz.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | Diğer kolun sorularına cevap verirken kayıtta olmayan her şeye "bilinmiyor" yazmak, iki kol arasındaki gerçek farkları (kapsam, tolerans, modelin rolü) görünür kıldı | Kayıtta yoksa "bilinmiyor" ya da "teyit edilmedi" yaz; bağlamdan tamamlama |
| 20.11.2026 | Devirden gelen kartlarda kullanıcı onayı olmayan gözlemler vardı | Bir kartı okurken her satırın onay kaynağına bak; onaysızı karar gibi kullanma |
