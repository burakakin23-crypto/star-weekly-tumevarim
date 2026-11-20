---
name: star-rol-sunumcu
description: STAR Weekly tümevarım kolunda sunumcu gözüyle bakmak gerektiğinde kullanılır – soru paneli, kullanıcıya özet ya da STAR ekibine gidecek soru metni yazılırken; anlatımın karşı tarafın anlayacağı dilde olup olmadığına bakılırken.
---

# STAR – Rol: Sunumcu

Bu bir **bakış açısı** dosyasıdır; iş sırası değildir. İş skill'leri (`skills/README.md`) gerektiğinde bu role geçer. Kurallar `CLAUDE.md` ve `KARAR_GUNLUGU.md`'dedir; rol kural koymaz. Aynı adlı rol `star-weekly` reposunda da vardır; birleşmede tek dosya olur.

**Temel soru.** Okuyan kişi bunu ilk okuyuşta anlayıp cevap verebilir mi?

## Neye bakar

- **Önce sonuç:** özet neyin yapıldığını ve neyin beklendiğini ilk cümlede söylüyor mu?
- **Kitle:** kullanıcı için karar ve seçenek; STAR ekibi için dosya, sayfa, hücre ve yanıtlanabilir soru.
- **Tek soru:** her soru tek bir şeyi mi soruyor; bağlamı kendi içinde mi?
- **Dil:** iç kod ve kısaltma açıklanmış mı; dosya ve sayfa adları dosyadaki gibi mi yazılmış?
- **Dürüstlük:** emin olunmayan şey "emin değilim", teyitsiz şey "teyit edilmedi" diye mi yazılmış?
- **Rakam yok:** soruda şirket verisi ya da rakam var mı?

## Kendine sorduğu sorular

- Bu metni projeyi bilmeyen biri okusa ne soracağını anlar mı?
- Önerimi cevap gibi mi sundum?

## Çıktısı

Panel soru metni ya da kısa özet; STAR ekibi için ekip başlığıyla soru listesi.

## Sınırı

Sunum için içerik değiştirilmez; öneri cevap gibi yazılmaz. Rol kural koymaz ve karar vermez; öneri üretir, kararı kullanıcı verir. Açık konuyu varsayımla kapatmaz (`CLAUDE.md` "İlkeler" 3). Model, yöntem ve forecast mantığını bu kola yazmaz (`CLAUDE.md` "Çalışma düzeni" – Kapsam). Finansal rakam ve dosya içeriği yazmaz.

## Öğrenilenler

| Tarih | Ne görüldü | Bundan sonra |
|---|---|---|
| 20.11.2026 | Kullanıcı özetleri "çok kısa" istedi; uzun açıklama yerine girdi başına ne işe yarar, özellik, dikkat edilecek üçlüsü işe yaradı | Özeti girdi başına üç başlıkla ver; ayrıntıyı karta bırak |
| 20.11.2026 | Panelde yalnız öneri ve "açık kalsın" yetmedi; kullanıcı kendi cevabını yazabileceği seçenek istedi | Her soruya "Diğer" (serbest metin) koy |
