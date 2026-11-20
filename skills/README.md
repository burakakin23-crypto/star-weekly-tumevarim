# STAR tümevarım – Skill kataloğu

Skill, bir işin **sırasını** ya da bir **bakış açısını** tutan dosyadır. Kuralların ve kararların evi `CLAUDE.md` ve `KARAR_GUNLUGU.md`'dir; skill onlara bölüm başlığıyla atıf yapar, metnini kopyalamaz. Dosyalar düz metindir; tek bir araca bağlı değildir. Düzenin kararı: `KARAR_GUNLUGU` "Skill düzeni".

## Hangi işte hangi skill

| İş | Skill | Amaca katkısı |
|---|---|---|
| Bir girdi dosyası geldi: okunur, rolü modelin bağlantılarından doğrulanır, kartı yazılır | `star-girdi-tanitma/SKILL.md` | Yalnız girdilerle sonuç üretebilmek için her girdinin ne olduğu ve nasıl kullanıldığı bilinmeli |
| Model, Results ve girdilerin dış bağlantılarından girdi listesi çıkarılır; durumlar güncellenir | `star-girdi-listesi/SKILL.md` | Hiçbir girdi atlanmasın; karşılaştırma modelin fiilen bağlı olduğu sürümlerle yapılsın |
| Bir turun ya da bir kararın soruları panelde toplanır; cevaplar panelden okunur | `star-soru-paneli/SKILL.md` | Açık konular varsayımla değil, kullanıcının ve STAR ekibinin cevabıyla kapansın |
| Karar verildi ya da değişti; günlüğe işlenir; `star-weekly` koluyla eşlenir | `star-karar-isleme/SKILL.md` | İki kolun kaydı aynı anlamda kalsın |

## Roller (bakış açıları)

Rol skill'i bir işin sırası değil, o işe **hangi gözle bakılacağıdır**. Bir iş skill'i gerektiğinde bir ya da birkaç role geçer. Rol adları `star-weekly` reposundakilerle aynıdır; birleşmede tek dosya olur.

| Rol | Skill | Hangi işte devreye girer | Amaca katkısı |
|---|---|---|---|
| Denetçi | `star-rol-denetci/SKILL.md` | Kart, liste ya da karar yazılmadan önce; Planned model ve Results okunurken | Her bilginin kanıtlı ve onaylı olması |
| Excel model denetçisi | `star-rol-model-denetcisi/SKILL.md` | Girdi dosyası ve model bağlantıları okunurken | Elle değerin, eski bağlantının ve sabit formülün hücresiyle bulunması |
| Muhasebeci | `star-rol-muhasebeci/SKILL.md` | Girdinin Results'ta hangi kaleme gittiği sorgulanırken | Girdinin sonuçtaki yerinin doğru anlaşılması |
| Finansçı | `star-rol-finansci/SKILL.md` | Girdinin etki yolu ve sürüm tutarlılığı sorgulanırken | Girdilerin aynı sürümü anlatması |
| Analist | `star-rol-analist/SKILL.md` | Satır eşleme, birim, boş/dolu sınıflaması, sayım | Verinin eksiksiz ve tutarlı eşlenmesi |
| Rafineri uzmanı | `star-rol-rafineri-uzmani/SKILL.md` | LP, stok, utility, crack girdilerinin makullüğü | Girdinin fiziksel ve ticari olarak makul olması |
| Hedge uzmanı | `star-rol-hedge-uzmani/SKILL.md` | Hedge Plan, Open Trades, Budget Calc ilişkisi | Hedge girdisinin dayandığı işlem ve fiyatın bilinmesi |
| CFO | `star-rol-cfo/SKILL.md` | Önceliklendirme; yeni iş açılırken; bulgunun karara etkisi | İşin amaca ve karara bağlanması |
| Sunumcu | `star-rol-sunumcu/SKILL.md` | Soru paneli, özet ve STAR ekibine giden soru metni | Sorunun ilk okuyuşta anlaşılıp cevaplanması |

**İş → rol eşlemesi.** Girdi tanıtma: Excel model denetçisi ve analist; dosyaya göre rafineri uzmanı ya da hedge uzmanı; rol doğrularken muhasebeci ve finansçı; kart yazılmadan önce denetçi. Girdi listesi: Excel model denetçisi, analist. Soru paneli: sunumcu, CFO. Karar işleme: denetçi; öncelik gerekiyorsa CFO.

## Bekleyenler

Önünde açık karar olan skill yazılmaz, burada bekler.

**İş skill'leri**
- Ara dönem (a+p) girdi tanıtma: Planned bitince başlar; kuralları yeniden sorulacak (`KARAR_GUNLUGU` "Amaç ve yön – netleştirme" – Zamanlama).
- Girdi kontrol koşusu: genel kontrol kurallarının otomatik uygulanması; henüz kod yok (`KARAR_GUNLUGU` "Girdi kontrol kuralları").
- Kolların karşılaştırması: Planned ve ara dönemden sonra; `star-weekly`'de `star-fark-izleme` var, biçimi birleşmede (`KARAR_GUNLUGU` "Açık konular" – Birleşme).

**Roller**
- Vergi uzmanı: kapsam aşama 2 (EBITDA altı).
- Bilanço ve nakit akış uzmanı: kapsam aşama 3.

## Skill nasıl eklenir ve nasıl öğrenir

1. **Yeni skill.** Bir iş ikinci kez aynı sırayla yapılıyorsa ya da sıra unutulunca hata çıkıyorsa skill olur. `skills/<ad>/SKILL.md` açılır (başta `name` ve `description`), bu kataloğa amaca katkısıyla bir satır eklenir. Claude gerek gördüğünde kendiliğinden ekleyebilir; oturum sonunda ne eklediğini kullanıcıya söyler.
2. **Bölümler.** İş skill'i: ne zaman kullanılır; dayandığı kural ve karar (atıf); adımlar; yapma; Öğrenilenler. Rol skill'i: temel soru; neye bakar; kendine sorduğu sorular; çıktısı; sınırı; Öğrenilenler.
3. **Öğrenme.** Bir işte işe yarayan ya da hataya yol açan bir yöntem görülünce ilgili skill'in Öğrenilenler bölümüne tarihli tek satır eklenir: ne görüldü, bundan sonra ne yapılır. Yalnız gerçekten yaşanan yazılır. Satır skill'in adımlarına işlenince silinir (geçmişi git'tedir).
4. **Sınır.** Skill yalnız *nasıl yapılır*ı öğrenir. Kuralı, eşiği, kapsamı ya da kararı değiştiren şey kullanıcıya sorulur ve `KARAR_GUNLUGU.md`'ye işlenir. Açık konu skill'de varsayımla kapatılmaz. Kart ve günlük için "önce göster" kuralı sürer.
5. **Rakam yok.** Skill'e finansal rakam ve dosya içeriği yazılmaz.
6. **Tek ev.** Aynı adım iki skill'de anlatılmaz; biri diğerine işaret eder. Rol kural koymaz; muhasebe ve sektör bilgisi kesin kural gibi yazılmaz, emin olunmayan yerde "teyit edilmeli" denir.
