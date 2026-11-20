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

### Kapsam (20.11.2026)
- Şu an Planned (0+30) girdileri tanıtılıyor.

### Devir 1 – Akın-Weekly Star (20.11.2026)
- Eski projenin `ortak-forecast-metodolojisi` skill'i (güven etiketleri, onay panosu, ayrı kural/varsayım/istisna günlükleri; PETKİM ile ortak) bu kola alınmaz. Bu reponun yapısı geçerlidir.
- Devirden gelen bilgi kartın başlıklarına yalnız kullanıcı onaylıysa yazılır; onaysız her şey kartın "Açık sorular" bölümüne gider. Onaylı sayılanlar: eski karar günlüğünde kullanıcının bildirdiği kararlar ve eski onay panosunda kullanıcının yorumuyla teyit ettiği kartlar. "Sonra sor", cevapsız ya da yorumu işaretiyle çelişen kartlar onaysızdır.
- Girdi dosyasından modele hücre düzeyindeki eşleme kartlara yazılmaz. Kartta yalnız rolün özeti ve hangi alanın kullanılıp hangisinin kullanılmadığı yazılır; hücre eşlemesi "Birleşmede aktarılacaklar"a gider.
- Tüm girdilere uyan eski kontrol kuralları kullanıcıya tek tek sorulur; onaylananlar bu günlüğe yazılır.
- Haftalık STAR girdi dosyası (`STAR <Ay> 2026 a__p.xlsx`) ile Planned LP model (`STAR Budget (2026) - Forecast (gg.aa.yyyy)`) iki ayrı karttır.
- Akın-Weekly Star bu kolun (tümevarım) eski çalışmasıdır; orada 3 girdi tanıtıldı: LP model, Hedge Plan, Budget Calc. Haftalık STAR girdi dosyasının kartı tanıtılmamış dosya olarak durur; dosya gelince tanıtılır.
- "STAR Weekly Forecast Automation" projesi tümden gelim koludur; onun bilgisi bu repoya değil `star-weekly`'ye gider. Bu kolun devri Akın-Weekly Star paketiyle tamamlandı.

### Girdi kontrol kuralları (20.11.2026)
Tüm girdi dosyalarına uyar. Akın-Weekly Star'da onaylanan kuralların genelleştirilmiş hali; kullanıcı tek tek onayladı.

**Tanıma ve dönem**
- Dosya adından değil içeriğinden tanınır; ad standarttan farklıysa durulmaz, uyarılır (eski R09).
- Aynı adlı girdinin iki farklı kopyası/konumu kullanılıyorsa hata sayılır (eski R16).
- Dosyaların hepsi aynı versiyona (Planned / a+p haftası) ait değilse önce bu söylenir.
- Yüklenen dosya değiştirilmez, kopyasında çalışılır. Düzeltmeyi kullanıcı yapar; Claude hücre bazında söyler.

**Satır ve kalem**
- Tüm satırlar, boş olanlar dahil, gruplu takip edilir; veri sonradan gelebilir (eski R02).
- Satırlar ada göre eşlenir; veri gelince otomatik kullanılır, karşılığı yoksa uyarı verilir (eski R08).
- Yeni kalem kullanıcıya sorulmadan eklenmez (eski R15).
- Girdide dolu olup forecast'a girmeyen her kalem için uyarı verilir (eski R05).

**Değer kontrolü**
- Fiyatı olup hacmi olmayan kalem uyarıdır, hata sayılmaz (eski R13).
- Birim uyuşmazlığında sessiz dönüşüm yapılmaz, uyarı verilir (eski R14).
- Elle yazılmış değer ya da başka ayın dosyasına giden bağlantı görülürse uyarılır (eski R07).
- Her rakam dosya + sayfa + hücreye izlenebilir olmalı; kaynakta olmayan rakam üretilmez.

## Açık konular

- **Birleşme (20.11.2026):** Bu kol `star-weekly` ile birleşecek; biçimi o gün kararlaştırılır.
- **Girdi teslim günü (20.11.2026):** Eski kayıtlar çelişiyor: "departmanlar salı gönderir" (eski K13), "cuma girdi, pazartesi sunum" (eski K08 ve hafıza), "cuma veri istenir, salı girdiler gelir" (eski karşılaştırma sohbeti, onaysız). İlk girdi dosyası tanıtılırken netleşecek.
- **Production girdi paketinde ana model ve Results olacak mı (eski D-02, 20.11.2026):** Seçenekler: aylık model ayda bir girdi olarak gelir · yalnız girdiler gelir · geçiş (şimdilik aylık model, nihai hedef yalnız girdiler). Bu kolun girdi listesini belirler.
- **Mevcut kanıtla çözülen 13 maddenin toplu onayı (eski D-05, 20.11.2026):** Maddelerin ayrıntısı eski "Proje bilgi karşılaştırması" sohbetinde ve devir paketinde olmayan `PROJECT_KNOWLEDGE_EXPORT_Akin_Weekly_Star.md` dosyasında. Dosya gelince ele alınacak.
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
  - **Ortak forecast metodolojisi v1.0:** güven modeli, mapping standardı, onay panosu, kayıt sistemi; PETKİM ile ortak. Bu kola alınmadı; tümden gelim kolunda kullanılıp kullanılmayacağı birleşmede kararlaştırılır.
  - **Girdi → model hücre eşlemesi:** eski SUREC_MAPPING_0_30 §1–§14 (LP ve Hedge Plan'ın model hücrelerine akışı) ve negatif ara ürünün ithal satırına pozitif hacim olarak gitmesi (eski R11). Hangi alanın kullanılıp hangisinin kullanılmadığına dair eski R01, R03, R04, R10, R12 kuralları ilgili dosya kartlarında.
  - **Hedge hesabı:** hedge'li tonajın fiyatı, ağırlıklı fiyat ve hedge etkisi formülü (eski H6, onaysız); model ile Results'ın aynı hedge fiyatını görüp görmediği ve "aynı sonuç" referansı (eski H4 / A06, onaysız).
