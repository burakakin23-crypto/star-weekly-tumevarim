# Karar Günlüğü

Yürürlükteki kurallar ve açık konular. Eski kural silinmez; değiştiğinde altına "yerine geçer: <tarih> <yeni kural>" yazılır.

## Yürürlükteki kararlar

### Kurulum (20.11.2026)
- Bu repo (`star-weekly-tumevarim`) STAR haftalık forecast'ının tümevarım koludur: girdi dosyaları tek tek tanıtılır. Tümden gelim kolu `star-weekly` reposudur.
- Detaylar GitHub'da (`star-weekly-tumevarim` reposu); claude.ai Project talimatı yalnızca repoya işaret eder.
- Oturum rutini ve dosya tanıtım rutini repodaki `CLAUDE.md`'de tutulur; ayrı bir skill yok.
- İlkeler: tek ev / kopya yok; dallanma ve versiyon yok.
- Git: doğrudan `main`.
- Bağımsızlık: `star-weekly` dışındaki projelerden (ör. OPEX) kural, eşik ya da yöntem taşınmaz; `star-weekly`'den de bir şey ancak kullanıcı açıkça isterse alınır.
- Dosya tanımları `dosyalar/<dosya_adı>.md` altında, dosya başına tek kart olarak tutulur. Kart biçiminin tek evi `CLAUDE.md`; ayrı şablon dosyası yok.
- Kartlara gerçek rakam ya da şirket verisi yazılmaz; yalnızca yapı ve anlam.
- Veri: sabit referans bilgiler Project dosya alanında; tanıtılan dosyalar ve haftalık veri sohbete eklenir; şirket verisi repoya girmez.
- Açık kararlar sohbette soru-cevap ile verilir; kullanıcının cevaplamadığı hiçbir şey kabul sayılmaz.
- Devir kayıtları (başka hesaptaki eski STAR çalışması): ham hali repoya konmaz. Kurallar ve kararlar → bu günlük; dosya tanımları → ilgili dosya kartı; model/yöntem/forecast mantığı → "Birleşmede aktarılacaklar" listesi; şirket verisi → hiçbir yere. Çelişen, eskimiş görünen ya da iki yere ait olabilecek her şey yazılmadan önce kullanıcıya sorulur.
- Birleşme uyumu: dosya adları, başlıklar ve tarih biçimi (GG.AA.YYYY) `star-weekly` ile aynı tutulur.

## Açık konular

- **Birleşme (20.11.2026):** Bu kol `star-weekly` ile birleşecek; biçimi o gün kararlaştırılır.
- **Birleşmede aktarılacaklar (20.11.2026):** Yöntem/model/forecast mantığına ait olup bu kola ait olmayan bilgiler burada listelenir.
  - (henüz yok)
