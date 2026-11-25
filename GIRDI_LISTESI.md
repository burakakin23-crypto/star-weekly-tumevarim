# Girdi Kontrol Listesi – Kasım 2026 Planned

Kasım 2026 Planned zincirine giren bütün dosyaların listesi. Tanıtım sırasında hiçbir girdinin atlanmaması için tutulur. Liste, ana modelin (`STAR 2026 10 2_Financial Model_EBITDA Forecast November Planned.xlsb`), Financial Results'ın, Hedge Plan'ın ve Tur 2 dosyalarının dış bağlantılarından çıkarıldı (20.11.2026). Dosyanın ne olduğu ve nasıl kullanıldığı burada değil, kartında yazar; bu liste yalnız ad, kimin okuduğu ve durum tutar.

**Durum:** ✅ kartı var ve dosyayla doğrulandı · 🔍 dosya geldi, analiz edildi, kart bekliyor · ⏳ dosya bekleniyor · ❔ kapsam kararı bekleniyor

## A. Kasım EBITDA'sına doğrudan giren ham girdiler

| # | Dosya | Okuyan | Durum | Kart |
|---|---|---|---|---|
| A1 | `STAR Budget (2026) - Forecast (03.11.2026)` (LP model) | Model | ✅ Tur 1 | `STAR_Budget_Forecast.md` |
| A2 | `Hedge Plan 2026 10 2  Forecast_November Planned` | Model, Results | ✅ Tur 1 · ileride Claude'un girdilerden hazırlayacağı çıktı (KARAR_GUNLUGU 25.11.2026) | `Hedge_Plan.md` |
| A3 | `2026 Budget Calc_16.10.2026` | Hedge Plan, Results | 🔍 Tur 2 | `Budget_Calc.md` (devirden) |
| A4 | `2026 Budget Calc_17.09.2026` (eski sürüm) | Hedge Plan (Jet dönüşüm faktörü; Ekim/Aralık) | 🔍 Tur 2 | `Budget_Calc.md` |
| A5 | `PETKİM&STAR Gas Power Prices_10_2` | Model | 🔍 Tur 2 | – |
| A6 | `3_Stoklar_2026` – Ekim sonu (10.2026) | Model (açılış stoğu) | ⏳ | – |
| A7 | `3_Stoklar_2026` – Eylül sonu (09.2026) | Model (açılış stoğu, iki satır) | 🔍 Tur 2 | – |
| A8 | `Daily Prices and Ratios_06112026` | Crack Margin Effect (güncel crack), Inventory Effect (Brent) | ⏳ | – |
| A9 | `Coupon Sales 2026_rev7` | Model | ⏳ | – |
| A10 | `Üretime Giden Kimyasallar_2026B` | Model | ⏳ | – |
| A11 | `STAR 2026 Utility` | Model | ⏳ | – |
| A12 | `Opex Calculation 2026B` | Model | ⏳ | – |
| A13 | `2026 Budget - Economic Assumptions - as of 07.10.2026 - 9+3` | Model (kur ve makro) | ⏳ | – |
| A14 | `Petkim 9 3 Forecast 2026 Budget_Model_rev` | Model (Petkim'den alınan bir fiyat) | ⏳ | – |
| A15 | `2026B_Personnel CC Chargeback_COGS GA SD Breakdown` | Results (COGS, G&A, S&D) | ⏳ | – |
| A16 | `9 3 Upside Downside Effects 2026` | Results | ⏳ | – |
| A17 | `TFS_Rolling Forecast_9+3_2026` | Results (diğer gelir/gider) | ⏳ | – |
| A18 | `STAR Ticari Ürün_2026 9 3` | Results (Revenue Breakdown) | ⏳ | – |
| A19 | `STAR Open Trades_<ggaayy>` | Hedge Plan (tarihli işlem sayfalarının olası kaynağı; teyit edilmedi). Model bağlantılarında görünmüyor; `star-weekly` bildirdi | ⏳ | – |

## B. Model ve Results'tan türeyen hesap dosyaları

İçindeki ham girdiler A bölümünde ayrıca listelenir.

| # | Dosya | Okuyan | Durum | Kart |
|---|---|---|---|---|
| B1 | `STAR EBITDA Crack Margin Effect` | Results (gelir), Hedge Plan (forecast crack) | 🔍 Tur 2 | – |
| B2 | `Inventory Effect Calculation_STAR 2026 10 2 November Planned` | Results (COGS, stok etkisi) | 🔍 Tur 2 | – |

## C. Kasım satırına giren ama EBITDA altında kalanlar

Kapsam aşamalı açılır (KARAR_GUNLUGU "Amaç ve yön – netleştirme"): bu bölüm aşama 2 (EBITDA altı) ve aşama 3 (bilanço, nakit akış) kapsamındadır.

| # | Dosya | Okuyan | Durum |
|---|---|---|---|
| C1 | `2026B STAR Ebitda altı figürler_9 9` | Results (finansman) | ❔ |
| C2 | `SOCAR Capital 2026F_2027B` | Results (finansman geliri) | ❔ |
| C3 | `TFS Update 2026B` | Results (kur farkı) | ❔ |
| C4 | `2026B Def Tax` | Results (vergi) | ❔ |
| C5 | `STAR 30.09.2026 Kredi Raporu` | Model (finansman) | ❔ |
| C6 | `Capex Input_9+3` | Model, Results (nakit akış) | ❔ |
| C7 | `NWC Assumption_2026B` | Model (işletme sermayesi) | ❔ |
| C8 | `Payment Schedule_Revised` | Model, Results (bilanço) | ❔ |
| C9 | `Net Debt Movement v2` | Results (bilanço, nakit akış) | ❔ |
| C10 | `Mart 2025 teşvik yatırıma katkı` | Model (vergi) | ❔ |
| C11 | `Taxation 2026B`, `IFRS _USD 2026`, `STAR VUK_TRY 2026`, `STAR IFRS 16 BÜTÇE_v2`, `7'li Hesaplar - STAR`, `Zero Based Budget Templates_B2026_Gayrimenkul Yönetimi` | Model (açılış / Ocak) | ❔ |

## D. Gerçekleşen aylar (Kasım rakamını değiştirmez; yıl toplamı için)

D2 ve D3 aylık Results ve aylık modeldir; girdi sayılır (KARAR_GUNLUGU "Amaç ve yön – netleştirme"). İçlerinden ne alınacağı açık.

| # | Dosya | Okuyan | Durum |
|---|---|---|---|
| D1 | `STAR_FS_<ay sonu>` (Ocak–Eylül, 9 dosya) | Model | ❔ |
| D2 | `STAR 2026 10 2_Financial Results_EBITDA Forecast` (aylık 10+2) | Model | ❔ |
| D3 | `STAR 2026 5 7_Financial Model_EBITDA Full Forecast` | Model (açılış) | ❔ |
| D4 | `STAR Margin Template_September_2026` | Results | ❔ |
| D5 | `crude processed analysis_September_2026` | Results | ❔ |
| D6 | `2_HC_Satis_2026` | Results | ❔ |
| D7 | `SATIŞLAR-2026` (Petkim) | Model (Ekim) | ❔ |
| D8 | `Daily Prices and Ratios_02112026` | Results (Ekim crack) | ❔ |
| D9 | `2026 Budget - Economic Assumptions - as of 06.05.2025 - v2` | Model (Ekim) | ❔ |

## E. Aralık sütunu (kapsam dışı: yalnız çalışılan ay)

| # | Dosya | Okuyan |
|---|---|---|
| E1 | `STAR Budget (2026) - Forecast (30.09.2026)` | Model |
| E2 | `Hedge Plan 2026 9 3 Forecast` | Model; Results'ta ayrıca Kasım "model harici etkiler" satırları (bkz. açık sorular) |
| E3 | `PETKİM&STAR Gas Power Prices_9_3_v2` | Model |
| E4 | `Prices Demands (Budget-2026)_9+3_RB` | Model |
| E5 | `Coupon Sales 2026_rev6` | Model |

## F. Karşılaştırma dosyaları (Kasım rakamını değiştirmez)

Bütçe (65 USD senaryosu) Results ve modeli · 2025 bütçe Results · Kasım 0+30 (9+3 bazlı) model ve Results · 8+4 Results · ULSD Hedge Plan bütçe (65 USD) · TFS Update 2027B · 65 USD senaryosu Ticari Ürün · TFS Update 2026B_6 6 · 2025 5+7 Results · Petkim 9 3 Full Forecast modeli (nafta faizi) · `2026 STAR Budget (HP Exc)`.

## G. Girdilerin içinde eskimiş görünen bağlantılar

Tanıtılırken ayrıca sorulacak.

- Gas Power Prices: 2021 gaz iş planına ve 9+3 elektrik iş planına bağlantı var; değerler hücrelere elle yazılmış.
- Crack Margin Effect: 2025 Temmuz Results'tan ürün başına katsayı, Ağustos Daily Prices, eski crude analiz dosyaları.
- Inventory Effect: 6+6 ULSD Hedge Plan ve Eylül Daily Prices.
- Budget Calc: hacimleri Planned modelden değil 10+2 aylık modelden okuyor.
