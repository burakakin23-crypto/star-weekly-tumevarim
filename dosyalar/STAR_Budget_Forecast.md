# LP model – STAR Budget (2026) - Forecast (gg.aa.yyyy)

## Dosya adı ve sürümü/dönemi
- Geçerli adlar: `STAR Budget (2026) - Forecast (gg.aa.yyyy)` (parantezdeki tarih dosyanın hazırlandığı gün) ve `STAR_LP_<Ay>_2026_0_30_Planned`. İkisi de geçerli; hangisiyle gelirse gelsin ad uyarısı verilmez.
- Planned dönemi için girdi; tonaj tüm ayı ifade eder. 0+30 ayrı bir versiyondur ve aynı biçimdeki LP'yi kullanır (bkz. KARAR_GUNLUGU "Tur 1 panel cevapları").
- Ad kalıbındaki `0_30`, `9_22` gibi ekler ayın gerçekleşen + forecast gün dağılımıdır (ör. `9_22` = 9 gün gerçekleşen + 22 gün forecast).
- Doğrulanan sürüm: Kasım 2026 Planned, 03.11.2026 tarihli dosya.

## Kaynak
- Doğrudan Ticaret ekibinden gelir.
- Girdi kontrolündeki geri bildirim de Ticaret'e gider ("geçen hafta X verdiniz, şimdi Y, doğru mu?").

## Sıklık
- Ayda bir, Planned döneminin başında.

## Yapı
- 4 sayfa: **Production Plan**, **Process Units**, **Crude & Import Prices**, **Product Prices**.
- Kalem adı **C** sütununda; aylar **D–O** (Ocak–Aralık).
- Production Plan **Q** sütunu: kanal oranı yardımcı formülleri (kalem / grup toplamı).
- Crude & Import Prices **S** sütunu: dönüşüm faktörü (bbl/t).
- Satır grupları (boş satırlar dahil):
  - Hacim (Production Plan): Crude Oil 43 · Imports 7 · Utility 6 · Final Products 27 · Intermediate Products 17.
  - Fiyat: aynı gruplar (Crude & Import Prices, Product Prices) + ham petrol ve ithal için dönüşüm faktörü.

## Anahtar alanlar ve diğer dosyalarla eşleşmesi
- Anahtar: kalem adı (C sütunu).
- Ad farkları (LP → model): KEBCO → Kebco (Kazakh Export Blend Crude Oil) · Ural (Spot) → Ural · Reformate (Export) → Reformate · High Sulphur Gasoil 0.1% → High Sulphur Gasoil. Dosya içinde: Product Prices "ULSD (Export)" ↔ Production Plan "ULSD 10 ppm (Export)". Listede olmayan farklı bir adlandırma görülürse sorulur.
- Hedge Plan, Budget Calc ve haftalık STAR girdi dosyasıyla ilişki: bkz. Açık sorular.

## Forecast'taki rolü
- Yalnız çalışılan ayın sütunu kullanılır; diğer aylara bakılmaz. Hangi ayın çalışıldığı LP'nin adından okunur.
- Buradan gelenler: hacimler (ham petrol, ithal, nihai ürün, utility tüketimi), ham petrol / ithal / ürün fiyatları, Brent, dönüşüm faktörleri, kanal oranları.
- Dönüşüm faktörleri o ay hacim olmasa da kullanılır (stoklar için gerekebilir). LP'deki bütün faktörler kullanılır; LP'de olup modelde karşılığı olmayan bir ham petrol görülürse uyarılır.
- HSGO ve VGO hem Crude Oil hem Imports bölümünde yer alabilir; bunlar ayrı kargolardır, ikisi de forecast'a girer.
- Ara ürünler (Intermediate Products): + gelirse ara ürün satışı olarak girer (hacim ve fiyat ara ürün satırlarına).
- ULSD ve Jet: bu dosyadaki efektif fiyatlar Hedge Plan'a hedgesiz fiyat olarak gider; forecast fiyatı Hedge Plan'dan gelir.
- "Her ürünün fiyatı ve hacmi LP'den" ifadesi doğalgaz/elektrik fiyatını ve ULSD/Jet'in nihai fiyatını kapsamaz.
- **Kanal oranı (Export / Domestic / Petkim):**
  - Ürünlerde her zaman kalem / grup toplamından hesaplanır. Dosyada hazır oran gelirse hesaplananla kıyaslanır; farklıysa hesaplanan kullanılır, fark uyarılır. Gelmezse hesaplanan kullanılır.
  - Kanal hacimleri forecast'a doğrudan bu dosyadan girer; oran yalnız açılış stoğunu (ay sonu stok raporu) kanallara bölmek için kullanılır.
  - Ham petrolde kanal dağılımı yapılmaz.
- **Buradan alınmayanlar:**
  - Doğalgaz ve elektrik fiyatları: Gas Power Prices dosyasından gelir (aylık baz etiketiyle, ör. `_10_2`).
  - Process Water (HGU): forecast'a girmez (kalıcı istisna).
  - Kalıcı istisnalar (forecast'a girmez, uyarı vermez): Process Units sayfası (yalnız Fuel Gas hacmi oradan hesaplanıp girer), CDU utilization, özet satırları (verimler, DCU suyu, toplam doğalgaz/su/elektrik ve fiyatları, VOC, alım/satış, GRM). Dayanak: Kasım 2026 Planned modelinin bu dosyaya olan bağlantılarının hiçbiri bu hücrelere gitmiyor. Listede olmayan yeni bir istisna görülürse uyarılır.
- Hücre düzeyindeki model eşlemesi bu kartta yok (bkz. KARAR_GUNLUGU "Birleşmede aktarılacaklar").

## Bilinen tuzaklar / temizlik adımları
- Genel girdi kontrol kuralları geçerli (KARAR_GUNLUGU "Girdi kontrol kuralları").
- Fiyatı olup hacmi olmayan kalemler (ör. LPG (Petkim), Full Range Naphtha (Export/Petkim), Heavy Naphtha (Export)) referans fiyattır; uyarı yeterli.
- Modelde doğalgaz satırları "Natural Gas" (LP'deki Process) ve "Natural gas" (LP'deki Fuel) yalnız büyük/küçük harfle ayrılır; ayrım LP'deki parantezden yapılır.
- Production Plan Q sütunundaki kanal oranı formülleri tek bir aya sabit yazılmış; ay değişince kendiliğinden kaymaz. Oran zaten her zaman hesaplanır.
- Ural (Spot)'un assay'i bilinçli olarak KEBCO'nunkiyle aynıdır.
- Product Prices'ta fiyat, ürün satırlarından (ör. ULSD ve Jet satırları) olduğu gibi alınır. Altındaki yoğunluk düzeltmeli efektif fiyat bloğu LP'nin kendi iç hesabıdır; bu kolda hesaplanmaz, kural konmaz. Orada mantıksız bir şey görülürse yalnız bilgi olarak bildirilir. Ürün satırında fiyat boş ama hacim varsa genel kural uygulanır (hacim var, fiyat yok = hata).
- Bulgu: Kasım 2026 Planned modelinde pozitif High Sulphur Gasoil ve Vacuum Residue ara ürün satırlarına bağlanmamış.

## Açık sorular
*(STAR) = STAR ekibiyle cevaplanacak.*
- **Birimler (STAR):** Ham petrol fiyatı $/bbl, ithal fiyatı $/ton, Production Plan ton/ay, elektrik MWh/ay, ürün fiyatı $/ton olarak okundu. Product Prices başlığında "(ton/month)" yazıyor, değerler $/ton görünüyor. (Tur 1 B1: açık)
- **Negatif ara ürünün fiyatı (STAR):** − gelen ara ürün import satırına pozitif hacim olarak işlenir; fiyatı ithal fiyatı mı (Crude & Import Prices), ara ürün fiyatı mı (Product Prices)? Negatif HSGO, Imports'taki "HSGO 0.1%" ile aynı model satırına düşer. (Tur 1 C2: açık)
- **Fiyat kaynağı:** Bütün fiyatlar sabit değer, dosyada dış bağlantı yok. Budget Calc'tan mı kopyalanıyor? Budget Calc tanıtılırken bakılacak.
- **Haftalık sürümle ilişki:** Planned olmayan actual + forecast sürümü (`STAR_LP_<Ay>_2026_<a>_<p>`) ile haftalık `STAR <Ay> 2026 a__p.xlsx` aynı dosya mı? Haftalık dosya gelince bakılacak.

## Tanıtım tarihi
- 10.11.2026 (Akın-Weekly Star'da). Bu repoya devir: 20.11.2026. Dosyayla doğrulama: 20.11.2026 (Kasım 2026 Planned). Tur 1 panel cevapları: 23.11.2026.
