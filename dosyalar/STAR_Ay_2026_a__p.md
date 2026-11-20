# Haftalık STAR girdi dosyası – STAR <Ay> 2026 a__p

## Dosya adı ve sürümü/dönemi
- İncelenen ad kalıbı: `STAR <Ay> 2026 <a>__<p>.xlsx` (ör. `STAR Oct 2026 16__15`). Bazı haftalarda sonraki ayın dosyası da gelir (ör. `STAR Nov 2026 0__30`).
- İlk incelenen sürümler: Ekim 2026, 9+22 ve 16+15 haftaları.

## Kaynak
- Teyitsiz (bkz. Açık sorular).

## Sıklık
- Teyitsiz (bkz. Açık sorular).

## Yapı
- Teyitli yapı bilgisi yok. Eski analizdeki gözlemler Açık sorular'da.

## Anahtar alanlar ve diğer dosyalarla eşleşmesi
- Teyitli bilgi yok (bkz. Açık sorular).

## Forecast'taki rolü
- Teyitli bilgi yok. Hücre düzeyindeki model eşlemesi bu kartta yok (bkz. KARAR_GUNLUGU "Birleşmede aktarılacaklar").

## Bilinen tuzaklar / temizlik adımları
- Teyitli bilgi yok (bkz. Açık sorular).

## Açık sorular
- **LP model ile ilişki:** Bu dosya Planned LP model (`STAR Budget (2026) - Forecast`) ile aynı dosyanın haftalık hali mi, ayrı bir dosya mı? Kim hazırlıyor? Haftalık mı geliyor?
- **Ad kalıbı (Claude gözlemi, onaysız):** `a+p` = ayın gerçekleşen gün sayısı + plan gün sayısı (ör. `16 15` → 1–16 gerçekleşen, 17–31 plan; `0 30` → ay tamamen plan).
- **Yapı (Claude gözlemi, onaysız):**
  - **Production Plan:** D = gerçekleşen, E = plan; ham petrol alımları, ithalat, utility tüketimleri, nihai ürünler, ara ürünler, kayıp %, HVP verimi.
  - **Process Units:** ünite kapasite ve kullanımı.
  - **Crude & Import Prices:** stok etkili ve stoksuz fiyat sütunları ($/bbl), assay, yoğunluk, dönüşüm faktörü (bbl/t).
  - **Product Prices:** ürün fiyatları ($/t).
- **Elle eklenen yardımcı sütunlar:** Production Plan'da toplam, kanal payı ve hacim ağırlıklı fiyat sütunları elle eklenmiş; sonraki ay dosyasında bir sütuna önceki haftanın değeri yapıştırılmış. Model bu sütunlara bağlı. Her hafta var olup doğru haftayı gösterdikleri kontrol edilmeli mi? (eski B10, onaysız)
- **Elle yazılmış plan değeri:** VGO plan değeri ay toplamını sabitleyen elle yazılmış bir formülle girilmiş. STAR planlamaya sorulacak (eski B15, onaysız).
- **Gerçekleşen = plan:** Bir haftada C5 (Petkim) ve Rafinat (Petkim) satırlarında gerçekleşen ve plan sütunları aynı; ay toplamı iki katına çıkmış görünüyor. Kopyalama hatası mı? Yüksek öncelikli, STAR planlamaya sorulacak (eski B18, onaysız).
- **Aynı dosyaya iki kopya:** Bir haftada model aynı adlı girdinin iki farklı konumdaki kopyasına bağlıydı; fiyat eski kopyadan geliyordu (eski B19). Bu artık genel kural (KARAR_GUNLUGU "Girdi kontrol kuralları"); bu dosyada tekrar edip etmediği teyit edilmeli.

## Tanıtım tarihi
- **Tanıtılmadı.** Kart, Akın-Weekly Star'ın 07.11.2026'daki ilk incelemesindeki gözlemlerden açıldı (kullanıcı onayı yok). Bu repoya devir: 20.11.2026. Dosya gelince tanıtım rutini uygulanır.
