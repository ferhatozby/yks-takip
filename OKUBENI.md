# YKS Takip - Android Uygulaması

Bu klasör, "YKS Takip" web uygulamanı gerçek bir Android uygulamasına (.apk) dönüştürmek için hazırlanmış bir **Capacitor** projesidir. Kod hazır; sadece bilgisayarında Android Studio ile derlemen gerekiyor (bunu ben senin yerine derleyemiyorum çünkü APK derlemek Google'ın sunucularına erişim gerektiriyor).

## Gerekenler
- Bir bilgisayar (Windows, Mac veya Linux)
- **Android Studio** (ücretsiz): https://developer.android.com/studio
- **Node.js** (ücretsiz): https://nodejs.org (LTS sürümünü indir)
- İnternet bağlantısı (ilk kurulumda bağımlılıklar indirilecek)

## Adım Adım

### 1. Android Studio'yu kur
İndirip kur, ilk açılışta "Standard" kurulum seçeneğini seç. Bu, Android SDK'yı otomatik kurar. 15-20 dakika sürebilir.

### 2. Node.js'i kur
Normal bir program gibi kur, kurulumdan sonra bir terminal/CMD açıp şunu yaz:
```
node -v
```
Bir sürüm numarası görüyorsan kurulum tamamdır.

### 3. Bu klasörü bilgisayarına indir
Bu klasörü (yks-android-app) bilgisayarına indir ve içine bir terminal/CMD ile gir:
```
cd yks-android-app
```

### 4. Bağımlılıkları kur
```
npm install
```

### 5. Android Studio ile aç
```
npx cap open android
```
Bu komut Android Studio'yu otomatik açacak ve projeyi yükleyecek. İlk açılışta Gradle senkronizasyonu biraz zaman alabilir (5-15 dk, internet hızına bağlı) — sabırla bekle, alt kısımda ilerleme çubuğunu görürsün.

### 6. APK oluştur
Android Studio açıldıktan ve Gradle senkronizasyonu bittikten sonra:
- Üst menüden **Build → Build Bundle(s) / APK(s) → Build APK(s)** seç
- Derleme bitince sağ altta çıkan bildirimden "locate" a tıkla, APK dosyasını bulursun
- APK genelde şurada olur: `android/app/build/outputs/apk/debug/app-debug.apk`

### 7. Telefonuna yükle
Bu `app-debug.apk` dosyasını telefonuna (WhatsApp, e-posta, USB kablosu, Google Drive — hangisi kolaysa) aktar, telefonda dosyaya dokun, "Bilinmeyen kaynaklardan yükleme"ye izin ver (telefon sorar), yükle. Artık gerçek bir uygulama ikonu olarak telefonunda!

## Uygulamayı güncellemek istersen
Web uygulamasının kodu `www/index.html` dosyasında. Orayı değiştirdikten sonra:
```
npx cap sync android
```
çalıştır, sonra Android Studio'da tekrar Build → Build APK(s) yap.

## Play Store'a yayınlamak istersen (opsiyonel, ileri seviye)
Bu ayrı bir süreç: Google Play Console'da geliştirici hesabı açman gerekir (tek seferlik ~25$ ücret), uygulamayı "release" modda imzalaman (signing key oluşturman) ve Play Store politikalarına uygun hale getirmen gerekir. İstersen bu konuda da adım adım yardımcı olabilirim, ama şimdilik kendi telefonunda test etmek için yukarıdaki adımlar yeterli.

## Sorun yaşarsan
- Gradle senkronizasyonu hata verirse: Android Studio'yu güncel tut, "File → Invalidate Caches / Restart" dene.
- "SDK not found" hatası: Android Studio → Settings → Android SDK'dan bir SDK sürümü seçili olduğundan emin ol.
- Bana ekran görüntüsüyle hata mesajını gösterirsen, birlikte çözeriz.
