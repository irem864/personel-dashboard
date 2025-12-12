Personel Dashboard – Power BI Raporlama Projesi 

Bu proje, bir şirketin insan kaynakları verilerini tek sayfada toplayan, interaktif ve yönetim odaklı bir Power BI Dashboard çalışmasıdır. Dashboard; çalışan sayısı, cinsiyet dağılımı, maaş toplamı, personel durum oranları ve çeşitli filtrelerle detaylı analiz yapılabilmesini sağlar.

Tasarım, kullanıcı dostu bir deneyim sunmak amacıyla özel PowerPoint arka planı, Google’dan indirilen özel filtre ikonu, özelleştirilmiş tooltipler ve temiz bir UI/UX yaklaşımı ile hazırlanmıştır.

 1. Projenin Amacı

Bu dashboard ile:

Toplam maaş ve personel sayılarını izlemek

Cinsiyet dağılımını analiz etmek

İşten ayrılan personellerin oranını görmek

Departman, durum ve şehir bazlı dağılımları incelemek

Filtre alanını kullanarak veri detaylandırmak

Üst yönetime hızlı, tek bakışta bilgi sağlamak

hedeflenmiştir.

 2. Dashboard’ın Ana Bileşenleri
 A. KPI Kartları

Raporun üst bölümünde 4 ana KPI bulunmaktadır:

Toplam Maaş (Total Salary Sum)

Measure: SUM('Personeller'[Maas])

Amaç: Şirketin toplam çalışan maliyetini gösterir.

Tüm slicer’lara duyarlıdır.

 Toplam Personel Sayısı (Total Employee Count)

Measure: COUNTA('Personeller'[PersonelID])

Dinamik olarak çalışır.

Aktif çalışan + ayrılan tüm kayıtları filtreye göre hesaplar.

 Kadın Personel Sayısı (Female Employee Count)

Measure:

Female Count =
CALCULATE(
    COUNTA('Personeller'[Cinsiyet]),
    'Personeller'[Cinsiyet] = "Kadın"
)

 İşten Ayrılanların Yüzdelik Oranı (Resignation Percentage)

“Çalışma Durumu” kolonuna göre hesaplanır.

Measure:

Resigned Rate =
DIVIDE(
    CALCULATE(COUNTA('Personeller'[Durum]), 'Personeller'[Durum] = "Ayrıldı"),
    COUNTA('Personeller'[Durum])
)


Bu measure’da CALCULATE + COUNTA + DIVIDE birlikte kullanılmıştır.

 B. Bar Chart (Dikey Sütun Grafik)
Personel Sayısının Departman Bazlı Dağılımı

X ekseni: Departman

Y ekseni: Personel Sayısı

Amaç: Hangi departmanlarda yoğunluk veya eksik çalışan olduğunu göstermek.

Bu grafik tamamen slicer’lara duyarlıdır.

 C. Donut Chart
Personel Sayısının Durum Bazlı Dağılımı

Dilimler:

Çalışıyor

Ayrıldı

Amaç: Personel durum dağılımını görsel olarak açıklamak.

Oranların kolay anlaşılması için donut chart tercih edilmiştir.

 D. Sol Taraf Filtre Paneli (Custom Filter Panel)

Sol tarafta özel olarak tasarlanmış, ikon destekli bir filtre alanı bulunur.

Kullanılan slicer’lar:

Slicer	Açıklama
Cinsiyet	Kadın – Erkek filtresi
Çalışma Durumu	Çalışıyor / Ayrıldı
Şehir	Şehirlere göre analiz
Departman	Bölümlere göre kırılım
Yıl	Yıllara göre filtre

Bu panel:

PowerPoint ile özel arka plan tasarımı

Google’dan indirilen custom filtre ikonu

Temiz UI/UX yaklaşımı

ile profesyonelleştirilmiştir.

 3. Tasarım Özellikleri (UI / UX)

Minimal ve kurumsal renk paleti

Özel PowerPoint arka plan tasarımı

Koyu–açık alan dengesi

KPI kartlarında yüksek kontrast

Temiz grafik düzeni

Özelleştirilmiş Tooltip kullanımı (bar chart ve donut chart’taki bilgi baloncukları düzenlenmiştir)

Filtre panelinin sola alınmasıyla profesyonel BI standardı korunmuştur

 4. Kullanılan DAX Measure’ları
Toplam Maaş
Total Salary = SUM('Personeller'[Maas])

Toplam Personel Sayısı
Total Employees = COUNTA('Personeller'[PersonelID])

Kadın Personel Sayısı
Female Count =
CALCULATE(COUNTA('Personeller'[Cinsiyet]), 'Personeller'[Cinsiyet] = "Kadın")

Erkek Personel Sayısı
Male Count =
CALCULATE(COUNTA('Personeller'[Cinsiyet]), 'Personeller'[Cinsiyet] = "Erkek")

Ayrılan Personel Sayısı
Resigned Count =
CALCULATE(COUNTA('Personeller'[Durum]), 'Personeller'[Durum] = "Ayrıldı")

Ayrılma Oranı
Resigned Rate =
DIVIDE([Resigned Count], [Total Employees])

 5. Veri Modeli

Tek tablo üzerinden çalışan sade bir model:

 Tablo: Personeller

Kolon	Açıklama
PersonelID	Benzersiz çalışan ID
Ad	Çalışan adı
Cinsiyet	Kadın / Erkek
Departman	Bağlı olduğu birim
Durum	Çalışıyor / Ayrıldı
Maas	Çalışanın maaşı
Sehir	Yaşadığı şehir
Yıl	Analiz yılı
6. Kurulum

Power BI Desktop’ı açın

Depoyu klonlayın veya ZIP olarak indirin

personeldashboard.pbix dosyasını açın

Dashboard otomatik olarak yüklenir





Personnel Dashboard – Power BI Analytics Project

This Power BI project visualizes key HR metrics such as employee counts, salary totals, gender distribution, resignation rates, department-based distribution and more.
The dashboard is designed using a clean, modern UI supported with a custom PowerPoint background and a custom filter icon downloaded from Google.

The report enables HR teams and management to make fast, data-driven decisions.

 Project Objectives

Monitor total salary and employee count

Analyze gender distribution

Track resignation percentages

Visualize department and city distributions

Filter data with an enhanced left-panel slicer area

Provide a single-page, executive-ready analytics dashboard

 Dashboard Components
 A. KPI Cards
 Total Salary

Measure: SUM('Personeller'[Maas])

Shows company’s total salary cost.

 Total Employees

Measure: COUNTA('Personeller'[PersonelID])

Responds to all filters dynamically.

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

X–Axis: Department

Y–Axis: Employee Count

Completely responsive to slicers.

 C. Donut Chart – Employee Status Distribution

Shows “Active vs Resigned” employee rates.

 D. Custom Left Filter Panel

Includes the following slicers:

Gender

Employment Status

City

Department

Year

Designed using:

Custom PowerPoint background

Custom filter icon

Clean and minimal UX

 DAX Measures Used

Total Salary

Total Employees

Female Count (CALCULATE + COUNTA)

Male Count

Resigned Count

Resignation Rate (DIVIDE)

All measures are optimized and fully filter-responsive.

 Data Model

A single-table optimized data model:

Column	Description
PersonelID	Unique employee ID
Gender	Female / Male
Department	Employee's department
Status	Active / Resigned
Salary	Monthly salary
City	Location
Year	Filter field
 UI / UX Highlights

Custom background created using PowerPoint

Custom slicer icon (Google)

High-contrast KPI cards

Professional BI layout

Clean tooltip customization

Balanced chart placement

 Installation

Open Power BI Desktop

Clone repository / download ZIP

Open personeldashboard.pbix

Dashboard loads automatically

