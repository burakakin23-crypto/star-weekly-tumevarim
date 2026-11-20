---
name: star-girdi-listesi
description: STAR Weekly tümevarım kolunda bir dönemin girdi listesi çıkarılırken ya da güncellenirken kullanılır – Planned modelin, Financial Results'ın ve girdi dosyalarının dış bağlantıları okunurken, GIRDI_LISTESI.md'ye satır eklenirken ya da durum değiştirilirken.
---

# STAR – Girdi listesi ve dış bağlantı çıkarma

Bu skill yalnız sırayı tutar. Dayandığı kurallar: `CLAUDE.md` "İlkeler", "Bilgi nerede durur"; `KARAR_GUNLUGU` "Girdi kontrol kuralları", "Amaç ve yön – netleştirme" (Kapsam aşamalı; Karşılaştırmada girdi sürümü), "Açık konular".

## Ne zaman kullanılır

Yeni bir dönemin modeli geldiğinde; bir girdi dosyası tanıtılırken kendi bağlantıları çıkarılırken; bir dosyanın durumu değiştiğinde; diğer kol listede olmayan bir dosya bildirdiğinde.

## Adımlar

**1. Kaynakları belirle**
Planned model, Financial Results ve o güne kadar gelen her girdi dosyası. Dosyaların kopyasında çalış.

**2. Dış bağlantıları çıkar**
1. Her dosyanın dış bağlantı listesini oku: bağlandığı dosyanın adı, bağlantının hangi sayfa ve satır grubunda kullanıldığı.
2. Adı dosyada yazdığı gibi kaydet; sürümü ya da bazı adı yorumlayarak değiştirme.
3. Aynı dosyanın iki farklı kopyasına ya da konumuna giden bağlantıyı ayrıca işaretle.
4. `star-rol-model-denetcisi` gözüyle bak: başka aya ya da eski baza giden bağlantı, elle yazılmış değerle örtülmüş bağlantı.

**3. Bölümlere ayır**
`GIRDI_LISTESI.md`'deki bölüm düzenini koru: çalışılan ayın EBITDA'sına doğrudan giren ham girdiler; türeyen hesap dosyaları; EBITDA altı (aşama 2–3); gerçekleşen aylar; kapsam dışı ay; karşılaştırma dosyaları; eskimiş görünen bağlantılar.

**4. Bağlantıda görünmeyeni ara**
1. Dış bağlantı listesi elle kopyalanmış ya da yapıştırılmış veriyi göstermez. Girdi içindeki tarihli, yapıştırılmış ya da başka ekip adını taşıyan sayfaların kaynağını soru olarak yaz.
2. Diğer kolun kullandığı ama bu listede olmayan dosya bildirilirse kullanıcıya sor; onayla "dosya bekleniyor" durumuyla ekle.

**5. Yaz**
1. Liste yalnız ad, kimin okuduğu ve durumu tutar. Dosyanın ne olduğu kartında yazar.
2. Yeni satırı ve durum değişikliğini kullanıcıya göster; onayla yaz. `git pull --rebase`, küçük commit, `main`'e push.

## Yapma

- Bir dosyayı kapsam içi ya da dışı diye kendin sınıflama; "kapsam kararı bekleniyor" olarak bırak ve sor.
- Listeye dosyanın içeriğini, rakamını ya da hücre eşlemesini yazma.
- Kartı olmayan dosyaya "doğrulandı" durumu verme.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | Liste yalnız dış bağlantılardan çıkarılmıştı; diğer kolun kullandığı Open Trades dosyası listede yoktu | Adım 4'ü atlama: bağlantıda görünmeyen kaynakları ayrıca ara ve sor |
| 20.11.2026 | Planned modelin adı bir aylık bazı taşıyordu, bağlı olduğu girdilerin bir kısmı başka bazın adını taşıyordu | Sürümü modelin adından çıkarma; her bağlantının gittiği dosyanın adını olduğu gibi yaz |
| 20.11.2026 | Girdilerin kendi içinde eski döneme giden bağlantılar vardı | Yalnız modelin değil, her girdinin kendi bağlantılarını da çıkar; eskimiş görünenleri ayrı bölümde tut |
| 20.11.2026 | Model açılış stoğunu iki farklı ay sonu dosyasından okuyordu; hangi satırların hangisinden geldiği kaydedilmemişti | Aynı türden iki dosyaya bağlantı varsa satır grubunu ve hücreyi çıkarırken kaydet |
