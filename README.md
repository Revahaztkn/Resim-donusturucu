<p align="center">
  <img src="gorsel.png" width="160" alt="Resim Dönüştürücü">
</p>

<h1 align="center">Resim Dönüştürücü (Image Converter)</h1>

<p align="center">
  <a href="#türkçe">Türkçe</a> | <a href="#english">English</a>
</p>

---

## Türkçe

Windows için basit ve çevrimdışı çalışan resim dönüştürücü. `Resim Dönüştürücü.exe` dosyasına çift tıkla, tarayıcında açılır ve resimlerini **tamamen bilgisayarında** dönüştürür. Hiçbir dosya internete yüklenmez.

### Özellikler

- HEIC/HEIF dosyalarını JPEG, PNG, WebP ve BMP'ye dönüştürür; JPEG/PNG/WebP/BMP formatları da birbirine dönüştürülebilir
- Kaynak ve hedef format seçimi, yanlış formattaki dosyalar net bir mesajla reddedilir
- En yüksek kalite, kalite ayarı yok
- Sınırsız dosya, sayfanın herhangi bir yerine sürükle-bırak, klasör desteği
- Dosyaları tek tek indir veya **Tümünü İndir** (ZIP yok)
- Türkçe (varsayılan) ve İngilizce arayüz, karanlık ve aydınlık tema

### Kullanım

1. **Releases** bölümünden zip dosyasını indir ve çıkar.
2. `Resim Dönüştürücü.exe` dosyasını çalıştır, tarayıcın açılır.
3. Kaynak ve hedef formatı seç, resimleri sayfaya bırak.
4. Dönüşen dosyaları tek tek veya **Tümünü İndir** ile indir.
5. Uygulamadan çıkmak için tarayıcı sekmesini kapat.

### Windows SmartScreen uyarısı

Dosya dijital olarak imzalı olmadığı için Windows "Windows kişisel bilgisayarınızı korudu" uyarısı gösterebilir. Bu, tanınmayan her yeni uygulama için normaldir.

1. **Ek bilgi** yazısına tıkla.
2. **Yine de çalıştır** butonuna bas.

Alternatif olarak exe'ye sağ tıklayıp **Özellikler** bölümünde **Engellemeyi kaldır** kutusunu işaretleyebilirsin. İndirdiğin dosyayı release notlarındaki SHA256 değeriyle doğrulayabilir ya da kaynak koddan kendin derleyebilirsin.

### Notlar

- JPEG ve WebP kayıplı formatlardır. En yüksek kalite kullanılır ama çok küçük bir kayıp kaçınılmazdır. PNG ve BMP kayıpsızdır.
- EXIF bilgileri (çekim tarihi, konum vb.) korunmaz.
- HEIC dosyası oluşturma (JPG'den HEIC'e) desteklenmiyor.

### Kaynaktan derleme

[Go](https://go.dev/) 1.22 veya üstü gerekir.

```
GOOS=windows GOARCH=amd64 go build -ldflags "-s -w -H windowsgui" -o "Resim Dönüştürücü.exe" .
```

Uygulama simgesi ve sürüm bilgisi `rsrc_windows_amd64.syso` dosyasıyla gömülür (`app.rc` ve `icon.ico` dosyalarından üretilir, ör. `x86_64-w64-mingw32-windres` ile). Go bu dosyayı otomatik kullanır. Hata ayıklamak için `-H windowsgui` bayrağını kaldırıp konsollu derleyebilirsin.

### Teşekkürler

Dönüştürme motoru [heic-to](https://github.com/hoppergee/heic-to) (LGPL-3.0) kütüphanesidir, o da [libheif](https://github.com/strukturag/libheif) üzerine kuruludur. Ayrıntılar için `THIRD_PARTY_NOTICES.md` dosyasına bak.

### Lisans

MIT, bkz. `LICENSE`. Üçüncü taraf bileşenler kendi lisanslarını korur.

---

## English

A simple, offline image converter for Windows. Double-click `Resim Dönüştürücü.exe`, it opens in your browser and converts your images **locally on your computer**. No file is ever uploaded.

### Features

- Converts HEIC/HEIF to JPEG, PNG, WebP and BMP; JPEG/PNG/WebP/BMP can also be converted between each other
- Source and target format selection, files in the wrong format are rejected with a clear message
- Maximum quality output, no quality slider
- Unlimited number of files, drag and drop anywhere on the page, folder support
- Download each file separately or use **Download All** (no ZIP)
- Turkish (default) and English interface, dark and light theme

### Usage

1. Download the zip from **Releases** and extract it.
2. Run `Resim Dönüştürücü.exe`, your browser opens.
3. Pick the source and target format, drop your images on the page.
4. Download the converted files one by one or with **Download All**.
5. Close the browser tab to quit the app.

### Windows SmartScreen warning

Because the file is not digitally signed, Windows may show "Windows protected your PC". This is normal for any new, unrecognized app.

1. Click **More info**.
2. Click **Run anyway**.

Alternatively, right-click the exe, open **Properties** and tick **Unblock**. You can verify your download with the SHA256 hash in the release notes, or build it yourself from source.

### Notes

- JPEG and WebP are lossy formats. Output uses the highest quality setting, but a tiny loss is inherent. PNG and BMP are lossless.
- EXIF metadata (capture date, location, etc.) is not preserved.
- Creating HEIC files (JPG to HEIC) is not supported.

### Build from source

Requires [Go](https://go.dev/) 1.22 or newer.

```
GOOS=windows GOARCH=amd64 go build -ldflags "-s -w -H windowsgui" -o "Resim Dönüştürücü.exe" .
```

The app icon and version info are embedded through `rsrc_windows_amd64.syso` (generated from `app.rc` and `icon.ico`, e.g. with `x86_64-w64-mingw32-windres`). Go picks it up automatically. For debugging, remove `-H windowsgui` to get a console build.

### Credits

Conversion is powered by [heic-to](https://github.com/hoppergee/heic-to) (LGPL-3.0), which is built on [libheif](https://github.com/strukturag/libheif). See `THIRD_PARTY_NOTICES.md`.

### License

MIT, see `LICENSE`. Third-party components keep their own licenses.
