---
name: star-soru-paneli
description: STAR Weekly tümevarım kolunda kullanıcıya ya da STAR ekibine sorulacak sorular bir panelde (claude.ai sayfası) toplanırken ve cevaplar panelden okunurken kullanılır – tanıtım turu soruları, karar soruları ya da bir kişiden görüş alınması için.
---

# STAR – Soru paneli hazırlama

Bu skill yalnız sırayı tutar. Dayandığı kurallar: `CLAUDE.md` "İlkeler" 3 (anayasa); `KARAR_GUNLUGU` "Anayasa ve çalışma kuralları", "Tanıtım turu".

## Ne zaman kullanılır

Bir turun soruları toplandığında; birden çok açık konu aynı anda karar beklediğinde; kullanıcı bir kişiden görüş almak istediğinde. Tek bir soru için panel açma; sohbette sor.

## Adımlar

**1. Soruları topla**
1. Kaynaklar: kartların "Açık sorular"ı, `KARAR_GUNLUGU` "Açık konular", turdaki bulgular. Karta yazılı bilgiler de teyit için sorulur.
2. Her soru tek bir şeyi sorar ve bağlamını içinde taşır: ne görüldü, hangi dosya ve sayfada.
3. Soruları bölümlere ayır (çelişkiler, onay bekleyenler, yeni bilgiler, bulgular gibi). Kime sorulacağı belliyse belirt.
4. `star-rol-sunumcu` gözüyle oku: projeyi bilmeyen biri anlayabilir mi? `star-rol-cfo` gözüyle sırala: sonucu değiştiren soru önce.

**2. Seçenekleri yaz**
1. Her soruda: önerilen seçenek (işaretli), diğer seçenekler, "Açık kalsın", "Diğer" (serbest metin) ve not alanı.
2. Her soruda Claude'un emin olup olmadığını yaz.
3. Hiçbir seçenek önceden seçili gelmez.

**3. Sayfayı kur**
1. Önceki panelin görsel dilini ve yapısını kullan (bölüm listesi, ilerleme sayacı, yalnız cevaplanmamışlar süzgeci, cevap özeti).
2. Cevaplar kalıcı ve ortak kaydedilir; her soru için tek kayıt. Kaydın nereye yazıldığını not et; cevaplar oradan okunacak.
3. Yayınlamadan önce bir kez dene: bir seçenek işaretle, "Diğer"e yaz, hemen ardından başka bir soruda seçenek tıkla; sayaç ikisini de saymalı.
4. Panele rakam ve şirket verisi yazma.

**4. Teslim et**
1. Bağlantıyı ver; kaç soru ve hangi bölümler olduğunu söyle.
2. Sayfa yayınlandığında yalnız sahibine açıktır: başkası cevaplayacaksa paylaşılması gerektiğini söyle.
3. Tur panelinin bağlantısını günlüğe yazmak karardır: `star-karar-isleme`.

**5. Cevapları oku**
1. Cevapları panelin kaydından oku; sohbetteki özete ya da kendi önerine dayanma.
2. Önerilenden farklı seçilenleri ve "Diğer" cevaplarını ayrıca listele.
3. Cevaplanmayan soru açık kalır. Yazılacak metni kullanıcıya göster; sonrası `star-girdi-tanitma` adım 6 ya da `star-karar-isleme`.

## Yapma

- Seçilmeyen öneriyi kabul sayma.
- "Diğer" seçilip metin yazılmadıysa soruyu cevaplanmış sayma.
- Cevapları okumadan karta ya da günlüğe yazma.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | Kullanıcı on yedi sorudan ikisinde önerileni seçmedi | Cevabı her zaman kayıttan oku; öneriyi cevap yerine koyma |
| 20.11.2026 | Yayın öncesi denemede, yazı alanından çıkıp hemen bir seçeneğe tıklayınca sayfa yeniden çizildiği için tıklama kayboluyordu | Kayıttan sonra yeniden çizimi kısa bir gecikmeyle yap; kullanıcı yazarken çizme; adım 3.3'teki denemeyi atlama |
| 20.11.2026 | Kullanıcı seçeneklere ek olarak kendi cevabını yazabilmek istedi | Her soruda "Diğer" ve not alanı olsun |
| 20.11.2026 | İkinci panel ilkinin görsel diliyle kuruldu; kullanıcı yeniden alışmak zorunda kalmadı | Yeni panelde önceki panelin yapısını kullan |
| 20.11.2026 | Panel kaydının boş olduğu okundu ama gerçek bir cevabın kaydedildiği denenmedi; bunu kullanıcıya söylemek gerekti | Neyi denediğini ve neyi deneyemediğini teslimde tek cümleyle söyle |
| 23.11.2026 | Kullanıcı seçeneklerin hiçbirine uymayan cevabı yoruma yazdı; sayaç saymadığı için "Açık kalsın"ı seçmek üzereydi | Her soruya "Seçeneklerden biri değil, yorumda yazdım" seçeneği koy; böyle cevapta yalnız yorumu esas al |
| 23.11.2026 | Paneli ikinci oturuma taşırken cevaplananlar kapalı listeye alındı, "Açık kalsın" seçilenler açık sayıldı, anlaşılmayan sorular yeni kimlikle yeniden soruldu (ör. D5 → D5b) | Oturumlar arası panelde aynı düzeni kullan; eski cevabın üzerine yazma, yeniden sorulan soruya yeni kimlik ver |
