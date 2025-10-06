WordLogger — İzinli Yazı Sayacı (TR)

WordLogger, kullanıcının açık rızasıyla yazı etkinliğini takip eden basit bir .NET konsol uygulamasıdır. Amaç, farklı uygulamalar arasında yazılan kelime miktarını ölçmek, üretkenlik takibi yapmak ve belirlediğiniz bir eşiğe ulaşıldığında sizi yerel bir bildirimle haberdar etmektir.

Varsayılan davranış: İçerik saklamaz, yalnızca toplam kelime sayısını ve uygulama durumunu yerelde tutar.

Çalışma klasöründe iki dosya oluşur:

state.txt → sayaç/durum bilgisi

metrics.txt → tarih/zaman ve kelime sayısı metrikleri
(İsteğe bağlı içerik günlüğü kapalıdır. Kurumsal/akademik senaryolarda, açık rıza ve uygun izinler sağlandığında etkinleştirilebilir.)

Özellikler

🧮 Uygulamalar arasında toplam kelime sayacı

⏱️ Başlat/Durdur ve Duraklat/Devam kısayolları

🔔 Eşik (ör. 300 kelime) aşıldığında yerel bildirim

💾 Veriler yerelde saklanır; dışa aktarım (CSV) seçeneği

🧭 Türkçe/Q klavye için temel karakter eşlemesi (genişletilebilir)

🧰 Hafif, taşınabilir, .NET 8 ile çalışır

Kurulum

Gereksinim: .NET 8 SDK veya Runtime

Kaynağı içeren klasörde standart .NET komutlarıyla çalıştırabilirsiniz:

dotnet build
dotnet run


Not: Uygulama açık kaldığı sürece sayaç çalışır. Otomatik başlangıç istenirse Windows Görev Zamanlayıcı kullanılabilir.

Kullanım

İlk açılışta “Açık rıza” ekranı gelir. Onaylamadan sayaç başlamaz.

Kısayollar:

Ctrl + Shift + P → Duraklat/Devam

Ctrl + X → Uygulamadan güvenli çıkış

Kayıt dosyaları uygulamanın çalıştığı klasörde tutulur.

Yapılandırma (Opsiyonel)

Aşağıdaki ortam değişkenleri (Environment Variables) ile davranışı özelleştirebilirsiniz:

Değişken	Açıklama	Örnek
WL_THRESHOLD	Eşik kelime sayısı	300
WL_LOCALE	Dil/Bölge ayarı (bölütleme için)	tr-TR
WL_LOG_MODE	metrics | off | content*	metrics
WL_EXPORT_CSV	Otomatik CSV dışa aktarım (0/1)	1

* content modu varsayılan olarak kapalıdır ve yalnızca açık rıza + uygun izinler ile, gizlilik politikalarına uyum sağlandığında kullanılmalıdır. İçerik günlüğü, sınav/şifre alanları gibi hassas yerleri hariç tutacak şekilde kurum politikalarına göre filtrelenmelidir.

Uzak iletim (e-posta, webhook vb.) gerekiyorsa, bunun güvenli yapılandırması kurum/ödev danışmanının sorumluluğundadır. Bu README, uzak iletim için ayrıntılı kurulum talimatı içermez.

Gizlilik, Etik ve Uyum

Bu proje eğitim/üretkenlik amaçlıdır. Aşağıdakiler zorunludur:

✅ Açık ve bilgilendirilmiş onam (ilk açılışta kayıt altına alınır)

✅ Yerel saklama, asgari veri ilkesi; yalnızca gerekli metrikler

✅ Hassas alanların (parola, finansal/sağlık verisi vb.) hariç tutulması

✅ İlgili mevzuat ve kurum politikalarına tam uyum

❌ Gizli izleme/sızma amaçlı kullanım kesinlikle yasaktır.

Bilinen Sınırlamalar

Konsol kapatılırsa izleme durur.

Türkçe klavye dışındaki özel düzenlerde bölütleme ayarı gerekebilir.

Bazı uygulamalar odak/enjekte edilemeyen alanlarda metrik üretmeyebilir.

SSS

Bu uygulama keylogger mı?
Hayır. Varsayılan modda içerik kaydetmez; yalnızca kelime sayısı metriği tutar. İçerik günlüğü, açık rıza ve gerekli izinler yoksa kullanılmamalıdır.

Veriler nereye gidiyor?
Yerelde, uygulama klasörüne. Uzak sistemlere otomatik aktarım yapmaz.

Günlüğü nasıl temizlerim?
Uygulamayı kapatıp state.txt ve metrics.txt dosyalarını silebilirsiniz.

Katkı ve Lisans

Pull request açmadan önce kısa bir açıklama ekleyin.
Lisans: MIT (istenirse değiştirilebilir).
