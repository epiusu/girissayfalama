Aşağıda, oluşturduğumuz Giriş Sayfası (Landing Page) için kapsamlı bir `README.md` kullanım rehberi bulunmaktadır. Bu rehberi projenizin kök dizininde veya WordPress tema klasörünüzde `README.md` olarak kaydedebilirsiniz.

**Tema Giriş Önizleme**
<img src="https://raw.githubusercontent.com/epiusu/girissayfalama/refs/heads/main/screenshot.jpg" width="963" height="659" class="aligncenter size-full" /></a>

```
\# 🌐 WordPress Giriş Sayfası (Landing Page)  
  
WordPress tüm temalarıyla uyumlu, giriş sayfası modern, karanlık temalı, tam responsive (mobil ve masaüstü uyumlu) bir açılış/giriş sayfası şablonu.  
  
!\[Versiyon\](https://img.shields.io/badge/versiyon-1.0.0-blue)  
!\[WordPress\](https://img.shields.io/badge/WordPress-Uyumlu-9b59b6)  
!\[Responsive\](https://img.shields.io/badge/Responsive-Mobil%20%26%20Masa%C3%BCst%C3%BC-2ecc71)  
  
---  
  
\#\# 📋 İçindekiler  
  
- \[Özellikler\](\#-özellikler)  
- \[Ekran Görüntüleri\](\#-ekran-görüntüleri)  
- \[Kurulum (WordPress Entegrasyonu)\](\#-kurulum-wordpress-entegrasyonu)  
- \[Dosya Yapısı\](\#-dosya-yapısı)  
- \[Özelleştirme Rehberi\](\#-özelleştirme-rehberi)  
  - \[Logo ve Metinler\](\#1-logo-ve-metinler)  
  - \[Arka Plan ve Renkler\](\#2-arka-plan-ve-renkler)  
  - \[Kategoriler\](\#3-kategoriler)  
  - \[Arama Fonksiyonu\](\#4-arama-fonksiyonu-canlı-arama-entegrasyonu)  
  - \[Yönlendirme (Siteye Gir Butonu)\](\#5-yönlendirme-siteye-gir-butonu)  
- \[Responsive Tasarım Detayları\](\#-responsive-tasarım-detayları)  
- \[JavaScript (JS) API\](\#-javascript-js-api)  
- \[Geliştirici Notları\](\#-geliştirici-notları)  
  
---  
  
\#\# ✨ Özellikler  
  
- \*\*Wikipedia Tarzı Merkezi Tasarım:\*\* Logo, arama çubuğu ve kategorilerin odak noktası olduğu sade arayüz.  
- \*\*Canlı (Live) Arama:\*\* Yazdıkça sonuçları anlık gösteren arama çubuğu ve kategori filtreleme.  
- \*\*Dinamik Kategori Chip'leri:\*\* Tek tıkla filtreleme, çift tıkla kaldırma özelliği.  
- \*\*Giriş Yap (Login) Modalı:\*\* Sayfa yenilemeden açılan, form doğrulamalı modern giriş ekranı.  
- \*\*Toast Bildirim Sistemi:\*\* \`alert()\` yerine kullanılan, modern ve şık bildirim mesajları.  
- \*\*Tam Responsive:\*\* Mobil cihazlardan geniş ekranlara kadar kusursuz deneyim.  
- \*\*Tema Çakışma Önlemi:\*\* WordPress'in varsayılan stilleriyle çakışmayı önleyen CSS sıfırlamaları ve admin-bar uyumu.  
  
---  
  
\#\# 📸 Ekran Görüntüleri  
  
\*(Buraya proje tamamlandığında masaüstü ve mobil ekran görüntülerini ekleyebilirsiniz)\*  
  
| Masaüstü Görünüm | Mobil Görünüm |  
|:---:|:---:|  
| \`\[Masaüstü SS\]\` | \`\[Mobil SS\]\` |  
  
---  
  
\#\# 🛠 Kurulum (WordPress Entegrasyonu)  
  
Bu şablonu WordPress sitenize entegre etmek için 2 farklı yöntem kullanabilirsiniz.   
  
\#\#\# Yöntem 1: Özel Sayfa Şablonu (Önerilen)  
  
1. WordPress tema klasörünüzde (örn. \`/wp-content/themes/sizin-temaniz/\`) \`page-giris.php\` adında bir dosya oluşturun.  
2. Dosyanın en üstüne aşağıdaki WordPress şablon yorumunu ekleyin:  
   \`\`\`php  
   \<?php  
   /\*  
   Template Name: Giriş Sayfası  
   \*/  
   ?\>
```

1. PHP yorumunun altına, size verilen HTML kodunun tamamını yapıştırın.

2. WordPress yönetici paneline (Admin) gidin → **Sayfalar → Yeni Ekle**.

3. Sayfa özellikleri panelinden **Şablon** olarak "Giriş Sayfası"nı seçin ve yayımlayın.

4. **Ayarlar → Okuma** kısmından bu sayfayı "Anasayfa" olarak atayın.

### Yöntem 2: Statik HTML Sayfası Olarak

Eğer WordPress'i kök dizine kurduysanız ve tamamen statik bir giriş sayfası istiyorsanız:

1. Kodu `index.html` olarak kaydedin.

2. `.htaccess` dosyanızda `DirectoryIndex index.html index.php` satırını ekleyerek HTML sayfasının öncelikli yüklenmesini sağlayın.


## 📁 Dosya Yapısı

Şablonu WordPress standartlarına göre ayırmak isterseniz şu yapıyı kullanın:

```
sizin-temaniz/  
├── page-giris.php          \# Ana HTML şablonu  
├── assets/  
│   ├── css/  
│   │   └── anasayfa.css    \# \<style\> içindeki CSS kodları buraya taşınacak  
│   └── js/  
│       └── anasayfa.js     \# \<script\> içindeki JS kodları buraya taşınacak
```

**WP Entegrasyonu için Çağırma Örneği (page-giris.php):**

```
\<?php  
/\*  
Template Name: Giriş Sayfası  
\*/  
wp\_enqueue\_style('anasayfa-css', get\_template\_directory\_uri() . '/assets/css/anasayfa.css');  
wp\_enqueue\_script('anasayfa-js', get\_template\_directory\_uri() . '/assets/js/anasayfa.js', array(), '1.0', true);  
?\>  
\<!-- HTML kodları buraya --\>
```


## 🎨 Özelleştirme Rehberi

### 1. Logo ve Metinler

Logoyu ve başlıkları değiştirmek için HTML'de şu alanı bulun:

```
\<div class="logo-globe\_\_icon"\>...\</div\>  
\<div class="logo-text"\>  
    \<h1 class="logo-text\_\_title"\>Site Adı\</h1\>  
    \<p class="logo-text\_\_subtitle"\>Bilgiye Giden Yol\</p\>  
\</div\>
```

- **Logoyu görsel yapmak için:** `\<i data-lucide="globe"\>` kısmını silip `\<img src="logo.png" alt="Logo"\>` ekleyebilirsiniz.

### 2. Arka Plan ve Renkler

Tüm sayfa renkleri CSS'deki `:root` değişkenleriyle kontrol edilir:

```
:root \{  
    --primary: \#3366CC;       /\* Ana renk (Butonlar, odak halleri) \*/  
    --primary-hover: \#2952a3; /\* Hover rengi \*/  
    --bg-dark: \#0a0a0a;       /\* Sayfa arka planı \*/  
    --text-primary: \#ffffff;  /\* Ana metin rengi \*/  
\}
```

- **Arka Plan Görseli Eklemek:** `.landing-bg` içerisine görsel eklemek için CSS'de `.landing-bg\_\_image` kısmındaki `opacity: 0.15` ve `filter: saturate(0.3)` değerlerini ihtiyacınıza göre değiştirin.

### 3. Kategoriler

Kategori butonlarını düzenlemek için HTML'de `categoriesList` bölümünü bulun.

```
\<button class="category-chip" data-category="teknoloji"\>  
    \<i data-lucide="cpu" class="category-chip\_\_icon"\>\</i\>  
    Teknoloji  
\</button\>
```

- **Yeni kategori eklemek:** Bu yapıyı kopyalayıp yapıştırın. **Önemli:** `data-category` özelliğine benzersiz bir İngilizce değer verin (örn: `data-category="spor"`).

### 4. Arama Fonksiyonu (Canlı Arama Entegrasyonu)

Varsayılan kodda arama örnek verilerle (sampleData) çalışmaktadır. Bunu WordPress'inize bağlamak için:

`anasayfa.js` dosyasındaki `performSearch` fonksiyonunu bulun ve WP AJAX ile değiştirin:

```
function performSearch(query) \{  
    query = query.trim();  
    if (query.length \< 2) \{ searchResults.classList.remove('active'); return; \}  
  
    // WordPress AJAX isteği  
    fetch('/wp-admin/admin-ajax.php', \{  
        method: 'POST',  
        headers: \{ 'Content-Type': 'application/x-www-form-urlencoded' \},  
        body: \`action=live\_search&s=$\{encodeURIComponent(query)\}&category=$\{activeCategory || ''\}\`  
    \})  
    .then(res =\> res.json())  
    .then(data =\> \{  
        renderResults(data.results, query);  
    \});  
\}
```

### 5. Yönlendirme (Siteye Gir Butonu)

Kullanıcı "Siteye Gir" butonuna bastığında anasayfaya yönlendirmek için JS'deki ilgili alanı bulun:

```
enterSiteBtn.addEventListener('click', (e) =\> \{  
    e.preventDefault();  
    // Aşağıdaki satırın yorumunu kaldırın:  
    // window.location.href = '/anasayfa/';   
\});
```


## 📱 Responsive Tasarım Detayları

| Özellik | Masaüstü (\>1024px) | Tablet (641-1024px) | Mobil (\<640px) |
| - | - | - | - |
| **Logo Boyutu** | 140px | 130px | 110px |
| **Arama Kutusu** | 56px yükseklik | 54px yükseklik | 50px yükseklik |
| **Butonlar** | Yan yana | Yan yana | Alt alta (Tam genişlik) |
| **Kategori** | Ortada sıralı | Sarmal (Wrap) | Sarmal, küçük font |
| **Footer** | Sabit alt kısımda | Sabit alt kısımda | Akış içinde |



## 💻 JavaScript (JS) API

Şablonda özel olarak geliştirilmiş **Toast Bildirim Sistemi** bulunur. Kendi eklentilerinizi eklerken kullanıcıya bildirim vermek için kullanabilirsiniz:

```
// Kullanımı  
showToast('Mesajınız', 'tür', süre);  
  
// Türler: 'success' (Yeşil), 'error' (Kırmızı), 'info' (Mavi)  
// Süre: Milisaniye cinsinden (varsayılan: 3000ms)  
  
showToast('Başarıyla kaydedildi!', 'success');   
showToast('Bir hata oluştu.', 'error', 5000);
```


## 🧑💻 Geliştirici Notları

1. **Lucide Icons:** Proje [Lucide Icons](https://lucide.dev/) kullanmaktadır. Yeni bir ikon eklemek için HTML'e `\<i data-lucide="ikon-adi"\>\</i\>` yazmanız yeterlidir. JS otomatik olarak ikonu render edecektir.

2. **WordPress Admin Bar:** CSS, WordPress admin barının göründüğü durumlarda sayfanın aşağı kaymasını engellemek için `body.admin-bar` hack'ini içermektedir.

3. **Tema Çakışmaları:** Eğer temanızın CSS'i bu sayfanın tasarımını bozuyorsa, CSS dosyasındaki kuralları `!important` ile güçlendirebilir veya `.landing-page` kapsayıcısına daha spesifik seçiciler ekleyebilirsiniz.

```
  
Bu içerik, hem bir yazılımcının kodu anlaması ve geliştirmesi için rehber niteliğindedir, hem de WordPress site yöneticilerinin kodu sitelerine entegre etmesi için adım adım yol haritası sunar.
```

