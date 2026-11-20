# Hedge Plan

## Dosya adı ve sürümü/dönemi
- Standart ad: `Hedge_Plan_2026_0_30 Forecast_<Ay> Planned` (dönem etiketi + ay + Planned).
- Dosya adından değil içeriğinden tanınır; ad farklı gelirse durulmaz, uyarılır.
- İlk incelenen sürüm: Kasım 2026 Planned.

## Kaynak
- Finans ekibinin kendi sürecinden geçer (ULSD/Jet hedge hesabı ve Summary). İç süreç adımı olarak ele alınır.

## Sıklık
- Teyitsiz (bkz. Açık sorular).

## Yapı
- Teyitli yapı bilgisi yok. Eski analizdeki gözlemler Açık sorular'da.

## Anahtar alanlar ve diğer dosyalarla eşleşmesi
- Teyitli bilgi yok (bkz. Açık sorular).

## Forecast'taki rolü
- ULSD ve Jet fiyatlarının kaynağı. Bu fiyatlar LP model'den alınmaz.
- Hücre düzeyindeki model eşlemesi ve hedge hesabı bu kartta yok (bkz. KARAR_GUNLUGU "Birleşmede aktarılacaklar").

## Bilinen tuzaklar / temizlik adımları
- Ad standarttan farklı gelebilir (ör. dönem etiketi farklı yazılmış); içerikten tanınır, uyarılır.

## Açık sorular
- **Sıklık:** Haftalık mı? Eski analizde "finans süreci, haftalık" yazıyor ama onaylanmamış.
- **Yapı (Claude gözlemi, onaysız):** `ULSD_Hedge Calculation` ve `Jet_Hedge Calculation` sayfaları (ağırlıklı fiyat kanal başına bir satırda); `Summary` sayfası (ULSD/Jet crack hedge, crude roll + inventory hedge, product hedge, fuel oil roll; önceki versiyon ve fark sütunları); tarihli işlem sayfaları (gizli olanlar eski versiyonlar).
- **Hangi tarihli işlem sayfası esas?** En güncel sayfa mı, analistin seçtiği mi? Öneri: en güncel sayfa alınır, farklıysa uyarılır (eski H2, cevapsız).
- **Summary'deki crude roll + inventory hedge hangi işlemleri kapsıyor?** Yeni işlem eklenince aralık otomatik genişlesin mi? Dosyadaki "roll işlemleri Brent fiyatında zaten olabilir, double olmasın" notu kapandı mı? (eski H3, cevapsız)
- **Hacimler modelden okunuyor:** ULSD/Jet hacimleri ana modelden okunuyor, model de fiyatı bu dosyadan alıyor (döngü). Model gelmezse hacimler LP model'den alınsın mı? (eski H5, cevapsız)
- **Forecast crack'in kaynağı:** "STAR EBITDA Crack Margin Effect" dosyası olarak görünüyor; o dosya gelmedi. Her hafta gelecek mi, kim hazırlıyor? (eski H1, "sonra sor")
- **Budget Calc ile ilişki:** Bu dosya Budget Calc'tan yalnız CIF-FOB farkını alıyor görünüyor (Claude gözlemi).
- **Önceki versiyonla karşılaştırma:** Summary'deki önceki versiyon / fark sütunları beklenen çıktının parçası mı? Planned'da referans "0+30" mı, aylık baz mı? (eski H8, yorumsuz "Farklı düşünüyorum")
- **Hacim 0 olan kanal:** Ağırlıklı fiyat hücresi `#DIV/0!` veriyor (ör. ULSD Export). Uyarı mı sayılır? (eski H6 içinde, cevapsız)

## Tanıtım tarihi
- 11.11.2026 (Akın-Weekly Star'da). Bu repoya devir: 20.11.2026.
