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
  - yerine geçer: 20.11.2026 – başlıklar ve tarih biçimi aynı tutulur; karar dosyası birleşmeye kadar `KARAR_GUNLUGU.md` kalır, birleşmede içerik `star-weekly`'nin `00_MASTER/04_KARARLAR.md` yapısına taşınır.

### Anayasa ve çalışma kuralları (20.11.2026)
- **Anayasa:** Açıkta kalan konular Claude'un varsayımıyla kapatılmaz; öneri olarak da olsa mutlaka kullanıcıya sorulur. `CLAUDE.md`'ye 3. ilke olarak eklendi.
- **Çıktıların kullanımı:** Sonuç girdilerden üretilir; ana model ve Financial Results gibi çıktılardan değer alınarak sonuç üretilmez. Çıktılar yalnız öğrenmek için kullanılır ve denetçi gözüyle eleştirilir; içlerinde insan hatası olabilir. Çıktıda görülen her şüpheli nokta bulgu olarak kullanıcıya sorulur.
  - yerine geçer: 20.11.2026 – "ana model ve Financial Results" = Planned model ve Planned Results. Aylık model (n+m) ve aylık Results girdidir; bkz. "Amaç ve yön – netleştirme".
- **Eşzamanlı çalışma:** Proje paylaşıldı; aynı anda iki kişi çalışabilir. Repoda çakışmayı önleyen kurallar `CLAUDE.md` "Çalışma düzeni"nde.

### Tanıtım turu (20.11.2026)
- Devirden gelen kartlar ve açık sorular veriyle baştan kesinleştirilir. Tanıtılmış 3 girdinin (LP model, Hedge Plan, Budget Calc) kartları dosyayla doğrulanır: yazılı her şey ve açık sorular yeniden sorulur, onaylanan kalır, reddedilen düzeltilir.
- Dönem: Kasım 2026 Planned (0+30). Turdaki bütün girdiler bu dönemden olur.
- Ana model ve Financial Results ilk girdiyle bir kez gelir; yalnız girdinin rolünü doğrulamak için kullanılır. Hücre eşlemesi yine "Birleşmede aktarılacaklar"a gider.
  - yerine geçer: 20.11.2026 – burada kastedilen Planned model ve Planned Results; aylık model ve aylık Results girdi olarak ayrıca ele alınır.
- Sıra: LP model → Hedge Plan → Budget Calc → STAR EBITDA Crack Margin Effect.
- "(STAR)" işaretli açık sorular STAR ekibiyle birlikte cevaplanır.
- Girdiler turlar halinde toplu tanıtılır; her turun soruları bir panelde toplanır ve bir sonraki toplantıda STAR ekibiyle cevaplanır.
- Tur 1 paneli (LP model, Hedge Plan; 35 soru): https://claude.ai/artifact/7xovmnq3pPtxe7dxbB8Wm5
- Tur 2 sırası: Budget Calc → Crack Margin Effect → Gas Power Prices → 3_Stoklar → Inventory Effect.

### Kapsam (20.11.2026)
- Şu an Planned (0+30) girdileri tanıtılıyor.
- Nihai hedef: girdiler verilir, çıktı üretilir. Süreç 1–2 ay sürer: girdiler tek tek tanıtılır, açık sorular STAR ekibiyle cevaplanır, tümden gelim kolu (`star-weekly`) ile birleşilir.

### Amaç ve yön (20.11.2026)
- **Nihai amaç:** Yalnız girdiler verilir, ana modelin ürettiği çıktı elde edilir. Ana model ve Financial Results o aşamada verilmez.
  - yerine geçer: 20.11.2026 – verilmeyen Planned model ve Planned Results'tır; aylık model ve aylık Results girdidir; bkz. "Amaç ve yön – netleştirme".
- **İki kol:** Tümevarım (bu repo) girdileri tek tek tanıtır. Tümden gelim (`star-weekly`) ana modeli verip Claude'a tanıtır ve modelden sonuca gider.
- **Karşılaştırma:** İki kolun çıktıları karşılaştırılır, ardından kollar birleşir.
  - **Ne karşılaştırılır:** Ana modelin ve Financial Results'ın çıktılarının tamamı. Hedef birebir aynı sonuç.
    - yerine geçer: 20.11.2026 – çıktıların tamamı hedeftir, kapsam üç aşamada açılır; bkz. "Amaç ve yön – netleştirme".
  - **Ölçüm ve tolerans:** Her çıktı kalemi tek tek karşılaştırılır. Fark %1'in altındaysa ve yuvarlamadan geliyorsa kabul edilir. Formülden gelen fark %1'in altında olsa da bildirilir.
    - yerine geçer: 20.11.2026 – yuvarlama farkı ±1 USD içinde kabul edilir, %1 yalnız rapor eşiğidir; bkz. "Amaç ve yön – netleştirme".
  - **Formül hatası:** Fark modeldeki bir hatadan geliyorsa hatanın kendisi tespit edilir ve kullanıcıya uyarı olarak bildirilir (dosya, sayfa, hücre). Model "doğru cevap" sayılmaz; denetçi gözüyle okunur.
  - **Zamanlama:** Planned (0+30) girdileri bitince ara dönem (a+p) girdileri tanıtılır, karşılaştırma ondan sonra yapılır.
- **Pusula:** Her çalışma bu amaca hizmet etmeli. Amaca katkısı olmayan iş açılmaz.
  - yerine geçer: 20.11.2026 – yeni iş açılırken amaca katkısı yazılır; amaca katkısı olmayan iş açılmaz; park işlere şimdi dokunulmaz.
- **Dönemler:** Planned'da kurulan kurallar ara döneme otomatik taşınmaz; her biri ara dönem dosyası tanıtılırken yeniden sorulur.

### Amaç ve yön – netleştirme (20.11.2026)
`star-weekly` ile aynı anlamda kaydedildi (orada `00_MASTER/04_KARARLAR.md`, M-20–M-28). Cevaplar soru panelinden: https://claude.ai/artifact/JrKHszWGkLTVa6KAnD2xyp
- **Girdi/çıktı ayrımı:** Planned model ve onun Financial Results'ı çıktıdır (hedef); girdi olarak kullanılmaz, nihai aşamada verilmez. Aylık Financial Model (n+m) ve aylık Financial Results girdidir; yalnız gereken alınır.
- **Esas sonuç ve hedef:** Esas sonuç bizim hesabımızdır. Planned model ve Planned Results karşılaştırma hedefidir; çıktılarının tamamı kalem kalem karşılaştırılır, hedef birebir. Fark çıkarsa (biz–model, biz–Results, model–Results, kayıtlı değer–yeniden hesap) kaynak hücreye kadar izlenir, bulgu olarak raporlanır ve kullanıcıya sorulur; hangisinin doğru olduğuna sessizce karar verilmez.
- **Hedef değer:** Formüllerle yeniden hesaplanmış değerdir. Kayıtlı değer ile yeniden hesap arasındaki fark ayrıca bulgudur.
- **Kapsam aşamalı:** (1) cari ay P&L, EBITDA'ya kadar; (2) EBITDA altı; (3) bilanço ve nakit akış.
- **Tolerans:** Yuvarlamadan gelen fark ±1 USD içinde kabul edilir. %1 yalnız rapor eşiğidir: %1'i aşan kalem ayrıca işaretlenir, ama ±1 USD içindeyse kabul edilir. Formülden gelen fark eşiğin altında da bildirilir ve açık kalır. Modelden gelen fark dosya/sayfa/hücre ile uyarı olur; model doğru cevap sayılmaz.
- **`star-weekly` motorunun bilinçli sapmaları** (ULSD/Jet hedge fiyatı ham dosyalardan, CAPEX Capex Input'tan, açılış stoğu koşu ayından bir önceki ayın kapanışından) bu kolda şimdilik uygulanmaz. Girdiler modelin kullandığı şekliyle tanıtılır; sapmalar kolların karşılaştırmasında bulgu olarak görülür.
- **Zamanlama:** `star-weekly` önce Planned (0+30) backtesting'ini, sonra ara dönemi (a+p) yapar; bu kol önce Planned, sonra ara dönem girdilerini tanıtır; kolların karşılaştırması ondan sonra. Planned kuralları ara döneme otomatik taşınmaz.
- **Karar dosyası:** Birleşmeye kadar `KARAR_GUNLUGU.md`; birleşmede içerik `star-weekly`'nin `00_MASTER/04_KARARLAR.md` yapısına taşınır.
- **Pusula:** Yeni iş açılırken amaca katkısı yazılır; amaca katkısı olmayan iş açılmaz; park işlere şimdi dokunulmaz.

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
- Hacmi olup fiyatı olmayan kalem hatadır; fiyat kaynağı kullanıcıya sorulmadan devam edilmez.
- Birim uyuşmazlığında sessiz dönüşüm yapılmaz, uyarı verilir (eski R14).
- Elle yazılmış değer ya da başka ayın dosyasına giden bağlantı görülürse uyarılır (eski R07).
- Her rakam dosya + sayfa + hücreye izlenebilir olmalı; kaynakta olmayan rakam üretilmez.

## Açık konular

- **Birleşme (20.11.2026):** Bu kol `star-weekly` ile birleşecek; biçimi o gün kararlaştırılır.
  - yerine geçer: 20.11.2026 – birleşmenin yeri de biçimi de açık.
- **Girdi teslim günü (20.11.2026):** Eski kayıtlar çelişiyor: "departmanlar salı gönderir" (eski K13), "cuma girdi, pazartesi sunum" (eski K08 ve hafıza), "cuma veri istenir, salı girdiler gelir" (eski karşılaştırma sohbeti, onaysız). İlk girdi dosyası tanıtılırken netleşecek.
- **Production girdi paketinde ana model ve Results olacak mı (eski D-02, 20.11.2026):** Seçenekler: aylık model ayda bir girdi olarak gelir · yalnız girdiler gelir · geçiş (şimdilik aylık model, nihai hedef yalnız girdiler). Bu kolun girdi listesini belirler.
  - kısmen kapandı: 20.11.2026 – aylık model ve aylık Results girdidir; Planned model ve Planned Results verilmez. Açık kalan: aylık Results'tan ne alınacağı (aşağıda).
- **Mevcut kanıtla çözülen 13 maddenin toplu onayı (eski D-05, 20.11.2026):** Maddelerin ayrıntısı eski "Proje bilgi karşılaştırması" sohbetinde ve devir paketinde olmayan `PROJECT_KNOWLEDGE_EXPORT_Akin_Weekly_Star.md` dosyasında. Dosya gelince ele alınacak.
- **Aylık Results'tan ne alınacağı (20.11.2026):** Aylık Financial Results girdi sayılıyor; içinden hangi değerlerin alınacağı belli değil. İlk Planned karşılaştırmasından sonra ele alınır.
- **Sıfıra yakın kalem ve mutlak eşik (20.11.2026):** "Sıfıra yakın" tanımı ve mutlak eşik ilk Planned karşılaştırmasında önerilir ve kullanıcıya sorulur.
- **Karşılaştırmada girdi sürümü (20.11.2026):** `star-weekly` Kasım test koşusunu 9+3 aylık model ve 9+3 Capex Input ile yaptı; Planned model ve Hedge Plan 10+2. `star-weekly`'nin önerisi: "Kolların karşılaştırması, Planned modelin kullandığı aylık sürümle (Kasım için 10+2) yapılır; farklı sürümle koşu yalnız teknik testtir." Bu kolun gözlemi: Planned modelin bağlı olduğu bazı girdiler 9+3 adını taşıyor (`GIRDI_LISTESI.md` A9–A18, C6). İfade kullanıcıya sorulacak.
- **CAPEX sapması (20.11.2026):** `star-weekly`'ye göre sapma okuma yönteminde değil, hangi Capex Input sürümünün ve düzeltmesinin kullanıldığında; 9+3 aylık model 6+6 Capex Input'a bağlı. Bu kolun girdi listesine göre Planned model `Capex Input_9+3` dosyasını okuyor (C6; hücre teyit edilmedi). Aşama 3'e ait; açık.
- **Open Trades (20.11.2026):** `star-weekly`'ye göre ayrı bir dosya (`STAR Open Trades_<ggaayy>`); motor hedge crack ve çeyrek hacmini buradan okuyor. Hedge Plan'daki tarihli işlem sayfalarının bu dosyanın kopyası olup olmadığı hücre bazında teyit edilmedi. Bu kolun girdi listesine eklenip eklenmeyeceği kullanıcıya sorulacak.
- **Açılış stoğunda Eylül sonu satırları (20.11.2026):** Planned model açılış stoğunu ağırlıkla Ekim sonu `3_Stoklar` dosyasından alıyor, iki satırı Eylül sonu dosyasından okuyor (`GIRDI_LISTESI.md` A6–A7). Satırlar ve hücreler stok kartı yazılırken çıkarılır, STAR'a sorulur ve `star-weekly`'ye iletilir.
- **Birleşmede aktarılacaklar (20.11.2026):** Yöntem/model/forecast mantığına ait olup bu kola ait olmayan bilgiler burada listelenir.
  - *Kaynak: Akın-Weekly Star devir paketi (20.11.2026; kayıtların son hali 11.11.2026). Ayrıntı pakette; buraya yalnız başlık yazıldı.*
  - **Engine hedefi:** Nihai hedefte yalnız girdiler verilir; ana model (.xlsb) ve Financial Results verilmez, aynı sonuç bağımsız engine ile üretilir. Öğrenme aşamasında model ve Results yalnız doğrulama referansıdır (eski K16; eski K05 "model gerçeğin kaynağı"nın yerine geçmiş). Production girdi paketinde modelin olup olmayacağı (D-02) cevapsız.
    - yerine geçer: 20.11.2026 – bkz. "Amaç ve yön – netleştirme".
  - **Eski motor:** Excel modelinin Python kopyası; kodu kayıp, yöntemi eski MODEL_REHBERI'de belgeli.
  - **Model yapısı:** sayfa düzeni, ay türüne göre veri kaynağı, Results'taki model dışı etkiler, KPI tanımları (GRM, Net Cash Margin, Clean GRM), elle müdahale ve haftalık yeniden bağlama haritası.
  - **Reconciliation:** L0–L4 katmanları ve tolerans varsayımı (eski A07).
    - yerine geçer: 20.11.2026 – tolerans için bkz. "Amaç ve yön – netleştirme".
  - **Hedef çıktı:** model EBITDA'sı mı, Results EBITDA'sı mı (D-01, cevapsız). Haftalık stok kanal payı yöntemi (D-03, cevapsız).
    - yerine geçer (D-01 için): 20.11.2026 – ana modelin ve Financial Results'ın çıktılarının tamamı karşılaştırılır (bkz. "Amaç ve yön"). D-03 açık.
    - yerine geçer: 20.11.2026 – kapsam aşamalı; bkz. "Amaç ve yön – netleştirme".
  - **Çıktı biçimi:** dashboard (ana ekran + kontrol paneli), crack/fiyat senaryo kolları, girdi grubu bazında haftalık köprü (eski K02, K06, K07, K09).
  - **Sunum kuralları:** renk yönü, n.m. yüzde formülü, ay geçişinde kolon kaydırma kontrolü, şekil ve tanımlı ad kuralları; `weekly-sunum-kontrol` ve `denetci` skill'leri.
  - **Ajan ekibi ve döngü:** `star-weekly-orkestra` skill'i.
  - **STAR ekibine sorulacak model/Results soruları:** Net Refinery Margin tanımı, hedge roll çift sayımı, model Checks hataları, Results'taki sabit sayılar, sunumdaki FY EBITDA'nın aylık baza bağlı olması.
  - **Ortak forecast metodolojisi v1.0:** güven modeli, mapping standardı, onay panosu, kayıt sistemi; PETKİM ile ortak. Bu kola alınmadı; tümden gelim kolunda kullanılıp kullanılmayacağı birleşmede kararlaştırılır.
  - **Girdi → model hücre eşlemesi:** eski SUREC_MAPPING_0_30 §1–§14 (LP ve Hedge Plan'ın model hücrelerine akışı) ve negatif ara ürünün ithal satırına pozitif hacim olarak gitmesi (eski R11). Hangi alanın kullanılıp hangisinin kullanılmadığına dair eski R01, R03, R04, R10, R12 kuralları ilgili dosya kartlarında.
  - **Hedge hesabı:** hedge'li tonajın fiyatı, ağırlıklı fiyat ve hedge etkisi formülü (eski H6, onaysız); model ile Results'ın aynı hedge fiyatını görüp görmediği ve "aynı sonuç" referansı (eski H4 / A06, onaysız).
    - yerine geçer: 20.11.2026 – hedef değer ve "aynı sonuç" referansı için bkz. "Amaç ve yön – netleştirme".
