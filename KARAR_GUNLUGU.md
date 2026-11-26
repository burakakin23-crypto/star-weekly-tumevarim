# Karar Günlüğü

Yürürlükteki kurallar ve açık konular. Eski kural silinmez; değiştiğinde altına "yerine geçer: <tarih> <yeni kural>" yazılır.

## Yürürlükteki kararlar

### Kurulum (20.11.2026)
- Bu repo (`star-weekly-tumevarim`) STAR haftalık forecast'ının tümevarım koludur: girdi dosyaları tek tek tanıtılır. Tümden gelim kolu `star-weekly` reposudur.
- Detaylar GitHub'da (`star-weekly-tumevarim` reposu); claude.ai Project talimatı yalnızca repoya işaret eder.
- Oturum rutini ve dosya tanıtım rutini repodaki `CLAUDE.md`'de tutulur; ayrı bir skill yok.
  - yerine geçer: 20.11.2026 – oturum rutini `CLAUDE.md`'de kalır; dosya tanıtım adımları `skills/star-girdi-tanitma/SKILL.md`'ye taşındı; skill düzeni kuruldu (bkz. "Skill düzeni").
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
  - yerine geçer: 23.11.2026 – dönem Kasım 2026 Planned; 0+30 ayrı versiyondur (bkz. "Tur 1 panel cevapları").
- Ana model ve Financial Results ilk girdiyle bir kez gelir; yalnız girdinin rolünü doğrulamak için kullanılır. Hücre eşlemesi yine "Birleşmede aktarılacaklar"a gider.
  - yerine geçer: 20.11.2026 – burada kastedilen Planned model ve Planned Results; aylık model ve aylık Results girdi olarak ayrıca ele alınır.
- Sıra: LP model → Hedge Plan → Budget Calc → STAR EBITDA Crack Margin Effect.
- "(STAR)" işaretli açık sorular STAR ekibiyle birlikte cevaplanır.
- Girdiler turlar halinde toplu tanıtılır; her turun soruları bir panelde toplanır ve bir sonraki toplantıda STAR ekibiyle cevaplanır.
- Tur 1 paneli (LP model, Hedge Plan; 35 soru): https://claude.ai/artifact/7xovmnq3pPtxe7dxbB8Wm5
- Tur 2 sırası: Budget Calc → Crack Margin Effect → Gas Power Prices → 3_Stoklar → Inventory Effect.

### Kapsam (20.11.2026)
- Şu an Planned (0+30) girdileri tanıtılıyor.
  - yerine geçer: 23.11.2026 – şu an Kasım 2026 Planned girdileri tanıtılıyor; 0+30 ayrı bir versiyondur (bkz. "Tur 1 panel cevapları").
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
- **Karşılaştırmada girdi sürümü:** Kolların karşılaştırması, Planned modelin fiilen bağlı olduğu girdi sürümleriyle yapılır; farklı sürümle koşu yalnız teknik testtir. (Kasım Planned modeli 10+2 bazlı, ama bağlı olduğu bazı girdiler 9+3 adını taşıyor; bkz. `GIRDI_LISTESI.md`.)
- **Karar dosyası:** Birleşmeye kadar `KARAR_GUNLUGU.md`; birleşmede içerik `star-weekly`'nin `00_MASTER/04_KARARLAR.md` yapısına taşınır.
- **Pusula:** Yeni iş açılırken amaca katkısı yazılır; amaca katkısı olmayan iş açılmaz; park işlere şimdi dokunulmaz.

### Skill düzeni (20.11.2026)
Karar veren: Akın. `star-weekly`'deki düzenle aynı yapı (orada M-31); içerik bu kolun işine göre yazıldı.
- **Yer:** `skills/<ad>/SKILL.md`; her dosyanın başında `name` ve `description`. Katalog: `skills/README.md` (iş skill'leri, rol skill'leri, bekleyenler). Dosyalar düz metindir; tek bir araca bağlı değildir.
- **İş skill'leri:** `star-girdi-tanitma`, `star-girdi-listesi`, `star-soru-paneli`, `star-karar-isleme`.
- **Rol skill'leri** (adlar `star-weekly` ile aynı; birleşmede tek dosya olur): `star-rol-denetci`, `star-rol-model-denetcisi`, `star-rol-muhasebeci`, `star-rol-finansci`, `star-rol-analist`, `star-rol-rafineri-uzmani`, `star-rol-hedge-uzmani`, `star-rol-cfo`, `star-rol-sunumcu`. Rol kural koymaz.
- **Bekleyenler:** önünde açık karar olan skill yazılmaz, katalogda bekler.
- **Dosya tanıtım adımları** `star-girdi-tanitma` skill'indedir; `CLAUDE.md` oraya işaret eder. Dosya kartı biçimi `CLAUDE.md`'de kalır.
- **Atıf:** skill kurala ve karara bölüm başlığıyla atıf yapar, metnini kopyalamaz. **Atıf yapılan bölüm başlıkları değiştirilmez** (`CLAUDE.md` ve bu günlükteki bölüm başlıkları).
- **Öğrenme:** her skill'de Öğrenilenler bölümü vardır (tarih / ne görüldü / bundan sonra ne yapılır). Claude gerek gördüğünde yeni skill ekleyebilir ve Öğrenilenler'e kendiliğinden yazabilir; oturum sonunda ne eklediğini söyler.
- **Sınır:** kendiliğinden yazma yalnız Öğrenilenler ve yeni skill için geçerlidir; kart ve günlük için "önce göster" kuralı sürer. Skill yalnız "nasıl yapılır"ı öğrenir: kural, eşik, kapsam ya da karar değiştiren şey kullanıcıya sorulur ve bu günlüğe işlenir. Açık konu skill'de varsayımla kapatılmaz. Skill'e finansal rakam ve dosya içeriği yazılmaz.
- **Tek ev:** aynı adım iki skill'de anlatılmaz; biri diğerine işaret eder.

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
  - yerine geçer: 23.11.2026 – dosyalar ve sayfalar adından değil içeriğinden tanınır; ad standarttan farklıysa durulmaz, uyarılır.
- Aynı adlı girdinin iki farklı kopyası/konumu kullanılıyorsa hata sayılır (eski R16).
- Dosyaların hepsi aynı versiyona (Planned / a+p haftası) ait değilse önce bu söylenir.
- Yüklenen dosya değiştirilmez, kopyasında çalışılır. Düzeltmeyi kullanıcı yapar; Claude hücre bazında söyler.

**Satır ve kalem**
- Tüm satırlar, boş olanlar dahil, gruplu takip edilir; veri sonradan gelebilir (eski R02).
- Satırlar ada göre eşlenir; veri gelince otomatik kullanılır, karşılığı yoksa uyarı verilir (eski R08).
- Yeni kalem kullanıcıya sorulmadan eklenmez (eski R15).
  - yerine geçer: 23.11.2026 – yeni kalem önce kullanıcıya sorulur; onaylanınca modeldeki yöntemle eklenir (yöntem "Birleşmede aktarılacaklar"da).
- Her satır her ay şu durumlardan birine konur: dolu + karşılığı var · dolu + karşılığı yok (uyarı) · boş + karşılığı var · boş + karşılığı yok · yeni satır (sorulur).
- Girdide dolu olup forecast'a girmeyen her kalem için uyarı verilir (eski R05).

**Değer kontrolü**
- Fiyatı olup hacmi olmayan kalem uyarıdır, hata sayılmaz (eski R13).
- Hacmi olup fiyatı olmayan kalem hatadır; fiyat kaynağı kullanıcıya sorulmadan devam edilmez.
- Birim uyuşmazlığında sessiz dönüşüm yapılmaz, uyarı verilir (eski R14).
- Elle yazılmış değer ya da başka ayın dosyasına giden bağlantı görülürse uyarılır (eski R07).
- Her rakam dosya + sayfa + hücreye izlenebilir olmalı; kaynakta olmayan rakam üretilmez.

### Tur 1 panel cevapları (23.11.2026)
Cevaplar Tur 1 panelinden (https://claude.ai/artifact/7xovmnq3pPtxe7dxbB8Wm5); kullanıcı STAR ekibiyle cevapladı. Kart bilgileri ilgili kartlara işlendi; burada yalnız karar niteliğindekiler. Hedge Plan soruları 2. oturuma kaldı.
- **Hacim ve fiyat eksikliği (A1):** Mevcut ayrım kalır: hacim var fiyat yok = hata; fiyat var hacim yok = referans fiyat, uyarı. STAR notundaki "iki yön de veri girişi hatası" ifadesi uygulanmaz.
- **Versiyon adları (A4):** 0+30 ile Planned ayrı versiyonlardır; ikisi de aynı biçimdeki LP model dosyasını kullanır. Ayın son haftasında bir sonraki ay sunulur, adı 0+30'dur (ör. Kasım'ın son haftasında Aralık 0+30). Ertesi hafta aylık forecast verileriyle çalışılır, adı Planned'dır. İkisinde de gerçekleşen yoktur, fiyat doğrudan alınır.
- **Hedge tutarlarının Results'taki yeri (B5):** "Crude Roll + Inventory Hedge" COGS'a, "Product Inventory Hedge" gelire eklenir. Kasım 2026 Planned Results'ın tersini yapması bulgudur; sonraki ay gözlemlenir.
- **Çıktı biçimi (C5):** Çıktı Financial Results ile aynı sayfa düzeninde verilir.

### Tur 1 panel cevapları – 2. oturum (25.11.2026)
Cevaplar Tur 1 panelinden (2. oturum, STAR ekibiyle). Kart bilgileri ilgili kartlara işlendi; burada yalnız karar niteliğindekiler.
- **Yalnız çalışılan ay (E1):** Girdilerden yalnız çalışılan ayın (EBITDA'yı ilgilendiren ayın) rakamı alınır; geçmiş ve gelecek aylara bakılmaz. Stok gibi konularda geçmiş veriler kullanılır.
- **Hedge Plan çıktı olacak (E4):** Hedge Plan, Claude'un girdilerden hazırlayacağı bir çıktı olacak. Bunun için gereken girdiler (Open Trades, LP, Daily Prices – güncel fiyatla ilerlenirse, Budget Calc ve diğerleri) öğrenilir. Verilen girdi güncel kabul edilir; Claude yine de kendisi teyit eder.
- **Model ile girdi arasındaki güncelleme farkı (E5):** Planned modelin bir girdiden sakladığı değer girdinin şimdiki değerinden farklıysa (bağlantı güncellenmemiş), bu şimdilik dikkate alınmaz; hesap girdilerden yapılır.
- **Birim hataları (B1):** Birim ya da başlık hatası her görüldüğünde uyarı olarak bildirilir.
- **Çıktıda iki katman (E11):** Yönetici (1) model çıktısını ve (2) manuel düzeltmeleri ayrı görmek ister. Financial Results'taki manuel etkiler ayrı değerlendirilir. Results'ın kendi CHECK satırının sıfır olmaması normaldir (model dışı etkiler).

### Nihai çıktı: yönetim sunumu (26.11.2026)
Karar veren: Akın. Kaynak: kullanıcının paylaştığı `Management meeting template_10.11.2026.pptx` ve onu besleyen `PETKIM_STAR_Weekly_Forecast_Update_Presentation_Nov_Planned.xlsm` (dosyalar repoya girmez).
- **Nihai hedef:** Proje sonunda girdilerden haftalık yönetim toplantısı sunumunun STAR bölümü üretilir. Yönetimin kullandığı ve anladığı format budur.
- **Kapsam yalnız STAR:** Bu kol için sunumun STAR kısmı hedeftir: slayt 3 (STAR P&L ve operasyonel KPI), slayt 4 (ham petrol sepeti, tüketim, landing diferansiyeli), slayt 5 (satış miktarları, FOB crack) ve slayt 2'deki STAR satırları. Petkim, Petrol Ticaret, STAD, AR-GE ve R&P BU toplamı bu kolun hedefi değildir.
- **Dashboard:** Dashboard'da bu sunumdaki STAR verileri mutlaka gösterilir.
- **Girdi tanıtımı:** Girdiler tanıtılırken bu sunumdaki STAR sonuçlarına da ulaşılması hedeflenir.
- **Sunum Excel'i çıktıdır:** `PETKIM_STAR_Weekly_Forecast_Update_Presentation_<Ay>_Planned.xlsm` yalnız görmek için paylaşıldı; girdi olarak verilmeyecek. Claude bu Excel'i girdilerden kendisi üretir; girdilerden hem sunuma hem modele ulaşılır.
- **Çıktı katmanları (C5 ile):** C5 yürürlükte kalır: Financial Results düzeni ara çıktı, yönetim sunumu nihai çıktıdır.
- **Slayt 2 makro göstergeleri:** Hepsi hedefe girer: Brent, USD/TL, EUR/TL, EUR/USD, ABD TÜFE ve TL TÜFE (sunumda Economic Assumptions dosyasından okunuyor).
- **Yapı (bilgi):** Sunumun finans slaytları (1–9) sunum Excel'inden makroyla doldurulur (`HaritaOlustur`, `SunumaAktar`); Excel'deki tanımlı adlar sunumdaki şekil adlarıyla aynıdır (ör. `S03_T1`). 26.11.2026'da Excel'in kayıtlı değerleri sunumla karşılaştırıldı; farklar yalnız yuvarlama.

## Açık konular

- **Birleşme (20.11.2026):** Bu kol `star-weekly` ile birleşecek; biçimi o gün kararlaştırılır.
  - yerine geçer: 20.11.2026 – birleşmenin yeri de biçimi de açık.
- **Girdi teslim günü (20.11.2026):** Eski kayıtlar çelişiyor: "departmanlar salı gönderir" (eski K13), "cuma girdi, pazartesi sunum" (eski K08 ve hafıza), "cuma veri istenir, salı girdiler gelir" (eski karşılaştırma sohbeti, onaysız). İlk girdi dosyası tanıtılırken netleşecek.
- **Production girdi paketinde ana model ve Results olacak mı (eski D-02, 20.11.2026):** Seçenekler: aylık model ayda bir girdi olarak gelir · yalnız girdiler gelir · geçiş (şimdilik aylık model, nihai hedef yalnız girdiler). Bu kolun girdi listesini belirler.
  - kısmen kapandı: 20.11.2026 – aylık model ve aylık Results girdidir; Planned model ve Planned Results verilmez. Açık kalan: aylık Results'tan ne alınacağı (aşağıda).
- **Mevcut kanıtla çözülen 13 maddenin toplu onayı (eski D-05, 20.11.2026):** Maddelerin ayrıntısı eski "Proje bilgi karşılaştırması" sohbetinde ve devir paketinde olmayan `PROJECT_KNOWLEDGE_EXPORT_Akin_Weekly_Star.md` dosyasında. Dosya gelince ele alınacak.
- **Aylık Results'tan ne alınacağı (20.11.2026):** Aylık Financial Results girdi sayılıyor; içinden hangi değerlerin alınacağı belli değil. İlk Planned karşılaştırmasından sonra ele alınır.
- **Sıfıra yakın kalem ve mutlak eşik (20.11.2026):** "Sıfıra yakın" tanımı ve mutlak eşik ilk Planned karşılaştırmasında önerilir ve kullanıcıya sorulur.
- **CAPEX sapması (20.11.2026):** `star-weekly`'ye göre sapma okuma yönteminde değil, hangi Capex Input sürümünün ve düzeltmesinin kullanıldığında; 9+3 aylık model 6+6 Capex Input'a bağlı. Bu kolun girdi listesine göre Planned model `Capex Input_9+3` dosyasını okuyor (C6; hücre teyit edilmedi). Aşama 3'e ait; açık.
- **Open Trades (20.11.2026):** `star-weekly`'ye göre ayrı bir dosya (`STAR Open Trades_<ggaayy>`); motor hedge crack ve çeyrek hacmini buradan okuyor. Hedge Plan'daki tarihli işlem sayfalarının bu dosyanın kopyası olup olmadığı hücre bazında teyit edilmedi. Girdi listesine "dosya bekleniyor" durumuyla eklendi (A19); dosya gelince tanıtılır.
- **Açılış stoğunda Eylül sonu satırları (20.11.2026):** Planned model açılış stoğunu ağırlıkla Ekim sonu `3_Stoklar` dosyasından alıyor, iki satırı Eylül sonu dosyasından okuyor (`GIRDI_LISTESI.md` A6–A7). Satırlar ve hücreler stok kartı yazılırken çıkarılır, STAR'a sorulur ve `star-weekly`'ye iletilir.
- **Tur 1 panelinde açık kalanlar (23.11.2026):** Birimler (B1), negatif ara ürünün fiyatı (C2), forecast crack'in kaynağı (A3) ve Hedge Plan soruları (E1–E11). Panelin 2. oturumunda STAR ekibiyle.
  - yerine geçer: 25.11.2026 – 2. oturumdan sonra açık kalanlar: negatif ara ürünün fiyatı (C2, üç alt soru; LP kartı) ve forecast crack'in kaynağı (A3b; Hedge Plan kartı).
- **Ara dönem örneği (23.11.2026):** Kullanıcı September 11+19 dosyasını gönderecek (Product Prices sayfası). Ara dönemde fiyat, crack ve Brent ağırlıklandırması onunla doğrulanır (haftalık girdi kartı).
- **Manuel etkilerin verisi (25.11.2026, E11):** Financial Results'a elle eklenen etkilerin (ör. Upside/Downside Excel'i) bu kola hangi biçimde verileceği konuşulacak. Kullanıcı, Upside/Downside'ın modele eklenmesinin değerlendirilmesini istedi; değerlendirme sunulacak.
- **Hedge Plan çıktısının biçimi (25.11.2026, E9):** Summary dahil ne gösterileceği, önceki versiyonla kıyasın yeri; `star-weekly`'deki hedge plan sayfasıyla birlikte karar verilecek.
- **`star-weekly` ile eşleme (23.11.2026):** Tur 1 cevaplarından üçü diğer kolu da ilgilendiriyor: çıktı biçimi (C5), 0+30 ile Planned'ın ayrı versiyonlar olması (A4; "Amaç ve yön" bölümlerindeki "Planned (0+30)" ifadeleri ortak kayıtta düzeltilecek) ve hedge tutarlarının Results'taki yeri (B5). `star-karar-isleme` adım 4 ile iletilecek.
  - 25.11.2026 ek: Hedge Plan'ın çıktı olması (E4), çıktıda iki katman (E11) ve Hedge Plan çıktısının biçimi (E9) de iletilecek.
  - 26.11.2026 ek: Nihai çıktının yönetim sunumunun STAR bölümü olması ve dashboard'un bu verileri göstermesi de iletilecek (bkz. "Nihai çıktı: yönetim sunumu").
- **Sunumun STAR ara dosyası (26.11.2026):** Sunumdaki STAR rakamlarının çoğu ara bir dosyadan geliyor (`STAR EBITDA Performance Presentation_<Ay> Planned.xlsx`, Summary ve Margin Template sayfaları); Net refinery margin ve yıl sonu Brent Planned Results'tan, bütçe sütunu bütçe Results'ından. Ara dosya henüz görülmedi; girdi mi, hedef çıktı mı sayılacağı ve ne zaman tanıtılacağı açık.
- **Sunum Excel'indeki bulgular (26.11.2026):** Sunum Excel'i girdi değil, Claude'un üreteceği çıktı olduğu için bulgular STAR ekibine sorulmaz; Excel üretilirken bilgi olarak kullanılır. Ara dosya konusu (yukarıda) açık kalır.
  - Kullanım sayfası ve sayfa başı notları "tüm hücreler değerdir, formül yok" diyor; sayfalar 15 dış dosyaya formülle bağlı.
  - STAR bütçesi iki kaynaktan okunuyor: slayt 2 bütçe Results'ından (PL sayfası), slayt 3 ara dosyadaki Margin Template'ten. Aynı rakam olduğu teyit edilmedi.
  - Slayt 4 ham petrol tablosunda HSGO bütçe hücresi elle 0 yazılmış (`S04 STAR Ham Petrol`!D29).
  - Slayt 2 yıl sonu STAR katkısı (`S02 RPBU EBITDA`!C27) 9+3 Results ile Planned v2 Results'ın karışımından hesaplanıyor.
  - S05 slaytı sunumdan çıkmış: `S05_*` tanımlı adları #REF!; slayt 4'teki not hâlâ "landing diferansiyelleri sonraki sayfadan" diyor. Ayrıca `S01_H1` ve `S0x_SUB` adları #REF!.
  - Birim: slayt 3 Net refinery margin kartının Excel etiketi "[USD]", sunumda USD/bbl.
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
  - **Yeni kalem ekleme yöntemi (23.11.2026):** Modelde karşılığı olmayan kalem Master Data sayfasına eklenip ilgili sayfaya (ör. M_I) akıtılır.
  - **Hedge Summary çıktı olarak (23.11.2026):** Hedge Plan'ın Summary sayfası çıktı olarak verilir.
  - **Yönetim sunumu hücre eşlemesi (26.11.2026):** Sunum Excel'inin STAR sayfalarının (`S03`, `S04`, `S06` ve `S02`'deki STAR satırları) hangi dış dosyanın hangi hücresinden beslendiği ve makronun şekil ↔ aralık haritası (Harita sayfası). Ayrıntı sunum Excel'inde.
