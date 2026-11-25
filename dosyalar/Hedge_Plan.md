# Hedge Plan

## Dosya adı ve sürümü/dönemi
- Standart ad: `Hedge_Plan_2026_0_30 Forecast_<Ay> Planned`. Başka adla gelirse (ör. Kasım 2026 Planned modelinin bağlı olduğu `Hedge Plan 2026 10 2  Forecast_November Planned`; ad içinde çift boşluk var) uyarılır; dosya yine içerikten tanınır.
- Doğrulanan sürüm: Kasım 2026 Planned (10+2 aylık baz).

## Kaynak
- Ticaret ekibi hazırlıyor. (Önceki kartta "finans ekibinin kendi süreci" yazıyordu; 25.11.2026'da düzeltildi.)

## Sıklık
- Haftalık.

## Yapı
- Görünür sayfalar: **Summary**, **ULSD_Hedge Calculation**, **Jet_Hedge Calculation** ve son iki tarihli işlem sayfası (adı `ggaayyyy`).
- Gizli sayfalar: eski tarihli işlem sayfaları, **VGO_Hedge Calculation**, **Crude_Hedge Calculation**.
- Hesap sayfalarında aylar sütunlarda (Ocak = C … Aralık = N; Kasım = M).
- Summary'de aylık hedge tutarları, önceki versiyon sütunu ve fark sütunu var.

## Anahtar alanlar ve diğer dosyalarla eşleşmesi
- Dayandığı girdiler (Kasım 2026 Planned dosyasının bağlantılarından; ayrıntıları ayrıca konuşulacak):
  - LP model: ULSD ve Jet efektif fiyatları hedgesiz fiyat olarak.
  - STAR EBITDA Crack Margin Effect: forecast crack olarak "güncel crack" (Daily Prices and Ratios dosyasının son 5 kotasyonunun ortalaması).
  - Budget Calc: CIF-FOB farkı ve dönüşüm faktörü. Güncel sürüm kullanılmalı.
  - Tarihli işlem sayfaları (olası kaynağı Open Trades): hedge crack, hedge miktarı, işlem MTM'leri.
  - Ana model: kanal hacimleri. Girdilerden çalışırken hacimler LP'den alınır.

## Forecast'taki rolü
- **Hedef:** Hedge Plan, Claude'un girdilerden hazırlayacağı bir çıktı olacak. Bunun için gereken girdiler (Open Trades, LP, Daily Prices – güncel fiyatla ilerlenirse, Budget Calc ve diğerleri) öğrenilir. Verilen girdi güncel kabul edilir; Claude yine de kendisi teyit eder.
- Yalnız çalışılan ayın rakamı kullanılır; geçmiş ve gelecek aylara bakılmaz.
- Ana model ULSD Domestic-1–4 ile Jet Domestic-1, Domestic-2 ve Export'un ağırlıklı fiyatını buradan alır. Hesap girdilerden yapılır; hedgesiz fiyatın tabanı LP'deki fiyattır.
- **Crude Roll + Inventory Hedge ve Product Inventory Hedge:** İşlemlerin buy ve sell ayakları vardır; satış (sell) ayağı çalışılan aya düşen işlem çiftleri alınır ve iki ayağın toplam etkisi finansala yansıtılır. Kasım 2026 Planned örneğinde güncel tarihli sayfadaki ilgili satırlar (crude roll için dört satır, product için iki satır) Summary'nin aldığı satırlarla aynı.
- Kural: Summary'deki "Crude Roll + Inventory Hedge" tutarı COGS'a, "Product Inventory Hedge" tutarı gelire eklenir. Kasım 2026 Planned Financial Results bunun tersini yapıyor (crude roll gelire, product hedge COGS'a); bu fark bulgu olarak tutulur ve sonraki ay gözlemlenir. Crack hedge etkisi ayrıca eklenmez, fiyatın içindedir.
- Summary sayfası çıktı olarak verilir (KARAR_GUNLUGU "Birleşmede aktarılacaklar").
- Hücre düzeyindeki model eşlemesi ve hedge hesabı bu kartta yok (bkz. KARAR_GUNLUGU "Birleşmede aktarılacaklar").

## Bilinen tuzaklar / temizlik adımları
- Genel girdi kontrol kuralları geçerli (KARAR_GUNLUGU "Girdi kontrol kuralları").
- ULSD Export (`ULSD_Hedge Calculation`!M47) ve Jet Domestic-3 (`Jet_Hedge Calculation`!M45) hedgesiz fiyat hücrelerine LP'den bağlantı yerine elle 0 yazılmış; hacim gelirse bu kanallar 0 fiyatla hesaplanır.
- Bulgu: Jet hesabındaki "ton başına fiyat artışı" dönüşüm faktörünü eski Budget Calc'tan (9+3) alıyor; güncel Budget Calc olmalı (ULSD aynı hesapta güncelini kullanıyor).
- Ana modelin sakladığı ULSD/Jet fiyatları bu dosyadaki değerlerle aynı değil (model, Hedge Plan'ın Budget Calc crack'iyle hesaplandığı haliyle kaydedilmiş; dosya sonra güncel crack'e geçmiş). Bu bağlantı güncelleme farkı şimdilik dikkate alınmaz; hesap girdilerden yapılır.
- Summary'deki önceki versiyon sütunu hesapta kullanılmaz; yalnız kıyas için getirilir.
- Financial Results'ın "model harici etkiler" dökümündeki Kasım "Hedge_1" ve "Hedge_2" satırları eski 9+3 Hedge Plan'ı okuyor; döküm verisi eski kalmış olabilir, güncellenmeli (bulgu).

## Açık sorular
*(STAR) = STAR ekibiyle cevaplanacak.*
- **Forecast crack'in kaynağı (STAR, Tur 1 A3/A3b):** STAR notu "aylıkta crack margin Budget Calc'tan gelir, ULSD_Hedge Calculation'a gider" onaylandı. Dosyada ise Kasım forecast crack = güncel crack (Crack Margin Effect; Daily Prices'ın son 5 kotasyonu) + Budget Calc CIF-FOB farkı. Ana modelin sakladığı ULSD/Jet fiyatları ise forecast crack = Budget Calc crack'i + CIF-FOB farkı haliyle birebir tutuyor. Financial Results güncel crack ile Budget Calc crack'i arasındaki farkı Crack Margin Effect üzerinden gelire ayrıca ekliyor. Hedge Plan'ın forecast crack'i hangisi olmalı; güncel crack hem fiyata hem Crack Margin Effect'e girerse etki iki kez sayılır mı?
- **Hedge Plan'ı hazırlamak için gereken girdiler:** Tam liste ve her birinin hangi hücreyi beslediği; Open Trades dosyası gelince tarihli işlem sayfalarıyla karşılaştırılacak (GIRDI_LISTESI A19).
- **Hedge Plan çıktısının biçimi:** Summary dahil hangi tablo ve sütunlar gösterilecek; önceki versiyonla kıyas gösterilecek mi? `star-weekly` kolundaki hedge plan sayfasıyla birlikte karar verilecek.

## Tanıtım tarihi
- 11.11.2026 (Akın-Weekly Star'da). Bu repoya devir: 20.11.2026. Dosyayla doğrulama: 20.11.2026 (Kasım 2026 Planned). Tur 1 panel cevapları: 23.11.2026 ve 25.11.2026.
