![Dashboard ](dashboard_screenshot.png)

## 🇹🇷 Personel Dashboard – Power BI Raporlama Projesi (README)

Bu proje, bir şirketin insan kaynakları verilerini tek sayfada toplayan, interaktif ve yönetim odaklı bir Power BI Dashboard çalışmasıdır. Dashboard; çalışan sayısı, cinsiyet dağılımı, maaş toplamı, personel durum oranları ve çeşitli filtrelerle detaylı analiz yapılabilmesini sağlar.

Tasarım; özel PowerPoint arka planı, Google’dan indirilen özel filtre ikonu, tooltipler ve modern bir UI/UX yaklaşımı ile profesyonelleştirilmiştir.

##  Projenin Amacı

Bu dashboard ile:

-Toplam maaş ve toplam personel sayılarını izlemek

-Cinsiyet dağılımını analiz etmek

-İşten ayrılan personellerin yüzdelik oranını görmek

-Departman, durum ve şehir bazlı dağılımları incelemek

-Sol taraftaki filtre paneli ile veriyi detaylandırmak

-Üst yönetime hızlı, tek bakışta içgörü sunmak

## A. KPI Kartları

## Dashboard’un üst bölümünde KPI’lar:

## Toplam Personel Sayısı (PersonelSayısı)

PersonelSayısı = COUNTA(Tablo33[İsim Soyisim])

## Kadın Personel Sayısı (KadınSayısı)

KadınSayısı = CALCULATE([PersonelSayısı], Tablo33[Cinsiyet]="Kadın")

## Turnover Oranı (TurnOverRate)

TurnOverRate = DIVIDE(CALCULATE([PersonelSayısı], Tablo33[Durum]="Ayrıldı"), [PersonelSayısı])

Tüm KPI’lar dashboard’daki slicer’lara duyarlıdır.


## B. Bar Chart – Departman Bazlı Personel Sayısı

X Ekseni: Departman

Y Ekseni: Personel Sayısı (Values: PersonelSayısı)

Amaç: Departman yoğunluğunu analiz etmek.

## C. Donut Chart – Durum Bazlı Dağılım

Dilimler: Çalışıyor / Ayrıldı

Values: PersonelSayısı

Legend: Durum

Amaç: İşten ayrılma ve çalışan oranlarını görsel olarak sunmak.

## D. Sol Taraf Özel Filtre Paneli (Custom Filter Panel)

Slicer’lar:

Cinsiyet → Kadın / Erkek

Durum → Çalışıyor / Ayrıldı

Şehir → Şehir bazlı filtreleme

Filtre ikonları Google’dan indirilmiş ve Power BI’a eklenmiştir.

Filtreleri temizlemek için ikon kullanıldığında tüm filtreler resetlenir.


## E. Tooltip

Özel tooltip tasarımı ile grafiklerde fare üzerine gelindiğinde detaylı bilgi gösterilir.

## 3. Veri Modeli

Tek tablo: Tablo33

Kolonlar:

Kolon	Açıklama
İsim Soyisim	Çalışan adı
Cinsiyet	Kadın / Erkek
Departman	Çalıştığı birim
Durum	Çalışıyor / Ayrıldı
Maas	Çalışanın maaşı
Sehir	Şehir bilgisi
Yıl Analiz yılı

-Ayrıca _calc tablosu: DAX measure’ları burada toplanmıştır.

-Star schema veya ilişkiler yok; dashboard tek tablo üzerinden çalışır.

## 4. Tasarım Özellikleri (UI / UX)

Minimal ve kurumsal renk paleti

PowerPoint ile özel arka plan

KPI kartlarında yüksek kontrast kullanım

Düzenli grafik yerleşimi

Özel tooltip tasarımları

Sol filtre alanı ile profesyonel BI standardı

## 5. Kurulum

Power BI Desktop’ı açın

Depoyu klonlayın veya ZIP indirin

personeldashboard.pbix dosyasını açın

Dashboard otomatik olarak yüklenir


## Personnel Dashboard – Power BI Reporting Project (README)

This Power BI project visualizes HR data on a single interactive page. It includes employee counts, salary totals, gender distribution, resignation rates, and department/city-based breakdowns.

Design includes custom PowerPoint background, Google-sourced filter icon, enhanced tooltips, and a clean UI/UX approach.

## Project Objectives

Monitor total employee count

Analyze gender distribution

Display turnover percentages

Provide breakdowns by department, employment status, and city

Allow deeper analysis via the left-side filter panel

Provide a single-page executive dashboard

## Dashboard Components
## KPI Cards

## Total Employees

PersonelSayısı = COUNTA(Tablo33[İsim Soyisim])

## Female Employees

KadınSayısı = CALCULATE([PersonelSayısı], Tablo33[Cinsiyet]="Kadın")

## Turnover Rate

TurnOverRate = DIVIDE(CALCULATE([PersonelSayısı], Tablo33[Durum]="Ayrıldı"), [PersonelSayısı])

All KPIs respond dynamically to slicers.


##Bar Chart – Employee Count by Department

X-Axis: Department

Y-Axis: Employee Count

Shows department distribution.

##Donut Chart – Employment Status Distribution

Values: PersonelSayısı

Legend: Status

Shows ratio of Active vs Resigned employees.

##Custom Filter Panel

Slicers for Gender, Status, and City

Filter icon inserted from Google

Resetting filters clears all selections

## Tooltip

Custom tooltip shows details on hover

## Data Model

Single table: Tablo33

Columns: Name, Gender, Department, Status, Salary, City, Year

_calc table holds all DAX measures

No relationships needed; works with one table

## UI / UX Highlights

Minimal corporate color palette

Custom PowerPoint background

High-contrast KPI cards

Clean tooltip and layout

Professional BI standard filter panel

## Installation

Open Power BI Desktop

Clone repository / download ZIP

Open personeldashboard.pbix

Dashboard loads automatically
