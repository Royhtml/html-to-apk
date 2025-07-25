# **HTML to APK Converter with Cordova**  
`pip install html-to-apk`

# **Running*** 
`html-to-apk`


**Aplikasi Konversi Proyek Web ke Aplikasi Android (APK) dengan Apache Cordova**  

<img src="cordova.gif" width="auto" height="auto">  

<a href="https://pypi.org/project/html-to-apk/">Open Project on PYPI</a>  

---  

## **📋 Daftar Isi**  
1. [Deskripsi Proyek](#-deskripsi-proyek)  
2. [Fitur Utama](#-fitur-utama)  
3. [Algoritma & Arsitektur Cordova](#-algoritma--arsitektur-cordova)  
4. [Persyaratan Sistem](#-persyaratan-sistem)  
5. [Panduan Instalasi](#-panduan-instalasi)  
6. [Cara Penggunaan](#-cara-penggunaan)  
7. [Troubleshooting](#-troubleshooting)  
8. [Kontribusi](#-kontribusi)  
9. [Lisensi](#-lisensi)  

---  

## **📌 Deskripsi Proyek**  
**HTML to APK Converter** adalah alat berbasis Python yang mengubah proyek web (HTML, CSS, JS) menjadi aplikasi Android (APK) menggunakan **Apache Cordova**.  

🔹 **Keunggulan:**  
✔ **Tanpa coding** – GUI sederhana untuk konfigurasi  
✔ **Dukungan plugin Cordova** (Kamera, GPS, Notifikasi, dll.)  
✔ **Build langsung dari folder HTML**  
✔ **Customizable** (Nama App, Package ID, Ikon, Splash Screen)  

---  

## **✨ Fitur Utama**  
✅ **Konversi ke APK**  
- Build untuk Android (min SDK 21+)  
- Optimasi dengan **Gradle**  
- Signing APK otomatis (debug/release)  

✅ **Dukungan Cordova Plugin**  
- Akses **Device API** (Kamera, GPS, File System)  
- **Network Information**, Vibration, StatusBar  
- Tambahkan plugin via GUI  

✅ **Konfigurasi Aplikasi**  
- **Nama Aplikasi** & **Package ID** (e.g., `com.example.app`)  
- **Ikon & Splash Screen** (multi-resolusi)  
- **Orientasi Layar** (Portrait/Landscape)  
- **Versi App** (Version Code & Name)  

✅ **Preview Mode**  
- Jalankan di **Emulator Android**  
- Debug via **Chrome DevTools**  

✅ **Logging & Error Handling**  
- Log detail proses build  
- Deteksi error **Java SDK, Gradle, Cordova**  

---  

## **⚙ Algoritma & Arsitektur Cordova**  

### **📂 Alur Kerja**  
```mermaid
graph TD
    A[Input: Folder HTML] --> B[Init Cordova Project]
    B --> C[Copy Web Assets to www/]
    C --> D[Konfigurasi config.xml]
    D --> E[Tambahkan Plugin Cordova]
    E --> F[Build APK via Cordova CLI]
    F --> G[Output APK]
```  

### **🔧 Proses Konversi**  
1. **Inisialisasi Proyek Cordova**  
   ```bash
   cordova create myapp com.example.myapp MyApp
   ```  
2. **Salin File HTML ke `www/`**  
   ```bash
   cp -R /path/to/html/* ./myapp/www/
   ```  
3. **Konfigurasi `config.xml`**  
   ```xml
   <widget id="com.example.myapp" version="1.0.0">
       <name>MyApp</name>
       <icon src="res/icon.png" />
       <splash src="res/splash.png" />
   </widget>
   ```  
4. **Tambahkan Platform Android**  
   ```bash
   cordova platform add android
   ```  
5. **Build APK**  
   ```bash
   cordova build android --release
   ```  

---  

## **�️ Persyaratan Sistem**  
| Komponen | Versi Minimal | Catatan |  
|----------|--------------|---------|  
| **OS** | Windows 10 / macOS / Linux (x64) | - |  
| **Python** | 3.6+ | Untuk GUI |  
| **Node.js** | 14.x+ | Wajib untuk Cordova |  
| **Java JDK** | 8+ | Diperlukan untuk Android SDK |  
| **Android SDK** | API Level 21+ | `adb`, `gradle` harus di PATH |  
| **RAM** | 4GB+ | Lebih baik 8GB untuk emulator |  

---  

## **📥 Panduan Instalasi Terminal**  
```bash
pip install html-to-apk
html-to-apk
```  

## **📥 Panduan Instalasi Lengkap**  

### **1️⃣ Instal Python & PIP**  
```bash
python --version  # Pastikan Python 3.6+
pip --version
```  

### **2️⃣ Instal Node.js & npm**  
```bash
node --version  # Minimal v14
npm --version
```  

### **3️⃣ Instal Cordova Global**  
```bash
npm install -g cordova
```  

### **4️⃣ Instal Android SDK**  
- Download **Android Studio** [di sini](https://developer.android.com/studio)  
- Set **PATH** untuk `adb`, `gradle`:  
  ```bash
  export PATH=$PATH:$ANDROID_HOME/platform-tools
  export PATH=$PATH:$ANDROID_HOME/tools/bin
  ```  

### **5️⃣ Instal Java JDK**  
- Download [JDK 8+](https://adoptium.net/)  
- Set `JAVA_HOME`:  
  ```bash
  export JAVA_HOME=/path/to/jdk
  ```  

### **6️⃣ Verifikasi Instalasi**  
```bash
cordova requirements  # Pastikan semua tercentang
```  

---  

## **🖱 Cara Penggunaan**  

### **1️⃣ Tab Settings**  
- **HTML Folder**: Pilih folder berisi `index.html`  
- **App Name**: Nama aplikasi  
- **Package ID**: Format `com.nama.anda`  
- **Output Folder**: Lokasi penyimpanan APK  

### **2️⃣ Tab Cordova Options**  
- **Platform**: Android (default)  
- **Plugins**: Pilih plugin Cordova (e.g., Camera, Geolocation)  
- **Ikon & Splash Screen**: Upload gambar (PNG)  

### **3️⃣ Tab Preview**  
- **Run on Emulator**: Jalankan di emulator Android  
- **Debug via Browser**: Buka di Chrome DevTools  

### **4️⃣ Build APK**  
- Klik **"Build APK"**  
- APK akan tersimpan di `platforms/android/app/build/outputs/apk/`  

---  

## **⚠ Troubleshooting**  

| Masalah | Solusi |  
|---------|--------|  
| **Cordova tidak terdeteksi** | Jalankan `npm install -g cordova` |  
| **Error Android SDK** | Pastikan `ANDROID_HOME` sudah benar |  
| **Gradle Build Failed** | Update Gradle: `gradlew wrapper --gradle-version 7.x` |  
| **APK tidak terinstall** | Aktifkan **USB Debugging** di perangkat |  

---  

## **🤝 Kontribusi**  
- **Laporkan bug** di [Issues](https://github.com/Royhtml/html-to-apk/issues)  
- **Ajukan fitur** via Pull Request  

---  

## **📜 Lisensi**  
**MIT License** – Bebas digunakan untuk proyek komersial & open source.  

---  
**🚀 Selamat Membangun Aplikasi Android!**  

### **Catatan Tambahan:**  
- Untuk **signing APK release**, buat file `keystore` terlebih dahulu:  
  ```bash
  keytool -genkey -v -keystore myapp.keystore -alias myapp -keyalg RSA -keysize 2048 -validity 10000
  ```  
- Gunakan **Android Studio** untuk debugging lanjutan.
