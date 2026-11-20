# STAR Weekly Forecast — Tümevarım

STAR şirketinin haftalık forecast'ının tümevarım kolu: forecast'a giren dosyalar tek tek tanıtılır; her birinin ne olduğu, nereden geldiği ve forecast'ta nasıl kullanılacağı kayda geçirilir. Tümden gelim kolu (model → sonuç) `star-weekly` reposundadır; bu repo sonunda onunla birleşecek. Bu dosya projenin giriş noktası: her oturum önce bunu, sonra `KARAR_GUNLUGU.md`'yi okur.

> Bu proje bağımsızdır. `star-weekly` dışındaki projelerden (ör. OPEX) kural, eşik ya da yöntem taşınmaz. `star-weekly`'den de bir şey ancak kullanıcı açıkça isterse alınır.

## İlkeler

1. **Tek ev, kopya yok.** Her bilgi türünün tek bir yeri vardır (aşağıdaki tablo). Aynı bilginin ikinci kopyası tutulmaz; bir yerde değişen bilgi başka yerde eskimiş halde kalmaz.
2. **Dallanma ve versiyon yok.** `v2`, `_yeni`, `_eski` gibi paralel dosyalar ya da açık kalan git dalları tutulmaz. Kazanan yöntem kalır, kaybeden silinir; geçmiş git'tedir.

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

1. Kullanıcı dosyayı sohbete ekler.
2. Claude dosyayı okuyup yapısını çıkarır ve anlamadığını sorar.
3. Kullanıcı cevaplar.
4. Kart yazılır; cevaplanmayanlar "Açık sorular"da kalır.
5. Değişiklik `main`'e push edilir.

Kullanıcının cevaplamadığı hiçbir şey kabul sayılmaz.

## Oturum rutini

**Başlangıç**
1. Repo klonlu değilse klonla; `KARAR_GUNLUGU.md`'yi oku.
2. Project dosya alanındaki referans dosyaları ve `dosyalar/` altındaki kartları listele.
3. Dosya tanıtılacaksa dosyayı sohbette kullanıcıdan al; eksik ya da şüpheli noktayı kart yazılmadan önce sor.

**Bitiş**
1. Oturumda verilen kararları `KARAR_GUNLUGU.md`'ye işle. Eski kural silinmez, altına "yerine geçer: …" yazılır; kapanan açık konu listeden çıkar.
2. Değişiklikleri doğrudan `main`'e commit + push et. Açık dal bırakma.
3. Veri dosyasının commit'e girmediğini kontrol et.

## Çalışma düzeni

- **Git:** Tek dal, `main`. Değişiklik doğrudan `main`'e gider.
- **Kararlar:** Açık konular sohbette soru-cevap ile kapatılır, sonuç günlüğe işlenir. Kullanıcının cevaplamadığı konu kabul sayılmaz.
- **Kapsam:** Model, yöntem ve forecast mantığı bu kola yazılmaz; böyle bir bilgi gelirse `KARAR_GUNLUGU.md`'deki "Birleşmede aktarılacaklar" listesine kısa not olarak eklenir.
- **Veri gizliliği:** Şirket verisi (xlsx, xlsm, csv, sap çekimleri) repoya girmez; `.gitignore` bunu dışlar.
