# Linux komutları
<h3><br/><ins>CAT:</ins></h3>
<br/>Cat komutu dosya içeriğini, terminal ekranından okumamızı sağlayan komuttur.
<br/>Cat komutunun, bu işlemin yanı sıra başka yararları da mevcuttur. Bunlara da değineceğim.
<br/><br/>Örneğin; Linux terminalinde deneme.txt dosyası oluşturalım.
<br/>• cat > deneme.txt komutu ortamda deneme.txt dosyası yok ise önce dosyayı oluşturur ardından içine yazı yazabilmemizi sağlar.
<br/>Bu işlemden sonra cat komutu ile dosyayı okuyalım 
<br/> •	cat deneme.txt
<br/>Lakin dosyayı yeni yarattığımız için içi boş olacak ve herhangi bir yazı ile karşılaşmayacağız. 
<br/>Bu noktada yine “cat” komutu ile dosyamıza yazımızı ekleyebiliriz. Bunu da;
<br/>•cat > deneme.txt komutu ile yapabiliriz.
<br/>Yazımızı ekledikten sonda Ctrl+D ile dosyadan çıkabiliriz.
<br/><br/>Eğer ortamda önceden oluşturulmuş deneme.txt dosyası bulunuyorsa cat > deneme.txt komutu, önceki deneme.txt dosyasının içindeki verileri siler ve yazacağımız yeni verileri deneme.txt dosyasına yazmamızı sağlar.
<br/><br/>Eğer dosyanın üzerine yazmak istiyorsak **cat >>deneme.txt** komutunu kullanmamız gerekir. Bu şekilde eski veriler de yeni veriler de tutulmuş olur.
Bu yere kadar olan komutların terminaldeki örneklerine aşağıdaki linkten ulaşabilirsiniz.
</br> https://github.com/berilerzurum/Linux-komutlar-/blob/c0cacc99957bf03c5fcdd28bc70896a65b8a2ff7/Ekran%20G%C3%B6r%C3%BCnt%C3%BCs%C3%BC%20(728).png 

<br/><br/>Konsolda bir dosyanın içeriğini görüntülemek yerine sonucu > kullanarak başka bir dosyaya yönlendirebilirsiniz. Komut satırı böyle olacaktır:
<br/>• cat kaynak.txt > hedef.txt
<br/>Eğer hedef dosya bulunmuyorsa o zaman komut bu dosyayı yaratacak veya var olan dosyanın üzerine yazacaktır.
<br/><br/>Mevcut konumdaki bütün metin dosyalarının içeriğini görüntülemek için aşağıdaki komutu terminal’de kullanın:
<br/>• cat *.txt

<br/><br/>Cat komutu satır sonlarını, $ karakterini her satırın sonunda görüntüleyerek işaretleyebilir. Bu özelliği kullanmak için cat komutuyla birlikte -E seçeneğini kullanın:
<br/>•cat -E dosyaadi.txt

<br/><br/>Cat komutuyla bir dosyanın içeriklerini her satırın başında rakamlarla görüntüleyebilirsiniz. Bu özelliği kullanmak için cat komutuyla birlikte -n seçeneğini kullanın:
<br/>•cat -n dosyaadi.txt

<br/><br/>Cat komutuyla ilgili daha fazla bilgi için cat’in el kılavuzu sayfasına man cat komutu ile ulaşabilirsiniz.

<br/><h3><ins>More</ins></h3>
<br/>more komutu cat ile aynı ile vazifelidir. Ancak more komutunun bir avantajı, tek sayfada gösterilemeyecek olan dosyalar okunurken, boşluk tuşu ile kaydırma olanağı sağlamasıdır.
<br/>• more file_path
<br/><h3><ins>Less</ins></h3>
<br/>Less komutu da more komutu gibi dosyayı görüntülemeye yarar fakat birkaç farkla.
<br/>•	Less içerik içinde ileri - geri yönlü hareket edebilirken, more ile sadece ileri yönlü hareket edilebilir
<br/>•	Less tüm dosya içeriğini belleğe almadığı için büyük dosyaları okumak için daha uygundur
<br/>•	Less more'a göre daha gelişmiştir (metin içinde arama, zip dosyasını okuma vb..) ve more yerine artık less tercih edilmektedir
<br/><h3><ins>Head</ins></h3>
<br/>Bir metin dosyasının ilk birkaç satırını görüntülemek için kullanılır. Örnek:
<br/>head dosya.txt

<br/><h3><ins>Tail</h3></ins>
<br/>Bir metin dosyasının son birkaç satırını görüntülemek için kullanılır. Örnek:
<br/>tail dosya.txt

<br/>head ve tail komutları için varsayılan değer 10'dur. Ancak istenirse bu değer değiştirilebilir. Örnekler:
<br/>head -n 5 dosya.txt
<br/>tail -n 25 dosya.txt

<br/>Birinci örnekte dosyanın başından itibaren 5 satır görüntülenir. İkincisinde ise aynı dosyanın sonundan itibaren 25 satır görüntülenir. Eğer dosyanın satır sayısı belirtilen sayıdan az ise (veya sayı belirtilmediğinde 10'dan az ise) dosyada olan kadar satır görüntülenir.


<h1> STDIN, STDOUT, STDERR </h1>

<br/>Linux sistemlerinde giriş-çıkış işlemleri stdin, stdout, stderr akış araçlarıyla sağlanır. Bunlar terminalin bizimle iletişim kurmak için oluşturduğu 3 temel noktadır.

<br/>stdin --> Klavyeden ya da başka bir uygulamadan giriş içerir.
<br/>stdout --> Uygulamanın çıktısıdır.
<br/>stderr --> Hata mesajı göndermek için kullanılan çıktıdır.

<br/>Örneğin; klavyeden bir veri girdik. Bu önce uygulamanın Stdin akışına gider, uygulama buna cevap oluşturursa, bu cevabı stdout çıkışına gönderir. Terminalde bu çıkışı izlediği için bunu yakalar ve ekranda gösterir, aynı şekilde bu akış sırasında herhangi bir error oluşursa terminal bunu da yakalar ve ekranda gösterir.

<br/>Mesela terminale ls/beril komutunu girdik ama bulunduğumuz dizinde böyle bir klasör yok. Stderr bir hata mesajı üretir ve "no such file or directory" çıktısını gönderir. Ama dizinde olan bir dosyayı komut olarak girseydik Stdout bunu yakalayacak ve o çıktıyı gönderecekti.

<br/>Docker ile ilgili de birkaç örnek verelim.
<br/>Terminale --> docker run -d --name app berilerzurum/app komutunu girerek bir konteyner oluşturalım.
<br/>Konteynerimiz başlangıçta app uygulaması çalışacak şekilde ayarlı. App --> merhaba ben app. çıktısını bastırıyor. Bu çıktıyı önce stdout'a gönderiyor. Lakin bizim terminalimiz konteynerin terminaline bağlı değil ve konteyner -d ile arkaplanda çalıştığı için mesaj arkaplanada oluştu fakat biz çıktıyı terminalde göremedik. 

<br/>Docker logs tam bu durumu çözebilecek bir komut. Docker logs konteyner çalıştığı sürece, biz logs komutunu girene kadar oluşan tüm logları (stdout,stderr) yakalıyor ve onları komutu girince listeliyor ve bana göremediğim mesajları görebilme imkanı sunuyor.

<br/>Bir başka docker komutu daha girelim.
<br/>docker container run -d --name cont1 -p 80:80 nginx bu komutu girdikten sonra 127.0.0.1 adresine baktığımızda nginx'in mesajını göreceğiz. Nginx'in bu websayfsına erişirken oluşturduğu tüm logları aşağıdaki komutu girerek görebileceğiz.
<br/>docker logs cont1
<br/>Mesela 127.0.0.1/deneme.html diye olmayan bir dosya dizini girelim. Bu oluşan 404 hata mesajını da logların arasınd görebileceğiz.

<br/>Normalde nginx'in deamonı logları stdout,stderr akışına direkt olarak atmaz, access.log ve error.log dosyalarına yazar. Bu dosyalar, nginx'te stdout ve stderr akışına symlink ile bağlanarak bu dosyadakilerin akışta da görünmesini sağlar.

<br/>docker exec -it con1 sh
<br/>cd var/log/nginx
<br/>ls ----> access.log error.log
<br/>ls-l yaparak da access.log ve error.log dosyalarının /dev/stdout ve /dev/stderr dosyalarına bağlandığını görebiliriz. İşte bu bağlama görevini de önceden de bahsettiğim gibi symlink gerçekleştirir.


