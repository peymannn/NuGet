# NuGet
##Nuget nedir?
Microsoft geliştirme platformu için 2010’da vistual studio da piyasaya sunulan ve 2012 ile kendiliğinden yüklü gelen NUGET ; Visual Studio projemiz için eklemek istediğimiz 3. parti paket(sonradan eklenilebilen programlar; AjaxControlToolkit, Jquery, Facebook, log4net vb) ve DLL’leri (Dynamic Link Library)  bizim yerimize otomatik olarak ekleyen ücretsiz  ve açık kaynak paket yöneticisidir. **Nuget Gallery** paket yönetim uygulaması açık kaynak kodlu olduğu için kendi kütüphanenizi oluşturabilir,  nuget galeriye koyabilirsiniz.
![photo](https://github.com/peymannn/nugetPHOTO/blob/master/nuget1.png)

##Nuget nasıl kurulur?
NuGet doğrudan Visual Studio içerisine entegre olarak çalışmaktadır. Nuget kurulumu iki şekilde sağlanmaktadır. İlki doğrudan [CodePlex] (http://nuget.codeplex.com/) üzerinden kurulum dosyasını indirerek kurabilirsiniz, diğer türlü Vistual Studio 2010 içinde **Tools**  seçeneğinde         **  Extension Manager** ’i   tıklarız ve nuget diye aratırsak çıkan Nuget Package Manager ‘in Download seçeneğini tıklayıp kurulumunu yapabiliriz.
![photo](https://github.com/peymannn/nugetPHOTO/blob/master/Ekran%20Al%C4%B1nt%C4%B1s%C4%B1n%202.PNG)
Vistual studio’yu yeniden başlatmanız gerekmektedir. 

**NuGet Package Manager Console** kullanarak ya da **Add Library Package Reference** penceresinden yeni paketler yükleyebilir, güncelleyebilir veya kaldırabilirsiniz. Add Library Package Reference seçeneği sadece solution açık durumda iken kullanılabilir. 
* Gelin kullanımını bir örnekle  görelim:

Önceden olan banka_hesabı programımızı açtık ve **Tools --> Library Package Manager--> Manage NuGet Packages for Solution**   yollarını takip ediyoruz. Karşımıza çıkan ve ihtiyacımız olan EntiyFramework ve bootstrap için **install** butonuna bastığımızda programımıza eklendiğini göreceksiniz.

![photo](https://github.com/peymannn/nugetPHOTO/blob/master/Ekran%20Al%C4%B1nt%C4%B1s%C4%B13.PNG)
Projenizin dosyalarından da eklendiğini görebilirsiniz.

![photo](https://github.com/peymannn/nugetPHOTO/blob/master/6.PNG)

 Şimdide **Package Manager Console** ‘da işimize yarayacak birkaç Nuget komutunu inceliyelim;
 
 * ````
 get-package –remote
````= Nuget sunucusu üzerinde bulunan ve  indirebileceğiniz tüm kütüphaneleri  listeler.
 * ```` get-pacgake –remote  -filter  (kriter) ````= Nuget sunucusundaki kritere uygun olan kütüphaneleri listeler.
 * ````	Install-package (Kütüphane adı)    ````= =  Adı verilen kütüphane , proje içerisine indirilir ve  gerekli görüldüğü zaman config dosyaları güncellenir. Örnek:` PM>Install-Package EntityFramework `

 Daha fazla komuta  `get-help` komutu ile ulaşabilirsiniz.
 ##         Kendi Nuget Paketimizi nasıl yayınlarız?
 İlk önce geliştirdiğimiz kütüphaneyi Nuget ‘e koyabilmemiz için [Nuget Package Explorer ](http://nuget.codeplex.com/downloads/get/clickOnce/NuGetPackageExplorer.application?releaseId=59864)‘ı indirip kurmamız gerekiyor sonrada karşımıza çıkan tablodan **Create a new package**‘ı tıklarız.
 ![photo](https://github.com/peymannn/nugetPHOTO/blob/master/nugetexpolorer.PNG)
 
 Daha sonra karşımıza çıkan penceredeki **Package metadata** penceresindeki bilgileri kütüphane bilgilerimize göre doldururuz. Dll dosyalarını koyabilmek için açılan pencerenin Package contents kısmında sağ tıklayıp  **Add Lib Folder**’a tıklarız ve **Lib**‘e sağ tıklayıp **Add existing File** deyip dll dosyalarını ekleriz.
![photo](https://github.com/peymannn/nugetPHOTO/blob/master/Ekran%20Al%C4%B1nt%C4%B1s%C4%B17.PNG)

Kütüphanemizi kaydettikten sonra yayınlamak için NuGet  hesabına sahip olmalıyız .[Buradan ](https://www.nuget.org/users/account/LogOn?returnUrl=%2FErrors%2F404%3Faspxerrorpath%3D%2Faccount%2FRegister) kayıt olabirsiniz.
Kayıt olduktan sonra giriş yapıp **Upload Package** seçeneğini tıklayarak dosyaları yükleyebiliriz.

Ayrıca Vistual studio 2015 Nuget api v3 kullanmakta ve bu bazı paket yüklemelerine sorun çıkarabilir bunun için  **Tools--> Nuget Package Manager --> Package Manager Settings --> Package Sources --> Available package sources** oklarını takip etmeli ve yeni Nuget sources eklemeliyiz. Sources alanına https://www.nuget.org/api/v2/   
adresini yazıyoruz. Böylelikle pakat yükleme sorunsuz şekilde hallolur.

[Buraya tıklayarak](http://nugetmusthaves.com/ ) en popüler NuGet paketlerini bulabilirsiniz.

