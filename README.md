# key_logger
WordLogger — Global Klavye Karakter Sayacı ve E‑posta Bildirimi
Özellikler
Global klavye hook ile yazdığınız karakterleri sayar
Eşik değere ulaşıldığında e‑posta gönderir
config.json ile yapılandırılabilir
Kısayollar: Çıkış (varsayılan) Ctrl+X, Manuel e‑posta: Ctrl+Shift+M
Log ve durum dosyaları: log.txt, state.txt
Gereksinimler
Windows 10/11
.NET 8 SDK
Hedef çerçeve: net8.0-windows
Kurulum ve Derleme
...dotnet restore
dotnet build -c Release...
Çalıştırma
Uygulamayı çalıştırın; arka planda global klavyeyi dinler
Toplam karakter sayısı eşik değerine ulaşınca e‑posta gönderir
Çıkış için kısayolu kullanın (varsayılan Ctrl+X)
Ortam değişkeni ile bazı alanları geçersiz kılabilirsiniz:
WL_THRESHOLD, WL_SMTP_HOST, WL_SMTP_PORT, WL_SMTP_SSL, WL_SMTP_USER, WL_SMTP_PASS, WL_TEST_EMAIL
Notlar:
EmailFrom ve EmailTo değerleri öncelikle config.json’dan alınır
Eşik (Threshold) karakter bazında çalışır
Kısayollar
Çıkış: Varsayılan Ctrl+X (ExitHotkeyCtrl, ExitHotkeyKey ile değiştirilebilir)
Manuel e‑posta gönderimi: Ctrl+Shift+M
Log ve Durum
log.txt: Yazılan kelime/kayıt ve e‑posta denemeleri
state.txt: Toplam karakter sayaç değeri (uygulama yeniden açıldığında devam eder)
