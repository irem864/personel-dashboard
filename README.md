🇹🇷 Personel Dashboard – Power BI Raporlama Projesi (README)

Bu proje, bir şirketin insan kaynakları verilerini tek sayfada toplayan, interaktif ve yönetim odaklı bir Power BI Dashboard çalışmasıdır. Dashboard; çalışan sayısı, cinsiyet dağılımı, maaş toplamı, personel durum oranları ve çeşitli filtrelerle detaylı analiz yapılabilmesini sağlar.

Tasarım; özel PowerPoint arka planı, Google’dan indirilen özel filtre ikonu, özelleştirilmiş tooltipler ve modern bir UI/UX yaklaşımı ile profesyonelleştirilmiştir.

 1. Projenin Amacı

Bu dashboard ile:

Toplam maaş ve toplam personel sayılarını izlemek

Cinsiyet dağılımını analiz etmek

İşten ayrılan personellerin yüzdelik oranını görmek

Departman, durum ve şehir bazlı dağılımları incelemek

Sol taraftaki filtre paneli ile veriyi detaylandırmak

Üst yönetime hızlı, tek bakışta içgörü sunmak

hedeflenmiştir.

 2. Dashboard’ın Ana Bileşenleri
 A. KPI Kartları

Dashboard’un üst bölümünde 4 ana KPI bulunmaktadır:

 Toplam Maaş (Total Salary Sum)

Measure:

SUM('Personeller'[Maas])


Amaç: Şirketin toplam maaş maliyetini gösterir.
Tüm slicer’lara duyarlıdır.

 Toplam Personel Sayısı (Total Employee Count)

Measure:

COUNTA('Personeller'[PersonelID])


Dinamik çalışır; tüm filtrelere duyarlıdır.

Kadın Personel Sayısı (Female Employee Count)

Measure:

Female Count =
CALCULATE(
    COUNTA('Personeller'[Cinsiyet]),
    'Personeller'[Cinsiyet] = "Kadın"
)

 İşten Ayrılanların Yüzdelik Oranı (Resignation Percentage)

Measure:

Resigned Rate =
DIVIDE(
    CALCULATE(COUNTA('Personeller'[Durum]), 'Personeller'[Durum] = "Ayrıldı"),
    COUNTA('Personeller'[Durum])
)


Bu measure’da CALCULATE + COUNTA + DIVIDE birlikte kullanılmıştır.

 B. Bar Chart – Departman Bazlı Personel Sayısı

X ekseni: Departman

Y ekseni: Personel Sayısı
Amaç: Departman yoğunluğunu analiz etmek.

 C. Donut Chart – Durum Bazlı Dağılım

Dilimler:

Çalışıyor

Ayrıldı

Amaç: Durum oranlarını görsel ve anlaşılır şekilde sunmak.

 D. Sol Taraf Özel Filtre Paneli (Custom Filter Panel)

Kullanılan slicer’lar:

Slicer	Açıklama
Cinsiyet	Kadın – Erkek
Çalışma Durumu	Çalışıyor / Ayrıldı
Şehir	Şehir bazlı filtreleme
Departman	Departman kırılımı
Yıl	Yıllara göre analiz

Panelde kullanılan özellikler:

PowerPoint ile tasarlanmış özel arka plan

Google’dan indirilen özel filtre ikonu

Modern ve sade UI/UX

 3. Tasarım Özellikleri (UI / UX)

Minimal ve kurumsal renk paleti

PowerPoint ile özel arka plan

KPI kartlarında yüksek kontrast kullanım

Düzenli grafik yerleşimi

Özel tooltip tasarımları

Sol filtre alanı ile profesyonel BI standardı

 4. Kullanılan DAX Measure’ları
Total Salary = SUM('Personeller'[Maas])

Total Employees = COUNTA('Personeller'[PersonelID])

Female Count =
CALCULATE(COUNTA('Personeller'[Cinsiyet]), 'Personeller'[Cinsiyet] = "Kadın")

Male Count =
CALCULATE(COUNTA('Personeller'[Cinsiyet]), 'Personeller'[Cinsiyet] = "Erkek")

Resigned Count =
CALCULATE(COUNTA('Personeller'[Durum]), 'Personeller'[Durum] = "Ayrıldı")

Resigned Rate = DIVIDE([Resigned Count], [Total Employees])

 5. Veri Modeli

Tek tablo üzerinden çalışan sade bir yapı:

Tablo: Personeller
Kolon	Açıklama
PersonelID	Benzersiz çalışan ID
Ad	Çalışan adı
Cinsiyet	Kadın / Erkek
Departman	Çalıştığı birim
Durum	Çalışıyor / Ayrıldı
Maas	Çalışanın maaşı
Sehir	Yaşadığı şehir
Yıl	Analiz yılı
 6. Kurulum

Power BI Desktop’ı açın

Depoyu klonlayın veya ZIP indirin

personeldashboard.pbix dosyasını açın

Dashboard otomatik olarak yüklenir



🇬🇧 Personnel Dashboard – Power BI Reporting Project (README)

This Power BI project visualizes HR data such as employee counts, salary totals, gender distribution, resignation rates, and department-based or city-based breakdowns on a single interactive page.

The design includes a custom PowerPoint background, a custom filter icon downloaded from Google, enhanced tooltips, and a clean professional UI/UX structure.

 Project Objectives

This dashboard aims to:

Monitor total salary expenses and total employee count

Analyze gender distribution

Display resignation percentages

Provide breakdowns by department, employment status, and city

Allow deeper analysis through the left-side custom filter panel

Provide a single-page executive analytics view

 Dashboard Components
 A. KPI Cards
 Total Salary
SUM('Personeller'[Maas])


Shows total employee salary cost.

 Total Employees
COUNTA('Personeller'[PersonelID])


Fully responsive to all slicers.

 Female Employees
Female Count =
CALCULATE(COUNTA('Personeller'[Cinsiyet]), 'Personeller'[Cinsiyet] = "Kadın")

 Resignation Rate
Resigned Rate =
DIVIDE(
    CALCULATE(COUNTA('Personeller'[Durum]), 'Personeller'[Durum] = "Ayrıldı"),
    COUNTA('Personeller'[Durum])
)

 B. Bar Chart – Employee Distribution by Department

X-Axis: Department

Y-Axis: Employee Count

 C. Donut Chart – Employment Status Distribution

Shows Active vs Resigned employee ratio.

 D. Custom Left Filter Panel

Includes slicers for:

Gender

Employment Status

City

Department

Year

Designed with:

Custom PowerPoint background

Custom filter icon

Clean BI layout

 DAX Measures Used

(Same DAX formulas written above in English)

 Data Model

Single-table structure:

Column	Description
PersonelID	Unique employee ID
Gender	Female / Male
Department	Assigned department
Status	Active / Resigned
Salary	Monthly salary
City	Location
Year	Filter field
UI / UX Highlights

Custom PowerPoint background

High-contrast KPI cards

Clean tooltip design

Balanced layout

Professional BI structure

 Installation

Open Power BI Desktop

Clone repository / download ZIP

Open personeldashboard.pbix

Dashboard loads automatically
