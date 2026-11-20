# LP model – STAR Budget (2026) - Forecast (gg.aa.yyyy)

## Dosya adı ve sürümü/dönemi
- Geçerli adlar: `STAR Budget (2026) - Forecast (gg.aa.yyyy)` (parantezdeki tarih dosyanın hazırlandığı gün) ve `STAR_LP_<Ay>_2026_0_30_Planned`. İkisi de geçerli; hangisiyle gelirse gelsin ad uyarısı verilmez.
- Planned (0+30) dönemi için girdi; tonaj tüm ayı ifade eder.
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
- Ad farkları ve modelle eşleşme: bkz. Açık sorular.
- Hedge Plan, Budget Calc ve haftalık STAR girdi dosyasıyla ilişki: bkz. Açık sorular.

## Forecast'taki rolü
- Yalnız çalışılan ayın sütunu kullanılır; diğer aylara bakılmaz.
- Buradan gelenler: hacimler (ham petrol, ithal, nihai ürün, utility tüketimi), ham petrol / ithal / ürün fiyatları, Brent, dönüşüm faktörleri, kanal oranları.
- Dönüşüm faktörleri o ay hacim olmasa da kullanılır (stoklar için gerekebilir).
- **Kanal oranı (Export / Domestic / Petkim):**
  - Ürünlerde her zaman kalem / grup toplamından hesaplanır. Dosyada hazır oran gelirse hesaplananla kıyaslanır; farklıysa hesaplanan kullanılır, fark uyarılır. Gelmezse hesaplanan kullanılır.
  - Kanal hacimleri forecast'a doğrudan bu dosyadan girer; oran yalnız açılış stoğunu (ay sonu stok raporu) kanallara bölmek için kullanılır.
  - Ham petrolde kanal dağılımı yapılmaz.
- **Buradan alınmayanlar:**
  - Doğalgaz ve elektrik fiyatları: Gas Power Prices dosyasından gelir (aylık baz etiketiyle, ör. `_10_2`).
  - Process Water (HGU): forecast'a girmez (kalıcı istisna).
- Hücre düzeyindeki model eşlemesi bu kartta yok (bkz. KARAR_GUNLUGU "Birleşmede aktarılacaklar").

## Bilinen tuzaklar / temizlik adımları
- Genel girdi kontrol kuralları geçerli (KARAR_GUNLUGU "Girdi kontrol kuralları").
- Fiyatı olup hacmi olmayan kalemler (ör. LPG (Petkim), Full Range Naphtha (Export/Petkim), Heavy Naphtha (Export)) referans fiyattır; uyarı yeterli.

## Açık sorular
*(STAR) = STAR ekibiyle cevaplanacak.*
- **Dolu aylar:** Kasım 2026 Planned dosyasında yalnız cari ay (Kasım) ve sonraki ay (Aralık) dolu, Ocak–Ekim boş. Planned LP her zaman böyle mi gelir?
- **Birimler (STAR):** Ham petrol fiyatı $/bbl, ithal fiyatı $/ton, Production Plan ton/ay, elektrik MWh/ay, ürün fiyatı $/ton olarak okundu. Product Prices başlığında "(ton/month)" yazıyor, değerler $/ton görünüyor.
- **Ad farkları (STAR):** LP kalem adı modeldeki satır adıyla birebir aynı değil: KEBCO ↔ Kebco (Kazakh Export Blend Crude Oil) · Ural (Spot) ↔ Ural · Reformate (Export) ↔ Reformate · High Sulphur Gasoil 0.1% ↔ High Sulphur Gasoil. Dosya içinde: Product Prices "ULSD (Export)" ↔ Production Plan "ULSD 10 ppm (Export)". Bu liste kartta kalıcı eşleşme olarak durmalı mı?
- **Doğalgaz satırları (STAR):** Modelde "Natural Gas" (LP'deki Natural Gas (Process)) ve "Natural gas" (LP'deki Natural Gas (Fuel)) yalnız büyük/küçük harfle ayrılıyor. Tuzak olarak yazılmalı mı?
- **Q sütunu sabit ay (STAR):** Kanal oranı formülleri yalnız Kasım sütununa yazılmış; ay değişince kendiliğinden kaymaz. Tuzak olarak yazılmalı mı?
- **ULSD / Jet fiyatı (STAR):** Ana model ULSD/Jet fiyatını Hedge Plan'dan alıyor; Hedge Plan ise bu fiyatı LP'nin efektif fiyatlarından (Product Prices: ULSD Domestic-1–4, Jet Domestic-1, Domestic-2, Export) hesaplıyor. LP, ULSD/Jet için taban fiyatın kaynağı mı?
- **Efektif fiyat bloğu (STAR):** Product Prices'ta benzin, Jet ve ULSD için yoğunluk düzeltmeli efektif fiyat hesabı var: efektif fiyat = satış fiyatı × (referans yoğunluk / üretilen yoğunluk). Yoğunluk boşsa efektif fiyat boş çıkıyor (Kasım'da Jet Domestic-3, ULSD Export ve benzinde satış fiyatı var, yoğunluk yok). Karta nasıl yazılmalı; yoğunluk boşluğu uyarı mı?
- **HSGO ve VGO iki bölümde (STAR):** Production Plan'da hem Crude Oil bölümünde ($/bbl, kendi assay'iyle) hem Imports bölümünde ($/ton; HSGO "0.1%") var; ana model ikisini de alıyor. Ayrı kargolar mı, çift sayım mı?
- **Pozitif ara ürünler (STAR):** High Sulphur Gasoil ve Vacuum Residue hacim ve fiyatla dolu, LP kendi hesabında satış sayıyor; ana model bunları almamış. Eski projede "kullanıcı hatası, eksik bağlantı" denmişti. Forecast'a satış olarak girmeli mi?
- **Dönüşüm faktörü boşlukları (STAR):** 16 satırda faktör dolu ama ana modele bağlı değil: 10 ham petrol (Arab Heavy, Arab Medium, Bonga, Bonny Light, Bouri, Ekofisk, Forcados, Qua Iboe, Val d'Agri, Western Desert), modelde satırı olmayan 4 ham petrol (Arab Extra Light, Kuwait, Tengiz, Vasconia), ithal HSGO 0.1% ve VGO. Hepsi kullanılmalı mı; ithal satırların faktöre ihtiyacı var mı?
- **Forecast'a girmeyen bölümler (STAR):** Process Units sayfası (yalnız Fuel Gas hacmi buradan hesaplanıp giriyor), CDU utilization ve özet satırları (verimler, DCU suyu, toplam doğalgaz/su/elektrik ve fiyatları, VOC, alım/satış, GRM). Kalıcı istisna mı (uyarı vermez), her hafta uyarı mı?
- **Ural (Spot) assay (STAR):** Assay kodu KEBCO'nunkiyle aynı; yoğunluk ve dönüşüm faktörü de aynı çıkıyor. Bilinçli mi?
- **Fiyat kaynağı:** Bütün fiyatlar sabit değer, dosyada dış bağlantı yok. Budget Calc'tan mı kopyalanıyor? Budget Calc turunda bakılacak.
- **Satır durum sınıflaması:** Her satır her ay şu durumlardan birine konur: dolu + karşılığı var · dolu + karşılığı yok (uyarı) · boş + karşılığı var · boş + karşılığı yok · yeni satır (sorulur). Grup listesi Yapı'da onaylandı; sınıflamanın kendisi teyit bekliyor (eski M17).
- **Haftalık sürümle ilişki:** Planned olmayan actual + forecast sürümü (`STAR_LP_<Ay>_2026_<a>_<p>`) ile haftalık `STAR <Ay> 2026 a__p.xlsx` aynı dosya mı? Haftalık dosya gelince bakılacak.

## Tanıtım tarihi
- 10.11.2026 (Akın-Weekly Star'da). Bu repoya devir: 20.11.2026. Dosyayla doğrulama: 20.11.2026 (Kasım 2026 Planned).
