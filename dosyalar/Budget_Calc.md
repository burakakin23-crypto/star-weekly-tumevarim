# 2026 Budget Calc

## Dosya adı ve sürümü/dönemi
- İncelenen ad: `2026 Budget Calc_<gg.aa.yyyy>.xlsx`. Aylık baza (ör. 10+2) bağlı görünüyor; teyitsiz.

## Kaynak
- Teyitsiz (bkz. Açık sorular).

## Sıklık
- Teyitsiz (bkz. Açık sorular).

## Yapı
- Teyitli yapı bilgisi yok. Eski analizdeki gözlemler Açık sorular'da.

## Anahtar alanlar ve diğer dosyalarla eşleşmesi
- Teyitli bilgi yok (bkz. Açık sorular).

## Forecast'taki rolü
- Teyitli bilgi yok. Kullanıcı rolün Hedge Plan üzerinden kontrol edilmesini istedi ("hedge dosyasını kontrol edersin, sorun olursa tekrar sor"; eski M14).

## Bilinen tuzaklar / temizlik adımları
- Teyitli bilgi yok (bkz. Açık sorular).

## Açık sorular
- **Kaynak ve sıklık:** Kim hazırlıyor? Aylık baz değişince mi yenisi geliyor? (eski G03, cevapsız)
- **Yapı (Claude gözlemi, onaysız):**
  - **SOCAR 2026** sayfası: fiyat destesi. Brent birkaç kaynağın ortalaması (JBC, Pira, son kotasyonlar); ürün CIF/FOB fiyatları kaynak ortalaması; crack'ler.
  - **STAR 2026** sayfası: aylık ULSD ve Jet crack'leri, ürün fiyatları ($/MT), baz fiyat ve prim tablosu.
- **LP model ile ilişki:** Bu dosyadaki ürün fiyatları LP model'deki satış fiyatlarıyla aynı görünüyor. LP fiyatları buradan mı kopyalanıyor?
- **Modelden okuma:** Dosya ana modelden hacim okuyor; önbellekteki hacimler modelin güncel hacimlerinden farklıydı. Dosya model güncellemesinden önce mi kaydediliyor? Bu hacimler bir şeyi etkiliyor mu?
- **Hedge Plan ile ilişki:** Hedge Plan bu dosyadan yalnız CIF-FOB farkını alıyor görünüyor; buradaki crack Planned hedge'inde kullanılmıyor.
- **Results ile ilişki:** Financial Results'taki "Crack Margin" sayfaları bu dosyaya bağlı görünüyor.

## Tanıtım tarihi
- 10.11.2026 (Akın-Weekly Star'da, kısmen). Bu repoya devir: 20.11.2026.
