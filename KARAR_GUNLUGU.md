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
  - *Kaynak: Akın-Weekly Star devir paketi (20.11.2026; kayıtların son hali 11.11.2026). Ayrıntı pakette; buraya yalnız başlık yazıldı.*
  - **Engine hedefi:** Nihai hedefte yalnız girdiler verilir; ana model (.xlsb) ve Financial Results verilmez, aynı sonuç bağımsız engine ile üretilir. Öğrenme aşamasında model ve Results yalnız doğrulama referansıdır (eski K16; eski K05 "model gerçeğin kaynağı"nın yerine geçmiş). Production girdi paketinde modelin olup olmayacağı (D-02) cevapsız.
  - **Eski motor:** Excel modelinin Python kopyası; kodu kayıp, yöntemi eski MODEL_REHBERI'de belgeli.
  - **Model yapısı:** sayfa düzeni, ay türüne göre veri kaynağı, Results'taki model dışı etkiler, KPI tanımları (GRM, Net Cash Margin, Clean GRM), elle müdahale ve haftalık yeniden bağlama haritası.
  - **Reconciliation:** L0–L4 katmanları ve tolerans varsayımı (eski A07).
  - **Hedef çıktı:** model EBITDA'sı mı, Results EBITDA'sı mı (D-01, cevapsız). Haftalık stok kanal payı yöntemi (D-03, cevapsız).
  - **Çıktı biçimi:** dashboard (ana ekran + kontrol paneli), crack/fiyat senaryo kolları, girdi grubu bazında haftalık köprü (eski K02, K06, K07, K09).
  - **Sunum kuralları:** renk yönü, n.m. yüzde formülü, ay geçişinde kolon kaydırma kontrolü, şekil ve tanımlı ad kuralları; `weekly-sunum-kontrol` ve `denetci` skill'leri.
  - **Ajan ekibi ve döngü:** `star-weekly-orkestra` skill'i.
  - **STAR ekibine sorulacak model/Results soruları:** Net Refinery Margin tanımı, hedge roll çift sayımı, model Checks hataları, Results'taki sabit sayılar, sunumdaki FY EBITDA'nın aylık baza bağlı olması.
