Personel Dashboard – Power BI Projesi (TR | EN)

Personel Dashboard, insan kaynakları verilerinin analiz edildiği, tek sayfalık modern ve interaktif bir Power BI raporudur. KPI kartları, bar chart, donut chart, özel filtre paneli ve özelleştirilmiş tooltipler içerir.	Personnel Dashboard is a single–page, modern and interactive Power BI report built to analyze HR data. It includes KPI cards, bar charts, donut charts, a custom filter panel, and customized tooltips.
Tasarım, PowerPoint ile oluşturulmuş özel arka plan, Google’dan indirilen özel filtre ikonu ve sade bir UI/UX yaklaşımı ile hazırlanmıştır.	The dashboard uses a custom PowerPoint background, a custom filter icon downloaded from Google, and a clean UI/UX layout.
 1. Projenin Amacı | Project Objectives

• Toplam maaş ve personel sayılarını izlemek
• Cinsiyet dağılımını analiz etmek
• İşten ayrılanların oranını görmek
• Departman, şehir ve duruma göre filtrelemek
• Yönetim için hızlı içgörü sağlamak	• Monitor total salaries and employee counts
• Analyze gender distribution
• Track resignation rates
• Filter by department, city, and employment status
• Provide quick insights for management teams
 2. Dashboard Bileşenleri | Dashboard Components

###  KPI Kartları:
 Toplam Maaş (SUM)
 Toplam Personel Sayısı (COUNTA)
 Kadın Personel Sayısı (CALCULATE + COUNTA)
 Ayrılma Oranı (CALCULATE + COUNTA + DIVIDE)	### 🔹 KPI Cards:
 Total Salary (SUM)
 Total Employees (COUNTA)
 Female Employees (CALCULATE + COUNTA)
 Resignation Rate (CALCULATE + COUNTA + DIVIDE)
###  Bar Chart – Departmana Göre Dağılım	###  Bar Chart – Department-Based Distribution
###  Donut Chart – Durum Dağılımı	###  Donut Chart – Employment Status Distribution
###  Sol Özel Filtre Paneli: Cinsiyet, Durum, Şehir, Departman, Yıl için slicer’lar	###  Custom Left Filter Panel: slicers for Gender, Status, City, Department, and Year
 3. Kullanılan DAX Measure’ları | DAX Measures Used

Toplam Maaş
Total Salary = SUM('Personeller'[Maas])	Total Salary
Total Salary = SUM('Personeller'[Maas])
Toplam Personel Sayısı
Total Employees = COUNTA('Personeller'[PersonelID])	Total Employees
Total Employees = COUNTA('Personeller'[PersonelID])
Kadın Personel Sayısı
CALCULATE(COUNTA('Personeller'[Cinsiyet]), 'Personeller'[Cinsiyet]="Kadın")	Female Employees
CALCULATE(COUNTA('Personeller'[Gender]), 'Personeller'[Gender]="Female")
Ayrılan Sayısı
CALCULATE(COUNTA('Personeller'[Durum]), 'Personeller'[Durum]="Ayrıldı")	Resigned Count
CALCULATE(COUNTA('Personeller'[Status]), 'Personeller'[Status]="Resigned")
Ayrılma Oranı
DIVIDE([Resigned Count], [Total Employees])	Resignation Rate
DIVIDE([Resigned Count], [Total Employees])
 4. Tasarım Özellikleri | UI/UX Details

• Minimalist kurumsal renk paleti
• Özel PowerPoint arka plan tasarımı
• Google’dan alınan özel filtre ikonları
• Özelleştirilmiş tooltipler
• Slicer paneli sola alınarak profesyonel BI standardı uygulanmıştır	• Minimal corporate color palette
• Custom PowerPoint background
• Custom filter icons
• Customized tooltips
• Left-side slicer panel following BI best practices
 5. Veri Modeli | Data Model

Tek tablo modeli – Personeller: PersonelID, Ad, Cinsiyet, Departman, Durum, Maaş, Şehir, Yıl	Single-table model – Employees: ID, Name, Gender, Department, Status, Salary, City, Year
 Kurulum | Installation

• Repoyu klonlayın
• Power BI Desktop’ı açın
• personeldashboard.pbix dosyasını çalıştırın	• Clone repository
• Open Power BI Desktop
• Run personeldashboard.pbix
