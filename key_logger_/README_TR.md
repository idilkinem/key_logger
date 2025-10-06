## WordLogger (Türkçe)

Bu basit C# konsol uygulaması, Windows üzerinde global klavye kancası (WH_KEYBOARD_LL) ile yazdığınız kelimeleri uygulama odağından bağımsız olarak toplar, toplam kelime sayısını takip eder ve eşik (varsayılan 300) aşıldığında SMTP üzerinden e‑posta gönderir. Log ve durum dosyaları doğrudan uygulamanın çalıştığı klasörde oluşturulur: `log.txt` ve `state.txt`.

### Kurulum

1. .NET 8 Runtime veya SDK kurulu olmalı.
2. Bu klasörde komut çalıştırın:
```bash
dotnet run
```

> Not: Konsol açık kaldığı sürece çalışır. Başlangıca eklemek isterseniz Görev Zamanlayıcı kullanılabilir.

### Yapılandırma (Opsiyonel Çevre Değişkenleri)

- `WL_THRESHOLD`: kelime eşiği (örn: 300)
- `WL_SMTP_HOST`: SMTP sunucu (vars: smtp.gmail.com)
- `WL_SMTP_PORT`: SMTP port (vars: 587)
- `WL_SMTP_SSL`: TLS/SSL (true/false)
- `WL_SMTP_USER`: SMTP kullanıcı adı
- `WL_SMTP_PASS`: SMTP parola
- `WL_EMAIL_FROM`: Gönderici adresi
- `WL_EMAIL_TO`: Alıcı adresi
- `WL_TEST_EMAIL`: Uygulama açılışında test e-postası gönder (1/true)

### Yapılandırma (config.json)

`config.json` dosyası ile kodu değiştirmeden ayar yapabilirsiniz:

- Threshold, SMTP (host/port/ssl/user/pass), gönderici/alıcı
- Çıkış kısayolu: `ExitHotkeyCtrl` (true/false) ve `ExitHotkeyKey` (örn: "X")
- Dosya adları: `LogFileName`, `StateFileName`
- E-posta başlığı/gövdesi şablonları: `EmailSubjectTemplate`, `EmailBodyTemplate` (kullanılabilir değişkenler: `{count}`, `{date}`, `{log}`)

Örnek `config.json` bu proje kökünde yer alıyor; arkadaşınız kendi e-posta ve şifre (uygulama şifresi) ile doldurup kullanabilir.

### Güvenlik Uyarısı

Bu örnek uygulama eğitim amaçlıdır. Şifreleri düz metin olarak saklamak/commitlemek güvenli değildir. Üretimde Windows Credential Manager, kullanıcı gizliliği ve açık onam gibi gereklilikleri gözetin.

### Kısayol

- Uygulamayı kapatmak için: Ctrl + X
- Kapanışta kısa süreli bir komut penceresi açılıp kapanır.

### Bilinen Sınırlamalar

- Sadece temel harf/rakam ve birkaç noktalama işareti eşlenir. Türkçe klavye tüm karakterlerini kapsayacak şekilde genişletilebilir.
- Konsol kapatılırsa izleme durur.


