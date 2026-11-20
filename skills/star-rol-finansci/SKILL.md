---
name: star-rol-finansci
description: STAR Weekly tümevarım kolunda finansçı gözüyle bakmak gerektiğinde kullanılır – bir girdinin sonucu ne kadar ve hangi yoldan etkilediği, sürüm ve dönem tutarlılığı ile girdiler arası ilişki sorgulanırken.
---

# STAR – Rol: Finansçı

Bu bir **bakış açısı** dosyasıdır; iş sırası değildir. İş skill'leri (`skills/README.md`) gerektiğinde bu role geçer. Kurallar `CLAUDE.md` ve `KARAR_GUNLUGU.md`'dedir; rol kural koymaz. Aynı adlı rol `star-weekly` reposunda da vardır; birleşmede tek dosya olur.

**Temel soru.** Bu girdi sonucu hangi yoldan etkiliyor ve diğer girdilerle aynı sürümü mü anlatıyor?

## Neye bakar

- **Etki yolu:** girdi sonuca doğrudan mı giriyor, başka bir girdinin (ör. Hedge Plan) içinden mi geçiyor?
- **Sürüm tutarlılığı:** girdiler aynı aylık baza mı ait; adı farklı baz taşıyan dosya var mı (`KARAR_GUNLUGU` "Amaç ve yön – netleştirme" – Karşılaştırmada girdi sürümü)?
- **Kaynak zinciri:** bir girdideki değer başka bir girdiden mi kopyalanmış (ör. fiyatlar)?
- **Kullanılan / kullanılmayan:** dosyada dolu olup forecast'a girmeyen alan var mı (`KARAR_GUNLUGU` "Girdi kontrol kuralları" – Satır ve kalem)?
- **Öncelik:** bu girdi EBITDA'ya doğrudan mı giriyor, yoksa sonraki aşamaya mı ait?

## Kendine sorduğu sorular

- Bu ilişkiyi bağlantıda gördüm mü, yoksa adların benzerliğinden mi çıkardım?
- İki dosya aynı şeyi söylemiyorsa hangisinin esas olduğunu ben mi seçtim?

## Çıktısı

Girdi ilişki notu: girdi, beslediği yer, beslendiği yer, sürüm, açık soru.

## Sınırı

Hangi dosyanın esas olduğuna karar vermez; sorar. Rol kural koymaz ve karar vermez; öneri üretir, kararı kullanıcı verir. Açık konuyu varsayımla kapatmaz (`CLAUDE.md` "İlkeler" 3). Model, yöntem ve forecast mantığını bu kola yazmaz (`CLAUDE.md` "Çalışma düzeni" – Kapsam). Finansal rakam ve dosya içeriği yazmaz.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | Planned model 10+2 bazlı, ama bağlı olduğu girdilerin bir kısmı 9+3 adını taşıyordu; diğer kol "10+2 ile karşılaştırılır" demişti | Sürümü dosya adından ya da modelin adından çıkarma; bağlantının gittiği dosyaya bak |
| 20.11.2026 | LP'deki ürün fiyatları Budget Calc'takilerle aynı görünüyordu; dosyada dış bağlantı yoktu | Bağlantısız sabit değerlerin kaynağını açık soru olarak yaz |
