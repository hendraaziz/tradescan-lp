# Facebook Ads URL Templates untuk TradeScan

## 1. **Promo Launch URL**

### Basic Template:
```
https://tradescan.id/promo-launch.html?utm_source=facebook&utm_medium=paid_social&utm_campaign=launch_promo_feb2026&utm_content={{adset.name}}&utm_term={{ad.name}}
```

### With All Parameters:
```
https://tradescan.id/promo-launch.html?utm_source=facebook&utm_medium=paid_social&utm_campaign={{campaign.name}}&utm_content={{adset.name}}&utm_term={{ad.name}}&placement={{placement}}&platform={{site_source_name}}
```

---

## 2. **Promo Terbatas URL**

### Basic Template:
```
https://tradescan.id/promo-terbatas.html?utm_source=facebook&utm_medium=paid_social&utm_campaign=promo_terbatas&utm_content={{adset.name}}&utm_term={{ad.name}}
```

### With Audience Targeting:
```
https://tradescan.id/promo-terbatas.html?utm_source=facebook&utm_medium=paid_social&utm_campaign=promo_terbatas&utm_content={{adset.name}}&utm_term={{ad.name}}&audience={{adset.name}}
```

---

## 3. **Parameter Explanation**

### **UTM Parameters** (Google Analytics Standard):

| Parameter | Value | Purpose |
|-----------|-------|---------|
| `utm_source` | `facebook` | Traffic source identifier |
| `utm_medium` | `paid_social` atau `cpc` | Marketing medium type |
| `utm_campaign` | `launch_promo_feb2026` | Campaign identifier (custom) |
| `utm_content` | `{{adset.name}}` | Ad set/creative variant |
| `utm_term` | `{{ad.name}}` | Ad name or keyword |

### **Facebook Dynamic Parameters**:

| Parameter | Description | Example |
|-----------|-------------|---------|
| `{{campaign.name}}` | Campaign name auto-filled | "TradeScan Launch" |
| `{{campaign.id}}` | Unique campaign ID | "120210987654321" |
| `{{adset.name}}` | Ad set name | "Traders 25-45" |
| `{{adset.id}}` | Unique ad set ID | "120210987654322" |
| `{{ad.name}}` | Ad name | "Video Ad 1" |
| `{{ad.id}}` | Unique ad ID | "120210987654323" |
| `{{placement}}` | Where ad shown | "Feed", "Stories" |
| `{{site_source_name}}` | Platform | "Facebook", "Instagram" |

---

## 4. **Campaign Examples**

### **Campaign 1: Launch Promo - Video Ads**
```
Destination URL:
https://tradescan.id/promo-launch.html?utm_source=facebook&utm_medium=paid_social&utm_campaign=launch_video_feb2026&utm_content={{adset.name}}&utm_term={{ad.name}}&creative=video
```

**Use Case:** Video ads untuk traders baru

---

### **Campaign 2: Promo Terbatas - Image Carousel**
```
Destination URL:
https://tradescan.id/promo-terbatas.html?utm_source=facebook&utm_medium=paid_social&utm_campaign=terbatas_carousel&utm_content={{adset.name}}&utm_term={{ad.name}}&creative=carousel
```

**Use Case:** Carousel ads dengan multiple images

---

### **Campaign 3: Retargeting Campaign**
```
Destination URL:
https://tradescan.id/promo-terbatas.html?utm_source=facebook&utm_medium=retargeting&utm_campaign=retarget_visitors&utm_content={{adset.name}}&utm_term={{ad.name}}&type=retarget
```

**Use Case:** Retargeting website visitors yang belum convert

---

## 5. **How to Use in Facebook Ads Manager**

### Step-by-Step:

1. **Create Campaign** → Choose objective (Traffic/Conversions)
2. **Ad Set Level** → Define audience, placement, budget
3. **Ad Level** → Create ad creative
4. **Destination Section** → Paste URL template
5. **Preview** → Facebook will show resolved URL with actual values
6. **Publish** → Facebook auto-appends `fbclid` parameter

---

## 6. **Testing URLs**

### Before Publishing:
Test URL manually to ensure landing page loads correctly:

```bash
# Test Launch Promo
https://tradescan.id/promo-launch.html?utm_source=facebook&utm_medium=test&utm_campaign=test

# Test Promo Terbatas  
https://tradescan.id/promo-terbatas.html?utm_source=facebook&utm_medium=test&utm_campaign=test
```

---

## 7. **Tracking in Google Analytics**

These UTM parameters will appear in:
- **Acquisition** → **All Traffic** → **Source/Medium**
- **Acquisition** → **Campaigns** → **All Campaigns**

Filter by:
- Source: `facebook`
- Medium: `paid_social` or `cpc`
- Campaign: Your campaign name

---

## 8. **Best Practices** ✅

1. **Consistent Naming:** Use lowercase, underscores (no spaces)
2. **Descriptive Campaigns:** `launch_promo_feb2026` better than `promo1`
3. **Test Before Launch:** Verify URL loads correctly
4. **Track Conversions:** Set up Facebook Pixel events (already installed: `1492165862470149`)
5. **Use Dynamic Parameters:** Let Facebook auto-fill ad details
6. **Keep it Short:** Too many parameters can break on some devices

---

## 9. **Quick Copy-Paste Templates** 🚀

### Template A: Basic (Recommended for most campaigns)
```
https://tradescan.id/promo-terbatas.html?utm_source=facebook&utm_medium=paid_social&utm_campaign={{campaign.name}}&utm_content={{adset.name}}
```

### Template B: Detailed Tracking
```
https://tradescan.id/promo-terbatas.html?utm_source=facebook&utm_medium=paid_social&utm_campaign={{campaign.name}}&utm_content={{adset.name}}&utm_term={{ad.name}}&placement={{placement}}
```

### Template C: With Custom Parameters
```
https://tradescan.id/promo-terbatas.html?utm_source=facebook&utm_medium=paid_social&utm_campaign={{campaign.name}}&utm_content={{adset.name}}&offer=limited_time&ref=fb_ads
```

---

## 10. **Advanced: Custom Conversion Tracking**

For specific actions (signup, purchase), add event triggers:

```javascript
// On landing page load
fbq('track', 'ViewContent', {
  content_name: 'Promo Terbatas',
  content_category: 'Limited Offer',
  utm_source: getUrlParameter('utm_source'),
  utm_campaign: getUrlParameter('utm_campaign')
});

// On CTA button click
fbq('track', 'InitiateCheckout', {
  content_name: 'Promo Signup',
  value: 99000,
  currency: 'IDR'
});
```

---

## Notes:
- ✅ Meta Pixel already installed: `1492165862470149`
- ✅ Landing pages ready: `promo-launch.html`, `promo-terbatas.html`
- ⚠️ Test all URLs before launching campaign
- 📊 Monitor performance in Facebook Events Manager
