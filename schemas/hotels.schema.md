# 🏨 Hotels Data Schema

Bu dosya, `cesme_hotels.csv` verilerindeki sütunların anlamlarını ve veri türlerini tanımlar.  
Bu sayede n8n veya Google Sheets akışında doğru alan eşleştirmesi yapılabilir.

| Alan Adı | Tür | Açıklama | Örnek |
|-----------|-----|-----------|--------|
| `id` | integer | Her otel için benzersiz kimlik numarası | 1 |
| `name` | string | Otelin adı | Reges A Luxury Collection Resort & Spa |
| `category` | enum (`hotel`, `boutique`, `pension`) | İşletme türü | hotel |
| `district` | string | Bulunduğu bölge veya mahalle | Boyalık |
| `phone` | string | Telefon numarası (+90 formatında) | +90 232 723 03 03 |
| `website` | url | Otelin web sitesi | https://regescesme.com |
| `lat` | float | Enlem (harita konumu) | 38.3335 |
| `lng` | float | Boylam (harita konumu) | 26.3221 |
| `stars` | integer | Yıldız sayısı (1–5 arası) | 5 |
| `is_member` | boolean | Dernek/organizasyon üyesi mi | true |
| `updated_at` | date | Son güncelleme tarihi | 2025-11-11 |

## Özellik Sütunları

| Alan | Tür | Açıklama | Örnek |
|-----|-----|----------|-------|
| amenities | list(string) | Tesis özellikleri, `|` ile ayrılır | wifi|spa|pool |
| services | list(string) | Hizmetler | transfer|concierge |
| price_range | enum | budget\|mid\|premium\|lux | premium |
| accessibility | list(string) | Erişilebilirlik | step_free|accessible_room |
| pet_friendly | boolean | Evcil hayvan kabul | true |
| family_friendly | boolean | Aile uygunluğu | true |
| parking_type | enum | none\|street\|private\|valet | private |
| beach_access | enum | none\|public\|private | private |
| distance_to_sea_m | integer | Denize mesafe (metre) | 120 |
| checkin_from | time(HH:MM) | Giriş saati | 14:00 |
| checkout_until | time(HH:MM) | Çıkış saati | 12:00 |
| languages | list(string) | Konuşulan diller | tr|en|de |
| payment_methods | list(string) | Ödeme yöntemleri | cash|visa|mc |
| tags | list(string) | Sınıflandırma etiketleri | boutique|spa |
---

**Not:**  
Bu şema ileride `n8n` workflow’u tarafından otomatik doğrulama (schema validation) için kullanılacak.  
İstersen Supabase veya başka bir veritabanına geçişte de aynı sütun yapısı temel alınabilir.
