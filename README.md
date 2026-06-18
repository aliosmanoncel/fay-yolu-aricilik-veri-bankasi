# Fay Yolu Arıcılığı — Veri Bankası
**Active Fault Beekeeping — Data Repository**

[![Türkiye Diri Fay](https://img.shields.io/badge/MTA%20Diri%20Fay-14.565%20segment-orange)](data/turkiye_diri_fay.geojson)
[![WGS84](https://img.shields.io/badge/CRS-WGS84-blue)](data/turkiye_diri_fay.geojson)
[![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-green)](LICENSE)

> *"Arılar nektarı takip ediyor; Anadolu ise milyonlarca yıldır bu faylar boyunca şekilleniyor."*  
> — Öncel, A. O. (2026). Fay Yolu Arıcılığı Doktrini. BeekeepingGeoTour v8 Final.

---

## Veri Dosyaları / Data Files

| Dosya | İçerik | Kaynak |
|-------|--------|--------|
| [`data/turkiye_diri_fay.geojson`](data/turkiye_diri_fay.geojson) | Türkiye Diri Fay Veri Bankası — 14.565 segment | MTA 2013 (KMZ → GeoJSON) |
| [`data/beehive_sensors_template.geojson`](data/beehive_sensors_template.geojson) | Ardu-Bee kovan sensör ağı şablonu | Öncel (2026) |

---

## Fay Tipi Sınıflaması / Fault Type Classification

| Kod | Tip | Örnek | Arıcılık Tipi |
|-----|-----|-------|----------------|
| 1 | Doğrultu atımlı (strike-slip) | KAFZ · DAFZ | Geçiş koridoru |
| 2 | Normal fay (extension) | BAT Graben sistemleri | Ova / salgı arıcılığı |
| 3 | Ters fay / bindirme (thrust) | Güneydoğu Anadolu Bindirmesi | Dağ arıcılığı |
| 4 | Tanımsız | — | — |

---

## Kritik Segmentler / Key Segments

| Segment | Fay Zonu | Tip | Tarihsel Deprem |
|---------|----------|-----|-----------------|
| Ganos Segmenti | KAFZ | 1 | M 7,4 · 08/10/1912 |
| Pazarcık Segmenti | DAFZ | 2 | M 7,8 · 06/02/2023 |
| Amanos Segmenti | DAFZ | 2+3 | — |
| Erkenek Segmenti | DAFZ | 2 | — |
| Sürgü Fayı | — | — | M 7,7 · 06/02/2023 |

---

## Bilimsel Altyapı / Scientific Basis

**Jeolojik omurga:**  
Emre, Ö., Duman, T. Y., Özalp, S., Şaroğlu, F., Olgun, Ş., Elmacı, H., & Çan, T. (2018).  
Active fault database of Turkey. *Bulletin of Earthquake Engineering*, 16(8), 3229–3275.  
https://doi.org/10.1007/s10518-016-0041-2

**Biyosismik sensör mekanizması:**  
Woith, H., Petersen, G. M., Hainzl, S., & Dahm, T. (2018). Review: Can animals predict earthquakes?  
*Bulletin of the Seismological Society of America*, 108(3A), 1031–1045.  
https://doi.org/10.1785/0120170313

**Arı zehiri coğrafi farklılıkları:**  
Varol, E. (2024). *Türkiye'nin farklı coğrafi bölgelerindeki bal arısı ırk ve ekotiplerinden elde edilen arı zehirinin biyokimyasal içeriklerinin ve kalite özelliklerinin belirlenmesi* [Doktora Tezi]. Ege Üniversitesi.

---

## Ardu-Bee Entegrasyon Protokolü / Ardu-Bee Integration Protocol

Her kovan, Emre vd. (2018) veri tabanındaki 485 aktif fay segmentinden biriyle koordinat bazlı eşleştirilir.  
Fayın **tipine** ve **kayma hızına** göre Ardu-Bee biyo-akustik eşiği otomatik kalibre edilir:

```
Doğrultu atımlı (Tip 1)  →  KAFZ: 2,5 cm/yıl  →  yüksek gerilme eşiği
Normal fay       (Tip 2)  →  BAT:  3,0 cm/yıl  →  EC + kül bazlı terroir
Ters fay         (Tip 3)  →  DAF:  1,0 cm/yıl  →  yüksek prolin eşiği
```

**Huzur bandı:** 230–270 Hz  |  **Alarm bandı:** 265–350 Hz  
**Episantr eşiği:** 56 km (Whitehead & Ulusoy, 2013)

---

## Lisans / License

Orijinal KMZ verisi: **MTA Genel Müdürlüğü** (kamuya açık).  
GeoJSON dönüşümü ve entegrasyon şeması: **Ali Osman Öncel** (2026).  
Bu repo **CC BY-NC-SA 4.0** lisansı altında paylaşılmaktadır — akademik atıf zorunludur, ticari kullanım yasaktır.

---

*İletişim: ali.oncel@iuc.edu.tr · İstanbul Üniversitesi-Cerrahpaşa, Jeofizik Mühendisliği*
