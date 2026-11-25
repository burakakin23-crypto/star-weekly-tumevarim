# Hedge Plan

## Dosya adı ve sürümü/dönemi
- Standart ad: `Hedge_Plan_2026_0_30 Forecast_<Ay> Planned`. Başka adla gelirse (ör. Kasım 2026 Planned modelinin bağlı olduğu `Hedge Plan 2026 10 2  Forecast_November Planned`; ad içinde çift boşluk var) uyarılır; dosya yine içerikten tanınır.
- Doğrulanan sürüm: Kasım 2026 Planned (10+2 aylık baz).

## Kaynak
- Finans ekibinin kendi sürecinden geçer (ULSD/Jet hedge hesabı ve Summary). İç süreç adımı olarak ele alınır.
- Ticari Risk'in rolü: bkz. Açık sorular.

## Sıklık
- Teyitsiz (bkz. Açık sorular).

## Yapı
- Görünür sayfalar: **Summary**, **ULSD_Hedge Calculation**, **Jet_Hedge Calculation** ve son iki tarihli işlem sayfası (adı `ggaayyyy`).
- Gizli sayfalar: eski tarihli işlem sayfaları, **VGO_Hedge Calculation**, **Crude_Hedge Calculation**.
- Hesap sayfalarında aylar sütunlarda (Ocak = C … Aralık = N; Kasım = M).
- Summary'de aylık hedge tutarları, önceki versiyon sütunu ve fark sütunu var.

## Anahtar alanlar ve diğer dosyalarla eşleşmesi
- Dosyanın dayandığı girdiler: bkz. Açık sorular.

## Forecast'taki rolü
- Ana model ULSD Domestic-1–4 ile Jet Domestic-1, Domestic-2 ve Export'un ağırlıklı fiyatını buradan alır.
- LP'nin ULSD ve Jet efektif fiyatları buraya hedgesiz fiyat olarak gelir.
- Kural: Summary'deki "Crude Roll + Inventory Hedge" tutarı COGS'a, "Product Inventory Hedge" tutarı gelire eklenir. Kasım 2026 Planned Financial Results bunun tersini yapıyor (crude roll gelire, product hedge COGS'a); bu fark bulgu olarak tutulur ve sonraki ay gözlemlenir. Crack hedge etkisi ayrıca eklenmez, fiyatın içindedir.
- Summary sayfası çıktı olarak verilir (KARAR_GUNLUGU "Birleşmede aktarılacaklar").
- Dosya kanal hacimlerini ana modelden okuyor. Girdilerden çalışırken hacimler LP model'den alınır.
- Hücre düzeyindeki model eşlemesi ve hedge hesabı bu kartta yok (bkz. KARAR_GUNLUGU "Birleşmede aktarılacaklar").

## Bilinen tuzaklar / temizlik adımları
- Genel girdi kontrol kuralları geçerli (KARAR_GUNLUGU "Girdi kontrol kuralları").

## Açık sorular
*(STAR) = STAR ekibiyle cevaplanacak.*
- **Ticari Risk'in rolü (STAR):** Dosyada "TİCARİ RİSK'den GELEN HESAPLAMA" bölümü ve karşı taraf / MTM içeren tarihli işlem sayfaları var. İşlem sayfaları Ticari Risk'ten mi geliyor?
- **Sıklık (STAR):** Kasım Planned dosyasında iki güncel tarihli işlem sayfası var. Dosya haftalık mı, Planned başında ayda bir mi geliyor?
- **Forecast crack'in kaynağı (STAR, 2. oturum):** STAR notu "aylıkta crack margin Budget Calc'tan gelir, ULSD_Hedge Calculation'a gider" onaylandı. Dosyanın formülü ise şöyle: Kasım forecast crack = STAR EBITDA Crack Margin Effect'teki "güncel crack" (Daily Prices and Ratios dosyasının son 5 kotasyonunun ortalaması) + Budget Calc'tan yalnız CIF-FOB farkı; dönüşüm faktörü de Budget Calc'tan. İkisi nasıl bağdaşıyor? (Tur 1 A3)
- **Results'ta eski Hedge Plan (STAR, bulgu):** Financial Results PL'deki "Model harici etkiler" dökümünde Kasım "Hedge_1" ve "Hedge_2" satırları eski 9+3 Hedge Plan'ı okuyor; ana gelir/COGS satırları güncel Hedge Plan'ı kullanıyor. Results'ın kendi CHECK satırı bu yüzden de sıfır değil.
- **Dayandığı girdiler (STAR):** Bağlantılardan görülen: LP model efektif fiyatı (hedgesiz fiyat), STAR EBITDA Crack Margin Effect (forecast crack), Budget Calc (CIF-FOB farkı ve dönüşüm faktörü), tarihli işlem sayfası (hedge crack ve miktar), ana model (kanal hacimleri). Doğru mu?
- **Hangi tarihli işlem sayfası esas (STAR):** Hedge crack ve miktar daha eski bir tarihli sayfadan okunuyor; dosyada daha yeni iki sayfa var (bu ay değerler aynı). En güncel sayfa mı, analistin seçtiği mi? (eski H2)
- **Open Trades ile ilişki (STAR):** `star-weekly` kolu hedge crack ve çeyrek hacmini ayrı bir dosyadan (`STAR Open Trades_<ggaayy>`, tarih adlı sayfa) okuyor. Bu karttaki tarihli işlem sayfaları o dosyanın kopyası mı, bağlantısı mı? Hücre bazında teyit edilmedi; dosya gelince bakılacak (GIRDI_LISTESI A19).
- **Model ile dosya farkı (STAR):** Ana modeldeki ULSD/Jet fiyatı bu dosyadaki ağırlıklı fiyattan yüksek (ürün başına her kanalda aynı fark); model güncel hedge dosyasıyla yeniden hesaplanmamış görünüyor. Financial Results ise hedge tutarlarını güncel dosyadan almış. Girdiden çalışırken esas hangisi? (eski H4)
- **Crude roll kapsamı (STAR):** Summary'deki Kasım "Crude Roll + Inventory Hedge" tutarı tarihli sayfadaki işlemlerin bir kısmını topluyor; sonradan eklenen iki işlem dahil değil. Summary'de "Roll olan işlemleri almamak gerekebilir" notu var. Hangi işlemler girer, yeni işlem otomatik dahil olur mu, roll'lar Brent fiyatında zaten var mı (çift sayım)? (eski H3)
- **Jet dönüşüm faktörü (STAR):** Jet hesabındaki "ton başına fiyat artışı" dönüşüm faktörünü eski Budget Calc'tan (9+3) alıyor; ULSD aynı hesapta güncel Budget Calc'ı (10+2) kullanıyor. Hata mı?
- **Elle yazılmış fiyatlar (STAR):** ULSD Export ve Jet Domestic-3'ün hedgesiz fiyatı LP'ye bağlı değil, hücreye elle yazılmış (Kasım'da ikisinin hacmi yok). Tuzak olarak yazılmalı mı?
- **Önceki versiyonla karşılaştırma (STAR):** Summary'deki önceki versiyon (elle yazılmış) ve fark sütunları her koşuda beklenen çıktının parçası mı? (eski H8)
- **Financial Results'ta artık hücre (STAR, bulgu):** Results PL sayfasında tablo dışında kalan bir hücre (AE1) bu dosyanın Kasım "Product Inventory Hedge" tutarını okuyor; başka yere bağlı görünmüyor. Amaçlı mı?

## Tanıtım tarihi
- 11.11.2026 (Akın-Weekly Star'da). Bu repoya devir: 20.11.2026. Dosyayla doğrulama: 20.11.2026 (Kasım 2026 Planned).
