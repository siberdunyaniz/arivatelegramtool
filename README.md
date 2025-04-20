# Ariva E-posta ve Şikayet Aracı 📧

**Ariva E-posta ve Şikayet Aracı**, e-posta gönderme, e-posta ve proxy doğrulaması, User-Agent testi ve Telegram’a şikayet gönderme işlemlerini otomatikleştiren bir Python aracıdır. Eğitim amaçlı geliştirilmiş olup, etik ve yasal kullanım için tasarlanmıştır. 🚀

**Tasarımcı**: @AtahanArslan  
**Telegram Kanalları**: [@ArivaTools](https://t.me/ArivaTools), [@Siberduyanizz](https://t.me/Siberduyanizz)

---

## Özellikler ✨

- **E-posta Gönderme**:
  - Telegram destek ekibine toplu e-posta gönderme.
  - Belirtilen bir adrese özel e-posta gönderme.
- **E-posta Doğrulama**: Gönderici e-posta hesaplarının çalışırlığını kontrol etme.
- **Proxy Kontrolü**: Proxy sunucularının çalışırlığını test etme.
- **User-Agent Testi**: User-Agent’ların geçerliliğini doğrulama.
- **Telegram Şikayet Gönderme**: Telegram destek sitesine otomatik şikayet formu gönderme.
- **Renkli Arayüz**: Renkli terminal çıktıları (`pystyle` ile) ve renk açma/kapama seçeneği.
- **Kullanıcı Dostu Menü**: Türkçe, emojili ve kolay gezinilebilir arayüz.

---

## Kurulum ⚙️

### Gereksinimler
- **Python 3.6+**
- Gerekli Python kütüphaneleri:
  - `pystyle` (renkli terminal çıktıları için)
  - `requests` (HTTP istekleri için)

### Kurulum Adımları
1. **Depoyu Klonlayın**:
   ```bash
   git clone https://github.com/kullanici_adi/ariva-eposta-sikayet-araci.git
   cd ariva-eposta-sikayet-araci
   ```

2. **Gerekli Kütüphaneleri Yükleyin**:
   ```bash
   pip install pystyle requests
   ```

3. **Yapılandırma Dosyasını Düzenleyin**:
   - `senders`, `recipients`, `phones`, `site_emails`, `proxies`, ve `user_agents` listelerini tanımlayın (aşağıya bakın).
   - SMTP sunucuları için `smtp_servers` sözlüğünü güncelleyin.

---

## Kullanım 📚

1. **Aracı Çalıştırın**:
   ```bash
   python ariva_tool.py
   ```

2. **Menü Seçenekleri**:
   - **1) Telegram desteğine e-posta gönder**: Toplu e-posta gönderimi.
   - **2) E-postaların çalışırlığını kontrol et**: Gönderici hesaplarını doğrula.
   - **3) Belirtilen adrese e-posta gönder**: Özel e-posta gönderimi.
   - **4) Telegram sitesine şikayet gönder**: Şikayet formu gönder.
   - **5) Çıkış**: Programdan çık.
   - **6) Renkleri Aç/Kapat**: Terminal renklerini değiştir.
   - **7) Proxy'lerin çalışırlığını kontrol et**: Proxy’leri test et.
   - **8) User-Agent'ların çalışırlığını kontrol et**: User-Agent’ları doğrula.

3. **Örnek Kullanım**:
   - **E-posta Gönderme** (Seçenek 3):
     ```
     Alıcının e-posta adresini girin: ornek@hedef.com
     E-postanın konusunu girin: Test E-postası
     E-postanın metnini girin: Merhaba, bu bir test mesajıdır.
     İstek sayısını girin: 5
     ```
     Çıktı: Gönderilen her e-posta için başarı/başarısızlık mesajı.

   - **Telegram Şikayet Gönderme** (Seçenek 4):
     ```
     Şikayet metnini girin: Bu bir test şikayetidir.
     İstek sayısını girin: 3
     ```
     Çıktı: Her şikayet için başarı/başarısızlık mesajı.

---

## Yapılandırma 🛠️

Aracın çalışması için aşağıdaki değişkenleri tanımlamanız gerekir. Örnek yapılandırma:

```python
# E-posta gönderici bilgileri
senders = {
    "ornek1@gmail.com": "sifre123",
    "ornek2@yahoo.com": "sifre456"
}

# Alıcı e-posta adresleri
recipients = [
    "destek@telegram.org",
    "abuse@telegram.org"
]

# Telefon numaraları (şikayet için)
phones = [
    "+905551234567",
    "+905559876543"
]

# Şikayet formu için e-posta adresleri
site_emails = [
    "ornek1@ornek.com",
    "ornek2@ornek.com"
]

# Proxy listesi
proxies = [
    "http://proxy1:port",
    "http://proxy2:port"
]

# User-Agent listesi
user_agents = [
    "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, gibi Gecko) Chrome/91.0.4472.124 Safari/537.36",
    "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, gibi Gecko) Version/14.0 Safari/605.1.15"
]

# SMTP sunucuları
smtp_servers = {
    "gmail.com": ("smtp.gmail.com", 587),
    "yahoo.com": ("smtp.mail.yahoo.com", 587)
}
```

**Not**: Gerçek e-posta şifreleri, proxy’ler ve User-Agent’lar kullanılmalıdır. Güvenlik için şifreleri kod içinde sabit kodlamayın; ortam değişkenleri veya ayrı bir yapılandırma dosyası kullanın.

---

## Etik Kullanım ve Yasal Uyarı ⚠️

Bu araç **eğitim amaçlı** geliştirilmiştir. Aşağıdaki kurallara uymalısınız:
- **Yasal Kullanım**: Yalnızca izinli e-posta adresleri ve hizmetlerle kullanın.
- **Spam Yasak**: Toplu e-posta veya şikayet gönderimi, hizmet sağlayıcıların politikalarına aykırı olabilir.
- **Sorumluluk**: Araç kullanımı tamamen kullanıcının sorumluluğundadır. Kötüye kullanım, yasal sonuçlara yol açabilir.

**Yasal Sorumluluk Reddi**: Geliştiriciler, aracın kötüye kullanımından sorumlu değildir. Her zaman yerel yasalara ve hizmet şartlarına uygun hareket edin.

---

## Katkıda Bulunma 🤝

Katkılarınızı bekliyoruz! Yeni özellikler, hata düzeltmeleri veya iyileştirmeler için:
1. Depoyu forklayın.
2. Değişikliklerinizi bir dalda yapın (`git checkout -b ozellik/yeni-ozellik`).
3. Değişiklikleri commit edin (`git commit -m "Yeni özellik eklendi"`).
4. Pull request açın.

---

## Lisans 📜

Bu proje [MIT Lisansı](LICENSE) altında lisanslanmıştır. Detaylar için `LICENSE` dosyasına bakın.

---

## İletişim 📬

Sorularınız veya önerileriniz için:
- **Telegram**: [@ArivaTools](https://t.me/ArivaTools), [@Siberduyanizz](https://t.me/Siberduyanizz)
- **Tasarımcı**: [@AtahanArslan](https://t.me/AtahanArslan)

⭐️ Depoyu beğendiyseniz, bir yıldız bırakmayı unutmayın! ⭐️