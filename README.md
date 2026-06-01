# AR Menü

QR kod ile açılan, uygulama indirmeye gerek duymadan çalışan AR (Augmented Reality) 3D model deneyimi.

## Nasıl Çalışır

Müşteri QR kodu telefonuyla okuttuğunda web sayfası açılır. "AR'da Gör" butonuna bastığında:

- **iPhone (Safari):** AR Quick Look devreye girer, `test.usdz` dosyasını kullanır.
- **Android (Chrome):** Scene Viewer devreye girer, `test.glb` dosyasını kullanır.

Hiçbir platformda uygulama indirme gerekmez.

---

## Klasör Yapısı

```
/AR Menu
  /docs                  GitHub Pages bu klasörü serve eder
    index.html
    /models
      test.usdz          iOS için
      test.glb           Android için
  qr.png
  README.md
```

---

## Aşama 1: iOS Testi için .usdz Dosyası

Apple'ın örnek USDZ modellerini buradan indirebilirsin:

👉 https://developer.apple.com/augmented-reality/quick-look/

Sayfada "Download" linkleri olan hazır modeller var (AirPods, sandalye, şapka vb.).
İndirdiğin dosyayı `docs/models/test.usdz` olarak kaydet.

---

## Aşama 2: Android Testi için .glb Dosyası

Aynı modelin `.glb` versiyonunu şu kaynaklardan bulabilirsin:

- **Sketchfab:** https://sketchfab.com — "Download" seçeneği olan modellerde GLB formatı mevcut.
- **Google Poly Arşivi (Icosa Gallery):** https://icosa.gallery — Google Poly'nin arşivi, GLB indirme destekler.
- **Blender:** Elinde `.usdz` varsa Blender ile `.glb`'ye dönüştürebilirsin (File → Export → glTF 2.0).

İndirdiğin dosyayı `docs/models/test.glb` olarak kaydet.

---

## GitHub Pages Kurulumu

1. Bu projeyi GitHub'a push et.
2. Repo sayfasında **Settings → Pages** bölümüne git.
3. "Source" olarak **Deploy from a branch** seç.
4. Branch: `main`, klasör: `/docs` seç, kaydet.
5. Birkaç dakika sonra GitHub sana bir URL verir:
   `https://<kullanici-adi>.github.io/<repo-adi>/`

---

## QR Kod Üretimi

### Otomatik (qrencode kuruluysa)

```bash
qrencode -o qr.png "https://<kullanici-adi>.github.io/<repo-adi>/"
```

### Manuel

Şu sitelerden herhangi birini kullan:
- https://www.qr-code-generator.com
- https://qr.io

URL olarak GitHub Pages adresini gir, PNG olarak indir, `qr.png` adıyla kaydet.

---

## Test Akışı

### Aşama 1 — iPhone Safari

1. `docs/models/test.usdz` dosyasını ekle.
2. GitHub'a push et.
3. GitHub Pages URL'ini QR koda çevir.
4. iPhone ile QR'ı okut, Safari'de sayfa açılır.
5. "AR'da Gör" butonuna bas → AR Quick Look açılır, model kamerada görünür.

### Aşama 2 — Android Chrome

1. `docs/models/test.glb` dosyasını ekle.
2. GitHub'a push et.
3. Aynı QR'ı Android telefonla okut.
4. "AR'da Gör" butonuna bas → Scene Viewer açılır, model kamerada görünür.

> Aşama 1'de Android'de sayfa açılır ama `.glb` olmadığı için AR butonu çalışmaz. Bu beklenen davranıştır.

### Aşama 3 — Gerçek Model

`test.usdz` ve `test.glb` dosyalarını gerçek yemek modelleriyle değiştir. QR kod ve URL değişmez.
