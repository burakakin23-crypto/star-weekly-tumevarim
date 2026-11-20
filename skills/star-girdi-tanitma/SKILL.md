---
name: star-girdi-tanitma
description: STAR Weekly tümevarım kolunda bir girdi dosyası sohbete eklendiğinde kullanılır – dosya okunurken, forecast'taki rolü Planned modelin bağlantılarından doğrulanırken ve dosya kartı yazılırken ya da güncellenirken.
---

# STAR – Girdi dosyası tanıtma ve kart yazma

Bu skill yalnız sırayı tutar. Dayandığı kurallar: `CLAUDE.md` "İlkeler", "Dosya kartı", "Çalışma düzeni"; `KARAR_GUNLUGU` "Anayasa ve çalışma kuralları", "Tanıtım turu", "Devir 1 – Akın-Weekly Star", "Girdi kontrol kuralları", "Amaç ve yön – netleştirme".

## Ne zaman kullanılır

Kullanıcı bir girdi dosyasını sohbete eklediğinde ya da var olan bir kart dosyayla doğrulanacağında. Dönem ara dönem (a+p) ise bu skill kullanılmaz: kuralları yeniden sorulacak (`skills/README.md` bekleyenler).

## Adımlar

**1. Al**
1. Dosyayı sohbette kullanıcıdan al. Turun ilk girdisiyle birlikte aynı dönemin Planned modeli ve Financial Results'ı da bir kez gelir; yalnız rolü doğrulamak için kullanılır.
2. Dosya adından değil içeriğinden tanı. Dönem ve sürüm turdaki diğer dosyalarla aynı değilse önce bunu söyle.
3. `GIRDI_LISTESI.md`'de satırı var mı bak; yoksa `star-girdi-listesi` skill'ine geç.

**2. Oku**
1. Dosyanın kopyasında çalış; yüklenen dosyayı değiştirme.
2. Yapıyı çıkar: sayfalar (gizliler dahil), satır grupları (boşlar dahil), sütunların anlamı, birimler.
3. Dosyanın kendi dış bağlantılarını çıkar (`star-girdi-listesi` adım 2).
4. Role geç: `star-rol-model-denetcisi` (bağlantı, elle değer, sabit ay), `star-rol-analist` (eşleme, birim, sayım). Dosyanın türüne göre `star-rol-rafineri-uzmani` ya da `star-rol-hedge-uzmani`.

**3. Rolü doğrula**
1. Planned modelin ve Results'ın bağlantılarından girdinin nereye gittiğini oku. Kullanılan ve kullanılmayan alanları ayır.
2. Model ve Results'ı `star-rol-denetci` gözüyle oku; şüpheli her nokta bulgudur ve sorulur. Çıktıdan değer alıp sonuç gibi yazma.
3. Hücre düzeyindeki eşlemeyi karta yazma; `KARAR_GUNLUGU` "Birleşmede aktarılacaklar"a kısa not olarak gider.

**4. Kartla karşılaştır**
1. Kart varsa satır satır dosyayla karşılaştır. Yazılı her bilgi ve her açık soru yeniden teyide gider.
2. Her bilginin onay kaynağını not et: panel cevabı, günlük kararı ya da yalnız Claude gözlemi.

**5. Sor**
1. Bütün soruları panelde topla: `star-soru-paneli` skill'i.
2. Cevaplar gelmeden kartın başlıklarına yeni bilgi yazma.

**6. Yaz**
1. Cevapları panelden oku. Karta ve günlüğe ne yazacağını önce kullanıcıya göster.
2. Onaylanan kartın başlıklarına, cevaplanmayan "Açık sorular"a. Kart biçimi: `CLAUDE.md` "Dosya kartı".
3. Karar çıktıysa `star-karar-isleme` skill'i. `GIRDI_LISTESI.md`'de durumu güncelle.
4. `git pull --rebase`, küçük commit, `main`'e push; veri dosyasının commit'e girmediğini kontrol et.

## Yapma

- Kullanıcının cevaplamadığı hiçbir şeyi kabul sayma; öneriyi cevap gibi yazma.
- Karta rakam, şirket verisi ya da hücre eşlemesi yazma.
- Planned'da kurulan kuralı ara dönem dosyasına taşıma.
- Aynı bilgiyi hem karta hem günlüğe yazma; kural günlükte, dosya tanımı kartta durur.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | Devirden gelen kartlarda onaylı bilgi ile onaysız gözlem karışıktı; hepsini dosyayla baştan doğrulamak gerekti | Karta her satırı yazarken onay kaynağını bil; kaynağı olmayanı "Açık sorular"a koy |
| 20.11.2026 | Tur 2'de beş dosya analiz edildi ama kartları yazılmadı; durum yalnız girdi listesinde görünüyordu | Analiz edilip kartı bekleyen dosyayı girdi listesinde "🔍" ile işaretle; kart yazılana kadar bulguları panel sorusu olarak tut |
| 20.11.2026 | Bir dosyanın rolü başka bir girdinin içinden geçiyordu (LP fiyatı Hedge Plan üzerinden modele gidiyordu) | Rolü yalnız modelin doğrudan bağlantısından değil, girdiler arası bağlantıdan da izle |
