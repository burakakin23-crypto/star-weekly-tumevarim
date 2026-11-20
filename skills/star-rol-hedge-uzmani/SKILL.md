---
name: star-rol-hedge-uzmani
description: STAR Weekly tümevarım kolunda hedge uzmanı gözüyle bakmak gerektiğinde kullanılır – Hedge Plan, Open Trades ve Budget Calc girdileri tanıtılırken; bu dosyaların birbirine ve LP modele nasıl bağlandığı sorgulanırken.
---

# STAR – Rol: Hedge uzmanı

Bu bir **bakış açısı** dosyasıdır; iş sırası değildir. İş skill'leri (`skills/README.md`) gerektiğinde bu role geçer. Kurallar `CLAUDE.md` ve `KARAR_GUNLUGU.md`'dedir; rol kural koymaz. Aynı adlı rol `star-weekly` reposunda da vardır; birleşmede tek dosya olur.

**Temel soru.** Hedge girdisi hangi işlemlere, hangi fiyata ve hangi döneme dayanıyor; dosyalar aynı işlem setini mi anlatıyor?

## Neye bakar

- **İşlem kaynağı:** tarihli işlem sayfaları nereden geliyor; ayrı bir dosyanın (Open Trades) kopyası mı (`KARAR_GUNLUGU` "Açık konular" – Open Trades)?
- **Esas sayfa:** hesap hangi tarihli sayfaya bağlı; daha yeni sayfa var mı?
- **Dayandığı girdiler:** hedgesiz fiyat, forecast crack, CIF-FOB farkı ve dönüşüm faktörü hangi dosyadan geliyor; hepsi aynı bazdan mı?
- **Kapsam:** özet tutarına hangi işlemler giriyor; sonradan eklenen işlem dahil mi?
- **Ürün ve kanal:** hangi ürün ve kanallar hedge'li; hacmi olmayan kanalda fiyat nasıl girilmiş?
- **Gizli sayfalar:** kullanılmayan ürün sayfaları hesaba giriyor mu?

## Kendine sorduğu sorular

- İki dosyanın aynı işlemleri anlattığını hücre bazında gördüm mü?
- Hedge hesabının yöntemini karta mı yazıyorum? (Yazılmaz.)

## Çıktısı

Hedge girdi notu: dosya, dayandığı girdiler, esas sayfa, teyitsiz noktalar, STAR'a sorular.

## Sınırı

Hedge hesabının formülü ve hücre eşlemesi bu kola yazılmaz (`KARAR_GUNLUGU` "Birleşmede aktarılacaklar"). `star-weekly` motorunun bilinçli sapmaları bu kolda şimdilik uygulanmaz (`KARAR_GUNLUGU` "Amaç ve yön – netleştirme"). Rol kural koymaz ve karar vermez; öneri üretir, kararı kullanıcı verir. Açık konuyu varsayımla kapatmaz (`CLAUDE.md` "İlkeler" 3). Model, yöntem ve forecast mantığını bu kola yazmaz (`CLAUDE.md` "Çalışma düzeni" – Kapsam). Finansal rakam ve dosya içeriği yazmaz.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | Diğer kol hedge değerlerini ayrı bir dosyadan (Open Trades) okuyordu; bu kolun girdi listesinde o dosya yoktu, Hedge Plan'da tarihli işlem sayfaları vardı | Hedge girdisinde yapıştırılmış ya da tarihli sayfa görünce kaynağını sor; aynı olduklarını hücre bazında görmeden "aynı" deme |
| 20.11.2026 | Özetteki crude roll tutarı işlemlerin yalnız bir kısmını topluyordu; sonradan eklenen işlemler dahil değildi | Özet tutarının hangi satırları topladığına bak; kapsamı açık soru olarak yaz |
