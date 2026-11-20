# STAR Weekly Forecast — Tümevarım

STAR şirketinin haftalık forecast'ının tümevarım kolu: forecast'a giren dosyalar tek tek tanıtılır; her birinin ne olduğu, nereden geldiği ve forecast'ta nasıl kullanılacağı kayda geçirilir. Tümden gelim kolu (model → sonuç) `star-weekly` reposundadır; bu repo sonunda onunla birleşecek. Bu dosya projenin giriş noktası: her oturum önce bunu, sonra `KARAR_GUNLUGU.md`'yi okur.

> Bu proje bağımsızdır. `star-weekly` dışındaki projelerden (ör. OPEX) kural, eşik ya da yöntem taşınmaz. `star-weekly`'den de bir şey ancak kullanıcı açıkça isterse alınır.

## İlkeler

1. **Tek ev, kopya yok.** Her bilgi türünün tek bir yeri vardır (aşağıdaki tablo). Aynı bilginin ikinci kopyası tutulmaz; bir yerde değişen bilgi başka yerde eskimiş halde kalmaz.
2. **Dallanma ve versiyon yok.** `v2`, `_yeni`, `_eski` gibi paralel dosyalar ya da açık kalan git dalları tutulmaz. Kazanan yöntem kalır, kaybeden silinir; geçmiş git'tedir.
3. **Anayasa: varsayımla sonuca gidilmez.** Açıkta kalan hiçbir konu Claude'un varsayımıyla kapatılmaz. Claude önerisini söyler ama her açık konuyu mutlaka kullanıcıya sorar; cevap gelene kadar konu açık kalır.

## Bilgi nerede durur

| Bilgi | Yeri |
|---|---|
| Rutin, ilkeler, dosya haritası, dosya kartı biçimi | `CLAUDE.md` (bu dosya) |
| Yürürlükteki kurallar, kararlar, açık konular | `KARAR_GUNLUGU.md` |
| Girdi dosyası tanımları | `dosyalar/<dosya_adı>.md` (dosya başına tek kart) |
| Kod ve testler | Bu repo |
| Sabit referans bilgiler (eşleme tabloları vb.) | claude.ai Project dosya alanı |
| Tanıtılan dosyanın kendisi ve haftalık veri | Sohbete eklenir; repoya girmez |

Claude.ai Project talimatı yalnızca bu repoyu işaret eder; detay orada tutulmaz.

## Dosya kartı

Her girdi dosyası için `dosyalar/` altında tek bir kart tutulur. Kartta şu başlıklar bulunur:

- **Dosya adı ve sürümü/dönemi**
- **Kaynak** (hangi sistem/rapor, kim gönderiyor)
- **Sıklık**
- **Yapı** (sayfalar, kolonlar, birimler)
- **Anahtar alanlar ve diğer dosyalarla eşleşmesi**
- **Forecast'taki rolü**
- **Bilinen tuzaklar / temizlik adımları**
- **Açık sorular**
- **Tanıtım tarihi**

Kartlara gerçek rakam ya da şirket verisi yazılmaz; yalnızca yapı ve anlam.

## Dosya tanıtım rutini

1. Kullanıcı dosyayı sohbete ekler. İlk girdiyle birlikte aynı dönemin ana modeli (.xlsb) ve Financial Results'ı da bir kez gelir.
2. Claude dosyayı okur ve yapısını çıkarır. Dosyanın kartı varsa dosyayla karşılaştırır; forecast'taki rolünü modelin bağlantılarından doğrular. Model ve Results'ı denetçi gözüyle okur (KARAR_GUNLUGU "Çıktıların kullanımı").
3. Claude bütün soruları bir soru panelinde (claude.ai sayfası) toplar. Her soruda önerisini ve emin olup olmadığını belirtir; karta yazılı bilgiler de teyit için sorulur.
4. Kullanıcı soruları STAR ekibiyle birlikte panelde cevaplar; Claude cevapları panelden okur.
5. Claude karta ve günlüğe ne yazacağını önce kullanıcıya gösterir; metin birlikte gözden geçirilir.
6. Kullanıcı onaylayınca yazılır ve `main`'e push edilir. Cevaplanmayanlar "Açık sorular"da kalır.

Kullanıcının cevaplamadığı hiçbir şey kabul sayılmaz.

## Oturum rutini

**Başlangıç**
1. Repo klonlu değilse klonla, klonluysa `git pull --rebase` ile güncelle; `KARAR_GUNLUGU.md`'yi oku.
2. Project dosya alanındaki referans dosyaları ve `dosyalar/` altındaki kartları listele.
3. Dosya tanıtılacaksa dosyayı sohbette kullanıcıdan al; eksik ya da şüpheli noktayı kart yazılmadan önce sor.

**Bitiş**
1. Oturumda verilen kararları `KARAR_GUNLUGU.md`'ye işle. Eski kural silinmez, altına "yerine geçer: …" yazılır; kapanan açık konu listeden çıkar.
2. Değişiklikleri doğrudan `main`'e commit + push et. Açık dal bırakma.
3. Veri dosyasının commit'e girmediğini kontrol et.

## Çalışma düzeni

- **Git:** Tek dal, `main`. Değişiklik doğrudan `main`'e gider.
- **Eşzamanlı çalışma:** Proje birden fazla kişiyle paylaşılır; aynı anda iki oturum çalışabilir.
  - Her yazmadan hemen önce `git pull --rebase` yapılır.
  - Değişiklik küçük commit'lerle hemen push edilir; oturum boyunca yerelde bekletilmez.
  - Dosya baştan yazılmaz; yalnız ilgili satır eklenir ya da değiştirilir. Bu özellikle `KARAR_GUNLUGU.md` için geçerlidir.
  - Push reddedilirse yeniden `git pull --rebase` yapılır.
  - Çakışmada diğer kişinin satırı silinmez ve üzerine yazılmaz; iki satır birleştirilir.
  - İki satır anlamca çelişiyorsa çözmeden önce kullanıcıya sorulur.
- **Kararlar:** Açık konular sohbette soru-cevap ile kapatılır, sonuç günlüğe işlenir. Kullanıcının cevaplamadığı konu kabul sayılmaz.
- **Kapsam:** Model, yöntem ve forecast mantığı bu kola yazılmaz; böyle bir bilgi gelirse `KARAR_GUNLUGU.md`'deki "Birleşmede aktarılacaklar" listesine kısa not olarak eklenir.
- **Veri gizliliği:** Şirket verisi (xlsx, xlsm, csv, sap çekimleri) repoya girmez; `.gitignore` bunu dışlar.
