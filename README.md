# Araştırma Ödevi


1. Solid Prensiplerini Öğren.
2. Microsoft Build 'den 2 etkinlik araştır.
3. Microsoft Build 2020 yeniliklerini Araştır.
4. Takip Ettiğin 2 yazılımcıyı araştır.
5. Devler Azure'da araştır [Eğitim-Workshop]
6. Yazılım ile ilgili Yarışmaları araştır (Örneğin: GGJ)


**Solid Nedir?**

SOLID prensipleri, anlaşılabilir, esnek ve yönetilebilir kod yazmak için takip edilmesi önerilen pratikleri ifade eder.

Solid, 5 prensibin baş harflerinin birleşimidir. Bu prensipler;

- Single Responsibility Prensibi
- Open Closed Prensibi
- Liskov Substitution Prensibi
- Interface Segregation Prensibi
- Dependency Inversion Prensibi

Bu prensiplere uygun olarak kodlama yapıldığında, programcıya kolay geliştirilebilir bir sistem sağlar.

**Nasıl Ortaya Çıkmıştır?**

Solid, 2000 li yılların başında Robert C. Martin tarafından nesne yönelimli programlamanın 5 temel prensibi bir araya getirilerek ortaya çıkmıştır.

**Single Responsibility Prensibi**

- Tek sorumluluk prensibidir.
- Bu prensibe göre; bir classın veya metodun sadece tek bir görevi olmalıdır ve o görevden sorumlu olmalıdır.
- Yazdığım örnek uygulamada Customer classında birden çok metod kullanmanın yerine ayrı ayrı classlar oluşturup **Single Responsibility Prensibine** göre kodumu düzelttim.

**Open**** Closed Prensibi**

- Open closed prensibine göre; yazılım varlıkları (classlar, modüller, fonksiyonlar vs.) gelişime AÇIK, kod değişimine KAPALI olmalıdır.
- Yazdığım örnek uygulamada müşterinin üyelik tipine göre indirim yapmak istiyorum. Buna göre sistemde, premium ve standart olmak üzere iki tür üyelik tipi var. Üyelik tipine göre sipariş için fiyat belirlenecek ancak eğer yeni bir üyelik tipi eklenecek olursa kodumuzu bayağı değiştirmek gerekeceğinden dolayı yani **Open Closed**** Prensibine** aykırı bunu düzeltmek için sipariş classının yapısını değiştirdim ve enum kullanmadan hesap tiplerini eklemek için abstract class yapısını kullanarak prensibe uygun hale getirdim.

**Liskovs Substitution Prensibi**

- Bu prensip Barbara Liskov tarafından öne sürülmüştür.
- Liskov un yerine geçme prensibine göre; alt sınıflardan oluşan nesneler üst sınıfın nesneleri ile yer değiştirdiklerinde, aynı davranışı sergilemesi beklenmektir.
- Yazdığım örnek uygulamada soyut (abstract) olarak bir car class tanımladım. Ve içerisine Run ve OpenAirCondutioning metotları ekledim. Kalıtım alınacak Run metodu ile araba çalıştırılacak, soyut (abstract) olarak tanımlanmış OpenAirCondutioning metotu ile kalıtım alan türe göre klima açılacak. Ardından Ferrari ile Şahin somut sınıflarını (concreate) Car soyut sınıfından kalıtım yoluyla oluşturuyoruz. Burada dikkatin çekilmesi gereken nokta: Şahinin klima özelliğinin olmamasından dolayı ve soyut (abstract) olarak tanımlanmış metotu override etmek zorunda olduğumuz için ya NotImplementedException hatası gelecektir. Bunu gidermek için **Liskovs Substitution Prensibini** uygulayarak OpenAirConditioning özelliğini temel sınıfımız olan Car sınıfından bir Interface (arayüz) aracılığı ile ayırarak ve ilgili somut sınıfa (concreate class) implemente ederek bu problemin önüne geçebiliriz.Klima özelliğini sadece Ferrari için implemente ettiğimizden dolayı, hiç kimse Şahin için OpenAirConditioning metotuna erişemeyecek ve herhangi bir problem ile karşılaşılmayacaktır.

**Interface Segregation Prensibi**

- Arayüz ayırım prensibi, bir arayüze gerektiğinden fazla yetenek eklemememiz gerektiği söyler.
- Single Responsibility prensibinin arayüzler için geçerli olduğu bir prensip olarak kabul edilebilir.
- Arayüz ayırım prensibinin bize önerdiği çözüminterface bölmektir.
- Yazdığım örnek uygulamada yüksek ve düşük seviyeli olmak üzeri iki kullanıcı var. Bunlar IUser interface içinde tanımlı update,deletep ve create metotlardır. Bunları bu iki kullanıcı için kullanmak istediğimde kalıtım olarak aldığımda düşük seviyeli kullanıcı için sadece updateaccount metodunu kullanmak istiyoruz ancak tüm metotları aldığından dolayı **Interface Segregation Prensibine** ters düşmekte bunu sağlamak için her metod için ayrı ayrı Interface oluşturup düşük kullanıcılar için sadece IUpdater implement ederek prensibe uygun hale getirdim.

**Dependency Inversion Prensibi**

- Bağlılığı tersine çevirme prensibidir.
- Bu prensibe göre; üst seviye sınıflar alt seviyeli sınıflara bağımlı olmamalıdır. Alt sınıflarda yapılan değişiklikler üst sınıfları etkilememelidir.
- Aralarındaki ilişki abstraction veya interface kullanarak sağlanmalıdır.
- Bu prensipteki amaç gerçek nesneye bağlı kalmamaktır.
- Yazdığım örnek uygulamada DbLogger,FileLogger ve LogManeger olmak üzere üç classım var. Burada bulunan sınıflar interfacede bulunan metodları kullanmaktadırlar. Bu sınıfların işlemlerini gerçekleştirmek için bulunan arayüze bağlı olmayan  **LogManager**  sınıfı sayesinde eklenen  **log**  sınıflarını kontrol edebiliyoruz. Böylelikle  **Dependency Inversion Prensibine** uygun olarak üst sınıfımız alt sınıflara bağlı kalmamış oluyor.


# **Microsoft Build 2020**

İzlediğim 2 Etkinlik

**Etkinliğin Adı:** Learn to code with Visual Studio Code

**Etkinliğin tarihi:** 20 Mayıs Çarşamba (01.30- 2.00)

**Konuşmacılar** :Devin Valenciano- Sana Ajani

**Etkinliğin İçeriği**

Bu etkinlikte temel olarak Visual Code nedir, ne için kullanılır ve eklentiler ile bazı yapabileceğimiz özelliklerden bahsedilmiştir.

Visual Code ile herhangi bir programlama dili kullanılabilir ( Phyton,java,C++). Basit ve ücretsiz bir kullanımı vardır. Kişiselleştirilebilir ayarlar ve temalar bulunmaktadır. Hemen hemen her dil için eklenti bulunmaktadır. Mac, Linux ve Windows tabanlı çalışabilmektedir ve birbirleriyle eşitlenebilir. Visual Code, Stackoverflow anketine göre %50,7 ile en popüler yazılım geliştirme aracı konumundadır.

**LiveShare Extension Pack eklentisi ile;**

Live Share, kullandığınız programlama dillerinden veya oluşturduğunuz uygulama türlerinden bağımsız olarak başkalarıyla gerçek zamanlı iş birliği yaparak kodu düzenlemenize ve hataları ayıklamanıza olanak tanır. Geçerli projenizi anında ve güvenli bir şekilde paylaşabilir, ortak hata ayıklama oturumları başlatabilir, terminal örneklerini paylaşabilir, localhost web uygulamalarını iletebilir, sesli aramalar yapabilir ve daha birçok özellikten yararlanılabilmektedir.

Sublime Text Keymap and Settings eklentisi ile klavye kısayolları atamak mümkündür.

Visual Code panelindeki her bir alanı özelleştirmek de mümkün. Örneğin arama çubuğunun yerini değiştirmek gibi.

Github eklentisini ekleyip repositorylere de kolayca ulaşılabiliriz ve Visual Code üzerine entegre edebiliriz.

Remote-Containers eklentisi ile kendi bilgisayarının depolama alanında değil uzak sanal makine üzerinde çalıştırabilmemizi sağlamaktadır. Bunun için Docker konteyner yüklemeliyiz.

Setting Sync eklentisi ile Vscode ayarlarını Github Gist üzerine upload etmemizi sağlayan bir eklentidir.

**Remote Devolopment eklentisi** **(****Visual Studio Code Uzaktan Geliştirme) ****ile;**

Visual Studio Code [Remote Development uzantı paketi](https://aka.ms/vscode-remote/download/extension) , bir kapta, uzak makinede (SSH aracılığıyla) veya Linux için Windows Alt Sisteminde herhangi bir klasörü açmanıza ve VS Codeun tam özellik kümesinden yararlanmanıza olanak tanır. Bu, VS Kodunun, kodunuzun bulunduğu veya barındırıldığı yerden bağımsız olarak, tam IntelliSense (tamamlamalar), hata ayıklama ve daha fazlasını içeren yerel kalitede bir geliştirme deneyimi sağlayabileceği anlamına gelir.

Etkinliğin Adı: **Introduction to GitHub for Student Developers**

Etkinliğin tarihi:20 Mayıs 2020 (00:45-1.15)

Konuşmacılar:Stanley Goldman

Etkinliğin İçeriği

Bu etkinlikte temel olarak Githubın ne olduğu ne için kullanıldığından bahsedilmiştir.

Github için kayıt olup oturum açtıktan sonra repository oluşturulur.

Konuşmacı bir örnek StudentZone repository oluşturduktan sonra basit bir kod yazımı için readme dosyası üzerinde kod yazıp düzenleme yapıldığından ve önizleme yapılabildiğinden bahsetti. Github desktop yükleyip yerel de çalışma yaptı. Kullanımını gösterdi. Github Desktop üzerinden oluşturulan StudentZone adlı repository kodları çekilerek yerel de Visual Code üzerinden çalışma yaptı.

**GitHub Nedir?**

Yazılımcıların sosyal medyası olarak da anılan GitHub, versiyon kontrol sistemlerinde uzak bir depo rolünü oynar. Github, geliştirilmekte olan projelere ya da yapım aşamasında olan projelere farklı ülkelerden ve bu ülkelerin çeşitli yerlerindenprojeye farklı kişilerin eklendiği ve birlikte bir takım çalışmasının yapıldığı proje yönetim sistemidir. Yapılan ekip çalışmasıyla hangi kişinin projenin hangi konumunda yer alacağı belirlenir, kişinin yaptığı çalışmalar incelenebilir ve bu proje üzerinde kimin ne kadar süre zarfında çalıştığını görüp, inceleyip çeşitli analizler yapılabilir. Bu yöntemle projede rahatlıkla görevler takip edilebilir ve yetkilendirmeler kolay hale gelir.

Githubta projelerini oluşturmak isteyen kişiler, ilk önce github sitesine girerek ücretsiz kullanıcı hesabı oluşturmalıdır. Kayıt yapıldıktan sonra kişilerin bilmesi gereken en önemli şeyler şunlardır: kullanıcı tarafından barındırılan proje branch ve fork, repository gibi isimlerle anılır. Bu bir nevi ana klasör olarak düşünülebilir. Branch ise repositorylerin alt klasörleri olarak düşünülebilir. Fork etmek ise başkası tarafından yapılan bir repositorynin kişi tarafından kopyalanması ve ayrıca bilgisayarda clone etmeye hazır hale getirilmesi anlamlarını taşıyor.

**Githubun Hangi Avantajları Bulunuyor?**

Github üzerinden yapılan projelerle kişiler kendilerini test etme imkanı elde ederler ve başka yazılımcılar tarafından üretilen kodlar ile kendi kodları arasında mukayese etme imkanı elde ederler. Projenin tıkanılan kısımlarında başka yazılımcılar tarafından yardım edilme imkanı elde edilir. Çoğu yazılım dilini ve uzantıyı destekleyen Github, ücretsiz bir şekilde kullanıldığı için de tercih edilir. Yazılan kodları paylaşmak istemeyen kullanıcılar bu kodları

[https://medium.com/sabancidx/microsoftun-azure-dedikleri-d08119cd66ba](https://medium.com/sabancidx/microsoftun-azure-dedikleri-d08119cd66ba)

belirli bir ücret karşılığında gizleyerek kendi ürettiği kodları diğer kullanıcılardan saklayabilir. Ayrıca site içerisinde hatırlatıcı da yer alıyor. Sitede git takvimi bulunuyor. Bu takvim üzerinden belirlenen günlerde projeyle ilgili gerekli hatırlatmaların yapıldığı bildirimlerden faydalanabilirsiniz. Bütün bunların yanı sıra Github üzerinden katılan her proje kişinin deneyimini artırmasına katkıda bulunur. Bu deneyimlere sahip olan kullanıcılar CVlerine yer aldıkları projeleri ekleyebilir.

**Takip Edilmesi Gereken Etkinlikler**

1. Java &amp; .NET Platformlarında Microservice Bileşenleri -Abdulkerim Karaman (12 Haziran Cuma-22:00)

[https://kommunity.com/devnot-yazilimci-bulusmalari/events/java-net-platformlarinda-microservice-bilesenleri-84d7a825](https://kommunity.com/devnot-yazilimci-bulusmalari/events/java-net-platformlarinda-microservice-bilesenleri-84d7a825)

2. DevOpsDays Türkiye Online 2020 (25 Haziran Perşemebe- 08:30-17:00)

[https://kommunity.com/devops-turkiye/events/devopsdays-turkiye-online-2020-c0b34c6a](https://kommunity.com/devops-turkiye/events/devopsdays-turkiye-online-2020-c0b34c6a)

**TAKİP ETTİĞİM 2 YAZILIMCI**

**Gökhan Ayrancıoğlu.**

IoT Java Developer olarak Turkcell de çalışmaktadır.

[https://medium.com/@gokhana](https://medium.com/@gokhana)

Beğendiğim makalesi; Microservice Mimarisi ile Yazılım Tasarımı ve Microservice Nedir? Microservice Mimarisine Giriş

[https://medium.com/@gokhana/microservice-mimarisi-ile-yaz%C4%B1l%C4%B1m-tasar%C4%B1m%C4%B1-1f6e54e09202](https://medium.com/@gokhana/microservice-mimarisi-ile-yaz%C4%B1l%C4%B1m-tasar%C4%B1m%C4%B1-1f6e54e09202)

[https://medium.com/@gokhana/microservice-mimarisi-nedir-microservice-mimarisine-giri%C5%9F-948e30cf65b1](https://medium.com/@gokhana/microservice-mimarisi-nedir-microservice-mimarisine-giri%C5%9F-948e30cf65b1)

Ayrıca Monolitik Mimari ve Microservice Mimarisi arasındaki farklar, Solid prensipleri, IIOT Nedir ? IIOT ve IoT arasında ki farklar nelerdir konularında makaleleri de bulunmaktadır.

**Mustafa Sadedil.**

SabancıDx de Software Developer olarak çalışmaktadır.

[https://medium.com/@sadedil](https://medium.com/@sadedil)

Beğendiğim makalesi; Microsoftun Azure dedikleri adlı makalesidir.
