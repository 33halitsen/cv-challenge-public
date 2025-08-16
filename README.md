YouTube’da [LuNiZz (Can Değer)](https://github.com/LuNiZz)’in videosunda karşılaştığım CV Challenge
isimli projeyi yapmayı denedim. Hem teknik becerilerimi geliştirmek hem de uygulamalı
bir proje deneyimi yaşamak adına oldukça öğretici bir süreçti.
Challenge hakkında detaylı bilgi almak isteyenler için Can Değer tarafından hazırlanan
roadmap formatındaki GitHub dokümantasyonunu buraya bırakıyorum:
[CV Challenge Dokümantasyonu](https://github.com/LuNiZz/siber-guvenlik-sss/blob/master/Belgeler/Dokumanlar/CV_Challenge.md)

Projeyi Nasıl Yaptım?
• HTML ve CSS kullanarak CV formatında bir blog sitesi tasarladım.
• Site klasörünü GitHub Desktop ile bir GitHub reposuna aktardım.
• AWS CodePipeline kullanarak bu repoyu S3 Bucket ile entegre ettim ve statik
web barındırma özelliğini aktif ettim.
• AWS’nin verdiği domain üzerinden siteyi yayınladım. Daha sonra HTTPS desteği
eklemek için CloudFront dağıtımı kurdum.
• Daha profesyonel bir görünüm için halitsen.online domain’ini satın alarak Route
53 ile CloudFront dağıtımına entegre ettim.

Ziyaretçi Sayacı Özelliği:
• Sayfaya HTMLiCSS ile bir ziyaretçi sayacı ekledim.
• Sayaç verisini çekmek için JavaScript ile bir script yazdım.
• Veri kaynağı olarak AWS DynamoDB kullandım.
• Güvenli bağlantı için veritabanı ile doğrudan değil, AWS API Gateway üzerinden
iletişim kurdurdum.
• Sayaç değerini artırmak için Python + boto3 ile bir AWS Lambda fonksiyonu
oluşturdum.
• Siteyi İngilizce ve Türkçe olmak üzere iki dilde sunduğumdan, her dil için ayrı
sayaç kullanmak istedim. Bu amaçla DynamoDB’ye ikinci bir sayaç alanı ve ayrı
bir Lambda fonksiyonu daha ekledim. Ve bu yeni Lambda fonksiyonunu da aynı
API Gateway ile entegre ettim.
• API Gateway önüne bir CloudFront katmanı daha koyarak hem performansı
artırdım hem de güvenliği yükselttim. Ayrıca CORS ayarlarını yapılandırarak
sadece kendi domain’imden gelen istekleri kabul ettim.

CIiCD ve Test Süreci:
• Lambda fonksiyonlarım için ayrı bir GitHub reposu oluşturdum.
• Kodlarımı test etmek için unittest ve mock kütüphanelerini kullandım.
• GitHub Actions ile otomatik test ve deploy süreci hazırladım. Böylece kodlarım
testleri geçtikten sonra otonom şekilde AWS Lambda fonksiyonlarına deploy
ediliyor.

Sayfamı Ziyaret Etmek İsterseniz:
👉 [halitsen.online](https://halitsen.online/)

Projeyi daha iyi anlatabilmek için, tüm bileşenleri ve aralarındaki ilişkileri gösteren bir
topolojik mimari diyagramı hazırladım. GitHub’dan AWS’ye, veritabanından Lambda
fonksiyonlarına kadar tüm yapıyı görsel olarak inceleyebilirsiniz.

<img width="905" height="698" alt="Ekran Resmi 2025-08-16 10 21 42" src="https://github.com/user-attachments/assets/4ecb42be-cd86-4757-af87-52e5d698dedb" />

