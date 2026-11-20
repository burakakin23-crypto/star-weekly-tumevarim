# LP model – STAR Budget (2026) - Forecast (gg.aa.yyyy)

## Dosya adı ve sürümü/dönemi
- Standart ad: `STAR Budget (2026) - Forecast (gg.aa.yyyy)`; parantezdeki tarih dosyanın hazırlandığı gün.
- Planned (0+30) dönemi için girdi. İlk incelenen sürüm: Kasım 2026 Planned.

## Kaynak
- Doğrudan Ticaret ekibinden gelir.
- Girdi kontrolündeki geri bildirim de Ticaret'e gider ("geçen hafta X verdiniz, şimdi Y, doğru mu?").

## Sıklık
- Teyitsiz (bkz. Açık sorular).

## Yapı
- 4 sayfa: **Production Plan**, **Process Units**, **Crude & Import Prices**, **Product Prices**.
- Kalem adı **C** sütununda; aylar **D–O** (Ocak–Aralık).
- Production Plan **Q** sütunu: kanal oranı yardımcı formülleri (kalem / grup toplamı).
- Crude & Import Prices **S** sütunu: dönüşüm faktörü (bbl/t).
- Birimler: ham petrol fiyatı $/bbl · ithal fiyatı $/ton · Production Plan ton/ay · elektrik MWh/ay · ürün fiyatı $/ton.

## Anahtar alanlar ve diğer dosyalarla eşleşmesi
- Anahtar: kalem adı (C sütunu).
- Ad farkları (dosya içinde ya da modelin ürün/ham petrol listesiyle):
  - KEBCO ↔ Kebco (Kazakh Export Blend Crude Oil)
  - Ural (Spot) ↔ Ural
  - Reformate (Export) ↔ Reformate
  - High Sulphur Gasoil 0.1% ↔ High Sulphur Gasoil
  - Product Prices "ULSD (Export)" ↔ Production Plan "ULSD 10 ppm (Export)"
- Diğer girdilerle ilişki: bkz. Açık sorular (Hedge Plan, Budget Calc, haftalık STAR girdi dosyası).

## Forecast'taki rolü
- Planned'da yalnız çalışılan ayın sütunu kullanılır; diğer aylara bakılmaz.
- Buradan gelenler: hacimler (ham petrol, ithal, nihai ürün, utility tüketimi), ham petrol / ithal / ürün fiyatları, Brent, dönüşüm faktörleri, kanal oranları.
- Dönüşüm faktörleri o ay hacim olmasa da kullanılır (stoklar için gerekebilir).
- Kanal oranı dosyada gelmezse aynı mantıkla (kalem / grup toplamı) hesaplanır.
- **Buradan alınmayanlar:**
  - ULSD ve Jet fiyatları: Hedge Plan'dan gelir.
  - Doğalgaz ve elektrik fiyatları: Gas Power Prices dosyasından gelir (aylık baz etiketiyle, ör. `_10_2`).
  - Process Water (HGU): forecast'a girmez (kalıcı istisna).
- Hücre düzeyindeki model eşlemesi bu kartta yok (bkz. KARAR_GUNLUGU "Birleşmede aktarılacaklar").

## Bilinen tuzaklar / temizlik adımları
- Genel girdi kontrol kuralları geçerli (KARAR_GUNLUGU "Girdi kontrol kuralları").
- Ara ürünlerin modele bağlanmaması geçmişte kullanıcı hatası olarak görüldü.
- Product Prices başlığında "(ton/month)" yazıyor, değerler $/ton.
- Ad standarttan farklı gelebilir (ör. `STAR_LP_<Ay>_2026_0_30_Planned` beklenirken bu adla geldi).

## Açık sorular
- **Sıklık:** Haftalık mı? Eski analizde "Ticaret, haftalık" yazıyor ama onaylanmamış.
- **HSGO ve VGO iki bölümde:** Production Plan'da hem Crude Oil bölümünde hem Imports bölümünde var. Ayrı kargolar mı? Aynıysa maliyet iki kez sayılır (eski S8 / A01, cevapsız).
- **Pozitif ara ürünler:** Pozitif gelen ara ürünler (ör. HSGO, Vacuum Residue) forecast'ta nereye gider? Eksik bağlantı olduğu biliniyor, hedefi belli değil.
- **Satır sınıflaması:** Her satır her hafta şu durumlardan birine konur: dolu + hedefi var · dolu + hedefi yok (uyarı) · boş + hedefi var · boş + hedefi yok · yeni satır (sorulur). Grup listesi (Crude Oil, Imports, Utility, Final Products, Intermediate) onay bekliyor (eski M17 / R02a).
- **Dönüşüm faktörü boşlukları:** Modelde boş kalan faktör satırları bu dosyadan doldurulsun mu? (eski M16)
- **Modelde karşılığı olmayan kalemler:** Dosyada olup modelin listesinde olmayan ham petroller (Arab Extra Light, Kuwait, Tengiz, Vasconia) ve ürünler nasıl ele alınır? (eski E07)
- **Forecast'a girmeyen bölümler:** Process Units sayfası, CDU utilization ve özet satırlarının (verimler, toplam NG/su/elektrik ve fiyatları, VOC, GRM) hiç kullanılmadığı gözlendi. Her hafta "girdide var, forecast'ta yok" diye raporlanması onaylıydı (eski M10); bunların bilinçli olarak dışarıda kaldığı teyit edilmeli.
- **Fiyatı olup hacmi olmayan kalemler:** Referans fiyat mı?
- **Ural (Spot):** Assay'i KEBCO ile aynı görünüyor. Bilinçli mi?
- **Budget Calc ile ilişki:** Fiyatlar sabit değer, Budget Calc'tan kopyalanmış görünüyor (Claude gözlemi).
- **Hedge Plan ile ilişki:** Hedge Plan bu dosyaya bağlı görünüyor (Claude gözlemi).
- **Haftalık STAR girdi dosyasıyla ilişki:** `STAR <Ay> 2026 a__p.xlsx` aynı dosyanın haftalık hali mi, ayrı bir dosya mı?

## Tanıtım tarihi
- 10.11.2026 (Akın-Weekly Star'da). Bu repoya devir: 20.11.2026.
