# NuGet
##Nuget nedir?
Microsoft geliştirme platformu için 2010’da Visual Studio'da piyasaya sunulan ve 2012 ile default olarak yüklü gelen NUGET, Visual Studio projemiz için eklemek istediğimiz 3. parti paket(sonradan eklenilebilen programlar; AjaxControlToolkit, Jquery, Facebook, log4net vb.) ve DLL’leri (Dynamic Link Library)  bizim yerimize otomatik olarak ekleyen ücretsiz  ve açık kaynak paket yöneticisidir. **Nuget Gallery** paket yönetim uygulaması açık kaynak kodlu olduğu için kendi kütüphanenizi oluşturabilir **Nuget Gallery**'e  koyabilirsiniz.
![photo](https://github.com/peymannn/nugetPHOTO/blob/master/nuget1.png)

##Nuget Nasıl Kurulur?
NuGet doğrudan Visual Studio içerisinde entegre olarak çalışmaktadır. Nuget kurulumu iki şekilde yapılabilir. 
İlki doğrudan [CodePlex] (http://nuget.codeplex.com/) üzerinden kurulum dosyasını indirerek kurabilirsiniz.İkinci olarak Visual Studio 2010 içinde **Tools**  seçeneğinde  **Extension Manager**’i   tıklarız ve nuget diye aratırsak çıkan Nuget Package Manager ‘in Download butonuna tıklayıp kurulumunu yapabilirsiniz.
![photo](https://github.com/peymannn/nugetPHOTO/blob/master/Ekran%20Al%C4%B1nt%C4%B1s%C4%B1n%202.PNG)
Visual Studio’yu yeniden başlatmanız gerekmektedir. 

**NuGet Package Manager Console** kullanarak yada **Add Library Package Reference** penceresinden yeni paketler yükleyebilir, güncelleyebilir veya kaldırabilirsiniz. **Add Library Package Reference** seçeneği sadece solution açık durumda iken kullanılabilir. 
* Gelin kullanımını bir örnekle  görelim:

Önceden yazmış olduğumuz "banka_hesabı" programımızı açıp  **Tools --> Library Package Manager--> Manage NuGet Packages for Solution**   yollarını takip ediyoruz. Karşımıza çıkan aynı zamanda ihtiyacımız olan EntiyFramework ve bootstrap için **install** butonuna bastığımızda programımıza eklendiğini göreceksiniz.

![photo](https://github.com/peymannn/nugetPHOTO/blob/master/Ekran%20Al%C4%B1nt%C4%B1s%C4%B13.PNG)

Projemizin dosyalarından da eklendiğini görebilirsiniz.

![photo](https://github.com/peymannn/nugetPHOTO/blob/master/6.PNG)

 Şimdi de **Package Manager Console**‘da işimize yarayacak birkaç Nuget komutunu inceliyelim;
 
 * ````
 get-package –remote
````= Nuget sunucusu üzerinde bulunan ve  indirebileceğiniz tüm kütüphaneleri  listeler.
 * ```` get-pacgake –remote  -filter  (kriter) ````= Nuget sunucusundaki kritere uygun olan kütüphaneleri listeler.
 * ````	Install-package (Kütüphane adı)    ````= Adı verilen kütüphane, proje içerisine indirilir ve  gerekli görüldüğü zaman config dosyaları güncellenir. Örnek:` PM>Install-Package EntityFramework `

 Daha fazla komuta  `get-help` komutu ile ulaşabilirsiniz.
 ##         Kendi Nuget Paketimizi nasıl yayınlarız?
 İlk önce geliştirdiğimiz kütüphaneyi Nuget‘e koyabilmemiz için [Nuget Package Explorer ](http://nuget.codeplex.com/downloads/get/clickOnce/NuGetPackageExplorer.application?releaseId=59864)‘ı indirip kurmamız gerekiyor. Sonra karşımıza çıkan tablodan **Create a new package**‘ı tıklamalıyız.
 ![photo](https://github.com/peymannn/nugetPHOTO/blob/master/nugetexpolorer.PNG)
 
Karşımıza çıkan  **Package metadata** penceresindeki bilgileri kütüphane bilgilerine göre dolduruyoruz. DLL dosyalarını koyabilmek için açılan pencerenin **Package contents** kısmında sağ tıklayıp  **Add Lib Folder**’ı seçiyoruz ve **Lib**‘e sağ tıklayıp **Add existing File** dediğimizde DLL dosyalarını ekleyebiliyoruz.
![photo](https://github.com/peymannn/nugetPHOTO/blob/master/Ekran%20Al%C4%B1nt%C4%B1s%C4%B17.PNG)

Kütüphanemizi kaydettikten sonra yayınlamak için NuGet  hesabına sahip olmalısınız. Eğer hesabınız yoksa [buradan ](https://www.nuget.org/users/account/LogOn?returnUrl=%2FErrors%2F404%3Faspxerrorpath%3D%2Faccount%2FRegister) kayıt olabilirsiniz.
Kayıt olduktan sonra giriş yapıp **Upload Package** seçeneğini tıklayarak dosyaları yükleyebilirsiniz.

Ayrıca Visual Studio 2015 Nuget API v3 kullanmakta ve bu bazı paket yüklemelerinde sorun çıkarabilir.Bunun için  **Tools--> Nuget Package Manager --> Package Manager Settings --> Package Sources --> Available package sources** sekmeleri takip etmeli ve yeni Nuget sources eklemelisiniz. Sources alanına https://www.nuget.org/api/v2/   
adresini yazmalısınız. Böylelikle paket yüklemedeki  sorunu çözmüş olursunuz.

[Buraya tıklayarak](http://nugetmusthaves.com/ ) en popüler NuGet paketlerini bulabilirsiniz.



Kaynakça :
- http://www.emrahyumuk.com/nuget-nedir-ve-nasil-kurulur/
- http://www.hanselman.com/blog/NuGetForTheEnterpriseNuGetInAContinuousIntegrationAutomatedBuildSystem.aspx
