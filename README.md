<p align="center">
  <img src="assets/banner.svg" width="100%" alt="Hilal Yöney · Siber Güvenlik Stajyer Adayı">
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/hilalyoney/"><img src="https://img.shields.io/badge/LinkedIn-Hilal%20Y%C3%B6ney-161b22?style=for-the-badge&logo=linkedin&logoColor=22d3ee&labelColor=0d1117" alt="LinkedIn"></a>
  <a href="mailto:hilalyoney@hotmail.com"><img src="https://img.shields.io/badge/E--posta-hilalyoney%40hotmail.com-161b22?style=for-the-badge&logo=maildotru&logoColor=22d3ee&labelColor=0d1117" alt="E-posta"></a>
  <a href="https://proofsender.com"><img src="https://img.shields.io/badge/Proje-proofsender.com-161b22?style=for-the-badge&logo=googlechrome&logoColor=22d3ee&labelColor=0d1117" alt="ProofSender"></a>
  <img src="https://img.shields.io/badge/Konum-%C4%B0stanbul,%20T%C3%BCrkiye-161b22?style=for-the-badge&logo=googlemaps&logoColor=22d3ee&labelColor=0d1117" alt="Konum">
</p>

<p align="center">
  <b>Açık olduğum roller</b> &nbsp;·&nbsp; Siber Güvenlik Stajı &nbsp;·&nbsp; Junior SOC Analyst &nbsp;·&nbsp; IT Destek / Help Desk &nbsp;·&nbsp; Sağlık BT &nbsp;·&nbsp; <i>İstanbul / Hibrit / Uzaktan</i>
</p>

---

## Hakkımda

Dokuz yıla yakın ameliyathanede **anestezi teknikeri** olarak çalıştım. İşim, monitördeki sinyalleri sürekli izlemek, normalden sapmayı erken fark etmek, protokole uymak ve her uygulamayı kayıt altına almaktı. Bugün aynı refleksi **siber güvenliğe** taşıyorum: sinyal artık hastadan değil, sistemlerden ve e-postalardan geliyor.

Kariyer değişikliğimi kendim planladım. **Bilgisayar Programcılığı** önlisansını onur öğrencisi olarak bitirdim, 120 saatlik siber güvenlik eğitimi aldım, Cisco'nun Introduction to Cybersecurity kursunu tamamladım; TryHackMe'de 12 oda bitirdim, Hack The Box'ta log incelemesine dayalı Brutus senaryosunu çözdüm. Öğrendiklerimi denemek için tek başıma, **Claude Code** ile bir e-posta güvenliği ürünü geliştirdim: **ProofSender**.

Mentorluk veren, yapılandırılmış bir güvenlik ekibinde **L1 SOC / güvenlik stajyeri** olarak başlamak istiyorum.

<table>
  <tr>
    <th align="left">🛡️ Güvenlik Temelleri</th>
    <th align="left">✉️ E-posta Güvenliği</th>
    <th align="left">🐧 Linux &amp; Ağ</th>
    <th align="left">🏥 Ameliyathaneden Gelen</th>
  </tr>
  <tr>
    <td valign="top">Saldırı vektörleri ve savunma<br>Log ve olay analizi (temel)<br>Kimlik doğrulama, erişim kontrolü<br>Kriptografi, hash, şifreleme</td>
    <td valign="top">SPF · DKIM · DMARC<br>MTA-STS · TLS-RPT · DNSSEC<br>Oltalama ve benzer alan adı<br>Sahte fatura / IBAN sinyalleri</td>
    <td valign="top">Linux komutları, Kali (temel)<br>TCP/IP, subnetting (temel)<br>DNS, HTTP/HTTPS<br>Nmap ile port ve servis keşfi</td>
    <td valign="top">Sürekli izleme ve alarm takibi<br>Baskı altında sakin karar<br>Protokol ve kontrol listesi<br>Hassas veri ve mahremiyet</td>
  </tr>
</table>

---

## Proje

### ProofSender · e-posta güvenliği SaaS · [proofsender.com](https://proofsender.com)

> **Kapalı beta.** Kaynak kodu gizli, bu yüzden repo yerine canlı siteye bağlantı veriyorum. Ürünü **tek başıma**, **Claude Code** ile geliştirdim (Ekim 2026'dan beri, tüm commit'ler bana ait).

Küçük ve orta ölçekli şirketleri iki yerden korur: **alan adının sahteciliğe karşı yapılandırması** ve **gelen kutusuna düşen oltalama ve sahte fatura e-postaları**. E-postayı engellemez; şüpheli olanı açıklamalı bir uyarıyla bildirir.

<table>
  <tr>
    <td align="center"><h3>132</h3>tespit<br>kuralı</td>
    <td align="center"><h3>7</h3>DNS / e-posta<br>protokolü analizi</td>
    <td align="center"><h3>697</h3>pytest<br>testi (engine)</td>
    <td align="center"><h3>67</h3>PHPUnit test<br>dosyası (web)</td>
  </tr>
</table>

<p align="center">
  <img src="assets/proofsender-architecture.svg" width="100%" alt="ProofSender mimarisi: Microsoft 365, Gmail ve DNS kaynakları, Laravel web katmanı, kuyruk, internete kapalı Python analiz motoru ve beş adımlı bulgu modeli">
</p>

**Alan adı koruması**
- **SPF, DKIM, DMARC, MX, MTA-STS, TLS-RPT ve DNSSEC** kayıtlarını analiz eden ayrı analizörler; sürekli izleme ve DMARC raporları
- Her bulgu aynı modelle, Türkçe ve İngilizce: *ne bulundu, neden önemli, kanıt, nasıl düzeltilir, nasıl doğrulanır*

**Gelen kutusu analizi**
- MIME ayrıştırma, kimlik doğrulama sonuçlarının yorumlanması, **benzer alan adı (lookalike)** tespiti
- Bağlantı ve **karekod** analizi, **Office makro (VBA)** analizi
- Faturalardan **IBAN çıkarma**, taranmış PDF'ler için **Tesseract OCR**

**Güvenlik ve gizlilik tasarımı**
- Organizasyonlar arası **veri izolasyonu**; her kullanıcı girdisi **güvenilmeyen veri** olarak işlenir
- **Ham e-posta saklanmaz**; Gmail ve Microsoft 365'e yalnızca okuma izniyle bağlanılır
- **Alan adı sahipliği doğrulanmadan** izleme başlamaz
- **GitHub Actions CI:** testler, statik analiz, bağımlılık denetimi; Docker Compose ile yedekleme ve geri yükleme betikleri

<img src="https://img.shields.io/badge/Email%20Security-161b22?style=flat-square"> <img src="https://img.shields.io/badge/Phishing%20Detection-161b22?style=flat-square"> <img src="https://img.shields.io/badge/DMARC-161b22?style=flat-square"> <img src="https://img.shields.io/badge/OAuth-161b22?style=flat-square"> <img src="https://img.shields.io/badge/KVKK-161b22?style=flat-square">

---

## Araçlar

**Güvenlik ve sistem**<br>
<img src="https://img.shields.io/badge/Linux-161b22?style=for-the-badge&logo=linux&logoColor=22d3ee"> <img src="https://img.shields.io/badge/Kali%20Linux-161b22?style=for-the-badge&logo=kalilinux&logoColor=22d3ee"> <img src="https://img.shields.io/badge/Nmap-161b22?style=for-the-badge"> <img src="https://img.shields.io/badge/TryHackMe-161b22?style=for-the-badge&logo=tryhackme&logoColor=22d3ee"> <img src="https://img.shields.io/badge/Cisco-161b22?style=for-the-badge&logo=cisco&logoColor=22d3ee"> <img src="https://img.shields.io/badge/Hack%20The%20Box-161b22?style=for-the-badge&logo=hackthebox&logoColor=22d3ee">

**ProofSender'da kullandıklarım (Claude Code ile)**<br>
<img src="https://img.shields.io/badge/Python-161b22?style=for-the-badge&logo=python&logoColor=22d3ee"> <img src="https://img.shields.io/badge/FastAPI-161b22?style=for-the-badge&logo=fastapi&logoColor=22d3ee"> <img src="https://img.shields.io/badge/Laravel-161b22?style=for-the-badge&logo=laravel&logoColor=22d3ee"> <img src="https://img.shields.io/badge/PostgreSQL-161b22?style=for-the-badge&logo=postgresql&logoColor=22d3ee"> <img src="https://img.shields.io/badge/Redis-161b22?style=for-the-badge&logo=redis&logoColor=22d3ee"> <img src="https://img.shields.io/badge/Docker-161b22?style=for-the-badge&logo=docker&logoColor=22d3ee"> <img src="https://img.shields.io/badge/GitHub%20Actions-161b22?style=for-the-badge&logo=githubactions&logoColor=22d3ee"> <img src="https://img.shields.io/badge/Git-161b22?style=for-the-badge&logo=git&logoColor=22d3ee"> <img src="https://img.shields.io/badge/Claude%20Code-161b22?style=for-the-badge&logo=anthropic&logoColor=22d3ee">

**Programlama (temel)**<br>
<img src="https://img.shields.io/badge/C-161b22?style=for-the-badge&logo=c&logoColor=22d3ee"> <img src="https://img.shields.io/badge/C%23-161b22?style=for-the-badge"> <img src="https://img.shields.io/badge/C%2B%2B-161b22?style=for-the-badge&logo=cplusplus&logoColor=22d3ee"> <img src="https://img.shields.io/badge/HTML%2FCSS-161b22?style=for-the-badge&logo=html5&logoColor=22d3ee">

---

## Eğitim ve Sertifikalar

- **Bilgisayar Programcılığı (Önlisans)** · Anadolu Üniversitesi · 2024 → 2026 · mezun, GNO 3.18 / 4, **Onur Öğrencisi**
- **Siber Güvenlik Uzmanlığı Eğitimi (120 saat)** · Unityverse Academy · Ocak 2024 · katılım belgesi; kriptografi, uygulama güvenliği, saldırı tespit sistemleri, olay yanıtı ve adli bilişim
- **Cisco Networking Academy · Introduction to Cybersecurity** · Kasım 2026 · tamamlandı
- **TryHackMe** · [hyny](https://tryhackme.com/p/hyny) · 12 oda, Top %30 · SOC Role in Blue Team, Junior Security Analyst Intro, Defensive Security Intro, Web Application Security, Guided Pentest: Web
- **Hack The Box** · crescent07 · **Brutus** Sherlock (Ekim 2024): auth.log ve wtmp kayıtlarından SSH kaba kuvvet saldırısı incelemesi
- **Anestezi (Önlisans)** · İstanbul Aydın Üniversitesi · 2013 → 2015

---

<p align="center">
  <sub><code>yalnızca yetkili test · sorumlu bildirim</code></sub>
</p>
