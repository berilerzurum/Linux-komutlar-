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

<br/><br/>Cat komutuyla bir dosyanın içeriklerini her satırın başında rakamlarla (satır numaralarıyla) görüntüleyebilirsiniz. Bu özelliği kullanmak için cat komutuyla birlikte -n seçeneğini kullanın:
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

<br/>---------------LINKKKK


<br/>Tail komutuna yukarıdaki seçenekleri de ekleyerek, komutu daha spesifik işlemler için kullanabiliriz.
<br/>tail [options] <files>
<br/>-n komutunu yukarıda örneklendirmiştik. Satır olarak sınırlayıp çıktıyı verir.
<br/>-> tail -n 5 dosya.txt komutu ile dosyanın son 5 satırı görüntülenir. 
<br/>-c komutu da dosya görüntülemeyi byte olarak sınırlayarak çıktıyı verir.
<br/>->tail -c 5 dosya.txt komutu ile dosyadan son 5 byte görüntülenir.
<br/>-q komutu ile birden çok dosya kullanırken, dosya adlarının çıktısını gizleyebiliriz.
<br/>->tail -q dosya.txt
<br/>-v komutu -q komutunun tam tersine, dosya adlarının çıktısını verir.
<br/>->tail -v dosya.txt
<br/>--------------v ve -q komutlarının örneklerine aşağıdaki linkten ulaşabilirsiniz.
<br/>------------------------------LİNKKKKKKKKKKKK
<br/>–retry komutu : Eğer dosyaya erişim yoksa tekrar dener, dosya yeni oluşturulduğu durumlar söz konusu olabilir. Kontrol edilmesini sağlar.
<br/>-f komutu dosyaya eklenen verilerin çıktısını verir. Yani dosya içeriğini canlı olarak gösterir. Biz dosyayı okurken sürekli yeni eklemeler yapılıyorsa bunları canlı olarak görebilmemizi sağlar.
<br/>Birim zaman başına çok sayıda erişim varsa bu yaklaşım pratik değildir. Bu durumda, günlük o kadar hızlı değişir ki terminal verilerle dolup taşar.
 Canlı kuyruğun geçerli yürütmesini iptal etmek içinse "Ctrl + C" tuşuna basılması gerekir.
<br/>->tail -f dosya.txt
<br/>--pid=PID komutu
<br/>-f seçeneğiyle birlikte kullanıldığında, belirtilen işlem kimliğine sahip işlem(PID), sona erdiğinde tail komutu sonlandırılır. Dosya yazma programı sonlandırıldığında, canlı kuyruğu iptal etmek için kullanışlıdır.
<br/>->tail -f dosya.txt –pid=1



<br/>

<br/>CD.
<br/>Mevcut çalışma dizinini değiştirmek için cd(change directory) komutu kullanılır. Bu komut, kullanıcıların sistem dizinleri arasında gezinmesini sağlar. 
<br/>SYNTAX;
<br/>cd [DIRNAME]
<br/> Mesela bulunduğumuz konumdan desktop konumuna geçmek istiyoruz. Bunun için aşağıdaki komutu, dizin adını girmemiz yeterlidir.
<br/>cd /home/user/Desktop

<br/>Bu komutun eşdeğeri  “cd ~/Desktop” komutudur.” ~ “ işareti kök dizini gösterir yani /home/user/ dizinidir.
 <br/>cd ~ komutu /home/user dizinine gitmemizi sağlar.
 <br/>cd – komutu bir önceki bulunduğumuz dizine geçmemizi sağlar. 
<br/> cd .. komutu /home dizinine geçer.

<br/><br/>MKDIR.
<br/>mkdir (make directory) yeni bir dizin oluşturmak için kullanılan komuttur. Syntax;
<br/>mkdir dizin_adı  şeklindedir.
<br/> Yukarıda yazıldığı gibi kullanıldığında yeni dizin şu anki dizinin içinde oluşturulur. 
<br/> • -p : (--parents) Eğer yoksa, gerekli üst dizinleri de oluşturur. Eğer bu dizinler zaten varsa bir hata iletisi göstermez. 
<br/>-p 'nin kullanılmasına bir örnek:
<br/>mkdir -p /geçici/a/b/c
<br/>Eğer /geçici/a dizini zaten varsa fakat /geçici/a/b dizini yoksa, mkdir , /geçici/a/b 'yi oluşturduktan sonra /geçici/a/b/c dizinini oluşturulur.

<br/> • -v : (--verbose) Oluşturulan her dizini ekranda gösterir. Çoğunlukla -p ile birlikte kullanılır.
<br/> • -m : Oluşturulan dizinin, erişim izinlerini belirler. Erişim izinleri ya sayısal olarak ya da r/w/x şeklinde belirtilmelidir. Genellikle bazı dizinlerin erişime engellenmesinde kullanılır.

<br/>Aşağıdaki örnekte tam erişimli dosya yaratma işleminin komutu var.
<br/>mkdir -m 777 newDir
<br/>Bu komut mkdir -m=rwx <file> komutuna eş değerdir.
<br/>Sadece okuma ve yazma işlemi için "mkdir -m=rw <file>"
<br/>Sadece yazma işlemi için "mkdir -m=r <file>"
<br/>Sadece okuma işlemi için "mkdir -m=w <file>"
<br/>Sadece execute işlemi için "mkdir -m=x <file>"

<br/><br/>RMDIR.
<br/>Mkdir’in tam tersine varolan dizini kaldırmak için kullanılır. SYNTAX;
<br/>rmdir [DIRNAME]

<br/><br/>MV.
<br/>mv(move) komutu dosya ve dizinleri taşımak için kullanılır, ayrıca dosya ve dizinleri yeniden adlandırmak için de kullanılabilir. SYNTAX; 
<br/>mv [eski] [yeni]
<br/>mv newDir ~/Documents/Dirs  
<br/>Dosya adını değiştirmek için; newdir olan dosya adını ChangedDir dosya adına çevirir.
<br/>mv newDir ChangedDir

<br/><br/>CP.
<br/>Dosya ve dizinleri kopyalamaya yarayan bir araç komutudur. 
<br/>cp newDir ~/Documents/Dirs
<br/>Komut, newDir dizininin içeriğini ~/Documents/Dirs içine kopyalayacaktır. newDir'in bulunduğu yerden kaldırılmayacağını unutmayın. Sadece kopyalanır.
<br/>CP komutunun;
<br/>Bir dosyayı başka bir dosyaya kopyalamaya, 
<br/>Birden çok dosyayı bir dizinin içine kopyalamaya veya
<br/>Bir dizinin içeriğini tamamen başka bir dizinin içine kopyalama gibi farklı işlevler görmesi için yanına eklenen argümanlarla sağlanabilecek üç ana modu vardır.

<br/>Bir dosyayı başka bir dosyaya kopyalamak:
<br/>cp kaynakdosya hedefdosya
<br/>Dosya veya dosyaları bir dizinin içine kopyalamak:
<br/>cp kaynakdosya... hedefdizin
<br/>Bir dizinin içeriğini başka bir dizinin içine kopyalamak (-r veya -R argümanları kullanılmak zorundadır):
<br/>cp -r|-R kaynakdizin hedefdizin

<br/>Peki, bulunduğumuz dizindeki tüm *.sql uzantılı dosyaların oluşturulmuş /db_yedek isimli bir başka klasöre kopyalanmasını istersek;
<br/>cp *.sql db_yedek/
<br/>-a dosyaya ait file mode, ownership, timestamps ve eğer mümkünse attributes: context, links, xattr verilerini aktarır.
<br/>-v işlemle ilgili süreci döker.
<br/>-R ya da -r ; klasör yapısını olduğu gibi kopyalar. Dizin ağacındaki tüm dosyaları, yani bir dizin ve onun alt dizinindeki tüm dosyaları kopyalar.

<br/><br/>RM.
<br/>Artık ihtiyacımız olmayan dosyaları kaldırmak için rm komutunu kullanırız.
<br/>rm myfile
<br/>Birden fazla dosyayı tek seferde kaldırmak istersek;
<br/>  rm dosya1 dosya2 dosya3  ; şeklinde komut girebiliriz.
<br/>-f (Silmeyi Zorla): Bir dosya yazmaya karşı korumalıysa, rm onayın kaldırılmasını ister. -f seçeneği bu küçük korumayı geçersiz kılar ve dosyayı zorla kaldırır.
<br/>------------------------LINKKKK
<br/>-r komutu ile dosyanın içindeki ve onun tüm alt dizinindeki dosyaları siler.
<br/>-------------------------------LINKKKKKKKKKK
<br/>rmdir -> boş klasörleri silmek için kullanılır.
<br/>rm -i -> interaktif modda çalışır ve sileceği her dosya için onay ister.
<br/>rm -rf /*  -> root dizinini ve altındaki bütün dosyaları siler.

<br/><br/>TOUCH. 
<br/>Touch komutu dosya yaratmak içindir.
<br/>touch <filename>
<br/>Eğer bulunduğumuz dizinde oluşturmak istediğimiz dosya isimli dosya yok ise,
<br/>Yeni bir dosya yaratır. Aynı isimde dosya zaten bulunuyorsa, sadece dosyanın oluşturulma zamanı(timestamp) güncellenir.
<br/>----------------------LINK
<br/>Birden çok dosya yaratmak istersek dosya adlarını ard arda yazmamız yeterlidir.
<br/>touch dosya1 dosya2 dosya3
<br/>touch test{1..10} Bu komut, 1’den 10’a kadar test dosyası yaratmamızı sağlar (test1 test2 test3 … test10)
<br/>touch test_{a..j} Bu komut, a’dan j’ye kadar test dosyası yaratmamızı sağlar (test_a test_b test_c … test_j)
<br/>-----------LINK

<br/><br/>PWD.
<br/>pwd Linux komutu, kökten (/) başlayarak geçerli (o anki bulunan, current) çalışma dizini yolunu yazdırır.
<br/>$pwd 
<br/>/home/user/Desktop

<br/><br/>WHOAMI.
<br/>Bu komut çağrıldığında mevcut kullanıcının kullanıcı adını görüntüler.
<br/>--------------------------------LINKKKKKKKKK

<br/><br/>WHEREIS.
<br/>whereis, belirli bir komut için binary (ikili), source (kaynak) ve manuel sayfa dosyalarının konumunu bulmanızı sağlayan bir komut satırı yardımcı programıdır. <br/>SYNTAX;
<br/>whereis [SEÇENEKLER] DOSYA-ADI...
<br/>Herhangi bir seçenek olmadan kullanıldığında, argüman olarak belirtilen komut için, binary (ikili), source (kaynak) ve manuel dosyalarını arar.

<br/>Varsayılan olarak whereis, ortam değişkenlerinde listelenen sabit kodlanmış yollarda ve dizinlerde komutun dosyalarını arar. 
<br/>whereis komutunun aradığı dizinleri bulmak için -l seçeneğini kullanabiliriz (whereis -l).

<br/>Örneğin, CAT komutu hakkında bilgi almak için aşağıdaki komutu yazabiliriz.
<br/>whereis cat
<br/>-------------------------------------------LINKKKKKKKKKKKK
<br/>/usr/bin/cat  binary (ikili) dosyanın yolu, /usr/share/man/man1/cat.1.gz ise man dosyasının yeridir.
<br/>Ayrıca, whereis komutuna birden fazla argüman sağlayabilirsiniz.
<br/>------------------------------------------LINK
<br/>Yalnızca komutun  binary (ikili) dosyalarını aramak için -b seçeneğini kullanabiliriz.
<br/>----------------------------LINKKKKKKKKKK
<br/>Yalnızca source dosyaları için -s, yalnızca man dosyalarının yeri için -m seçeneğini kullanabiliriz.
<br/>-u seçeneği, olağandışı girdilerin nerede aranacağını söyler. İstenen her türden, (binary (ikili), manuel ve kaynak) tam olarak bir girişi olmayan dosyalar, olağandışı dosyalar (komutlar) olarak kabul edilir.
<br/>Örneğin, /bin dizinindeki kılavuz sayfaları olmayan veya birden fazla belgeye sahip tüm binary (ikili) dosyaları aramak için aşağıdaki komutu yazabiliriz.
<br/>whereis -m -u *

<br/><br/>WHATIS.
<br/>whatis komutu aranan içeriği kütüphane içerisinde arayarak sonucu ekrana yansıtır.
<br/>#whatis ping
<br/>-------------------LINK


<br/><br/>TAR.
<br/>Tar komutu, bir grup dosyayı bir arşive sıkıştırmak için kullanılır. Komut ayrıca tar arşivlerini çıkarmak, korumak veya değiştirmek için de kullanılır. Tar <br/>dosyaların veya klasörlerin özelliklerini değiştirmez. Sıkıştırma işlemi yapılırken izinler ve diğer özellikler sabit kalır
<br/>Syntax:
<br/>tar [options] [archive-file] [file or directory to be archived]

<br/>Options:
<br/>-c : Creates archive (.tar file)
<br/>-x : Extracts the archive
<br/>-f : creates archive with given filename
<br/>-t : displays or lists files in archived file
<br/>-u : archives and adds to an existing archive file
<br/>-v : Displays verbose information
<br/>-A : Concatenates the archive files
<br/>-z : compresses the tar file using gzip
<br/>-j : compresses the tar file using bzip2
<br/>-W : Verifies an archive file
<br/>-r : updates or adds file or directory in already existing .tar file

<br/>Linux’da Bir .tar Arşiv Dosyası Oluşturma
<br/>tar -cvf ornekArsiv.tar /home/ornekArsiv  -- Bu örnekte sıkıştırılması gereken dizin /home/ornekArsiv‘dir ve bunun sonucu olarak ornekArsiv.tar oluşacaktır.
<br/>tar cfv archive.tar file1 file2 file3  --> dosyalardan arşiv yaratır.
<br/>tar cfv archive.tar *.txt -> Geçerli dizindeki tüm .txt dosyalarının sıkıştırılmamış bir arşivini oluşturur.

<br/>.tar.gz Dosyası Oluşturma:
<br/>tar -cvzf ornekArsivArchive.tar.gz /home/ornekArsiv

<br/>Ek z seçeneği gzip sıkıştırılmasını temsil eder. Alternatif olarak .tar.gz dosyasına oldukça benzer olan .tgz dosyası oluşturabilirsiniz. Bunun bir örneğiyse:
<br/>tar -cvzf ornekArsiv.tgz /home/ornekArsiv

<br/>tar.bz2 Dosyası Oluşturma:
<br/>.bz2 dosyası gzip’e kıyasla daha fazla sıkıştırılma sağlar. Ancak, sıkıştırma ve sıkıştırma işlemini geri almak daha uzun sürecektir. Bunu oluşturmak için -j seçeneğini kullanmanız gerekir. Bu işlemin bir örneğiyse:
<br/>tar -cvjf ornekArsiv.tar.bz2 /home/ornekArsiv

<br/>.tar Dosyalarını Açma
<br/>Linux tar komutu ayrıca bir dosyanın içindekileri çıkarmak için kullanılabilir. Aşağıdaki komut dosyaları mevcut dizine çıkaracaktır:
<br/>tar -xvf Arsiv.tar  -> (Options: x = extract, f = file, v = verbose)
<br/>Eğer dosyaları farklı bir dizine çıkarmak istiyorsanız -C seçeneğini kullanabilirsiniz. Bunun bir örneğiyse aşağıdaki gibidir:
<br/>tar -xvf ornekArsiv.tar -C /home/ExtractedFiles/

<br/>Arşiv oluşturulduktan sonra içerikleri aşağıdakine benzer bir komut kullanarak listeleyebilirsiniz:
<br/>tar -tvf ornekArsiv.tar  arşivdeki tüm dosyaları gösterir.

<br/>Arşiv oluşturulduktan sonra tek bir dosya çıkartabilirsiniz. Bunun bir örneği aşağıdaki gibidir:
<br/>tar -xvf ornekArsiv.tar example.sh
<br/>Eğer birden fazla dosya çıkarmak istiyorsanız aşağıdaki formatta bir komut kullanın:
<br/>tar -xvf ornekArsiv.tar "file1" "file2"

<br/>Belirli türden dosyaları çıkarabildiğiniz gibi var olan bir arşive dosya da ekleyebilirsiniz. Bunu yapmak için karşılığı append olan -r seçeneğini <br/>kullanmalısınız. Tar hem dosya hem de dizin ekleyebilir.
<br/>Var olan ornekArsiv.tar‘a example.jpg dosyasını eklediğimiz örnek:
<br/>tar -rvf ornekArsiv.tar example.jpg

<br/><br/>UNZIP.
<br/>Sıkıştırılmış zip dosyalarını çıkartır (extract). SYNTAX;
<br/>unzip file.zip

<br/><br/>GZIP.
<br/>Gzip, bir dosyanın boyutunu azaltmanıza ve orijinal dosya modunu, sahipliği ve zaman damgasını korumanıza izin veren en popüler sıkıştırma algoritmalarından biridir. SYNTAX;
<br/>gzip filename -> bu komut ile filename dosyasının sıkıştırılmış dosyası oluşturulur ve eski(sıkıştırılmamış) dosya silinir.
<br/>Eğer önceki dosyanın da korunmasını istiyorsak ; gzip -k filename
<br/>Ya da gzip -c filename > filename.gz   komutları ile eski dosyayı koruyabiliriz.
<br/>gzip -r directory  dizindeki tüm dosyaları sıkıştırır.
<br/>Çoklu dosya sıkıştırma   gzip file1 file2 file3
 <br/>Gzip ile decompressing 
<br/>.gz dosyasını çıkartmak için (extract), -d seçeneği kullanılır:
<br/>gzip -d filename.gz
<br/>Diğer bir seçenek ise “gunzip”.  gunzip filename.gz

<br/><br/>NETSTAT.
<br/>Netstat, sistem yöneticileri tarafından ağ yapılandırmasını ve etkinliğini değerlendirmek için kullanılan bir komut satırı aracıdır.
<br/># netstat -a | more   dinlenen ve dinlenmeyen tüm soketleri gösterir.
<br/>#netstat -at  tüm TCP portlarını listeler.
<br/># netstat -au tüm UDP portlarını listeler.
<br/>#netstat -l   Sadece dinlenen portları listeler.
<br/># netstat -lt  sadece dinlenen TCP portlarını listeler.
<br/># netstat -lu  sadece dinlenen UDP portlarını listeler.
<br/># netstat -s  tüm portların istatistiklerini listeler.
<br/># netstat -r  Kernel routing (yönlendirme) bilgilerini listelemek için kullanılır.
<br/># netstat -i  Ağ arayüzlerini (network interfaces) listeler.
<br/>#netstat -e: Ethernet İstatistiklerini Gösterir.


<br/><br/>NSLOOKUP.
<br/>(name server lookup ) Alan adı ve IP adresi eşleşmesi bulmak veya DNS kayıtlarını sorgulamak/incelemek için kullanılabilen bir komut satırı aracıdır.
<br/>1) Aşağıdaki komut microsoft.com’un IP ‘sini sorgular;
<br/>nslookup microsoft.com
<br/>Alan adı yerine IP adresini vererek yukarıdaki işlemi tersten de yapabiliriz. Örneğin, komut:
<br/>nslookup 134.170.185.46
<br/>2) Aşağıdaki komut microsoft.com’un mail servisini sorgular.
<br/>nslookup -query=mx microsoft.com
<br/>3) Aşağıdaki komut microsoft.com’un nameserverlarını sorgular;
<br/>nslookup -type=ns microsoft.com
<br/>4) Aşağıdaki komut SOA kaydını sorgular;
<br/>nslookup -type=soa microsoft.com

<br/><br/>NETCAT.
<br/>Netcat’in komut halini “nc” olarak kullanıyoruz. Bu komutun temel amacı networkler arasındaki veri okuma / yazma işlemlerine dair işlemlerdir.
<br/>Netcat’in Temel SYNTAX’ı:
<br/>$ nc [options] host port
<br/>Host: Hedefin IP adresidir.
<br/>Port: Hedefin port numarası ya da numaralarıdır. Yani birden fazla port dinlenebilir.
<br/>Options:
<br/>-l: (listen mode) dinleme modu
<br/>-L: (Listen harder) Netcat’in sadece windows için hazırlanan sürümlerinde geçerlidir. Client tarafı connection’ı sonlandırsa bile dinleme modunu tekrar başlatır. <br/>Böylece Netcat’i ısrarlı bir dinleyici haline getirmiş olur.
<br/>-u: (UDP mode) ön tanımlı olarak TCP gelir. Bunun yerine UDP kullanmak için bu opsiyonu kullanabiliriz.
<br/>-p:(Local port) Listen modundayken dinlenen portun, client modundayken tüm paketlerin gönderileceği kaynak portun belirtildiği opsiyondur.
<br/>-e: Eğer connection olursa sonrasında program çalıştığında STDIN ve STDOUT ile iletişim kurmak için kullanılan opsiyondur
<br/>-n: DNS lookup’larda diğer tarafın makinelerinin isimlerinde değişikliklik/oynama olamaması için kullanılacak opsiyon.
<br/>-z: Zero-I/O modudur. Herhangibir datanın yollanmamasıdır. Sadece payload dışında bir paketin yollanması için kullanılan opsiyondur
<br/>-wN: Connection’ın timeout olması yani süresinin dolması halinde STDIN kapandıktan sonra N saniye daha beklenir. Bir Netcat client ya da listener’ı bu opsiyon ile yeni bir connection açmak için N saniye bekleyecektir. Eğer bu süre içinde yeni bir connection oluşmazsa Netcat çalışmayı durduracaktır.
<br/>-v: (Be verbose) Connection sırasında Standard Error’da olan mesajların ayrıntılı biçimde yazılmasını söyleyen opsiyondur.
<br/>-vv: (Be very verbose) Standard Errror’da -v opsiyonundan daha fazla detaylı yazılmasının söylendiği opsiyonel durumdur.
<br/>– Temel Netcat Client:

<br/>$ nc [Hedef IP adresi] [Port]
<br/>Burada client modda hedef IP üzerindeki istenilen portta bir connection başlatmış oluruz.
<br/>– Temel Netcat Listener
<br/>$ nc -l -p [Local Port]
<br/>Burada listener modunda istenilen yerel portta bir Netcat Listener’ı oluşturmuş oluruz.
<br/>Hem client hem de listener modda veri STDIN’den alınır ve network’den STDOUT’a verilir.

<br/><br/>CHMOD.
<br/>Linux sistemlerde kullanıcıların dosyalara erişim haklarını belirlemek için “chmod” komutu kullanılınır. Chmod un tam karşılığı change moddur.
<br/>Chmod erişim izinleri herzaman rwx şeklinde sıralanmaktadır.
<br/>r – Okuma izni ( Read permission )
<br/>w – Yazma izni ( Write permission )
<br/>x – Çalıştırma izni ( Execute permission )
<br/>Bazı chmod örnekleri :
<br/>rwx : Okuma, yazma ve çalıştırma erişim izinlerinin hepsi var.
<br/>rw- : Okuma ve yazma izinleri var, çalıştırma için izin yok.
<br/>r-x : Okuma ve çalıştırma izinleri var, yazma için izin yok.
<br/>-wx : Okuma için izin yok, yazma ve çalıştırma izinleri var.
<br/>r– : Sadece okuma hakkı var.
<br/>-w- : Sadece yazma hakkı var.
<br/>–x : Sadece çalıştırma hakkı var.
<br/>— : Hiçbir erişim hakkı yok.

<br/>Dosya tür çeşitlerini şu şekilde sıralayabiliriz :
<br/>* Normal bir dosya
<br/>d Dizin
<br/>b Özel blok dosyası
<br/>c Özel karakter dosyası
<br/>l Sembolik bağlantı dosyası
<br/>P Özel isimlendirilmiş pipe dosyası

<br/>Chmod izinleri için Operatörler
<br/>– İzinleri kaldır ( remove chmod permission )
<br/>+ İzinleri ekle ( add chmod permission )
<br/>= İzinleri koy ( set chmod permission )
<br/>Örneğin;
<br/>chmod +r deneme : deneme dosyasına okuma(r) izni vermiş olduk.
<br/>chmod go+r deneme* : ( * ) joker parametresi ile deneme ile başlayan tüm dosyaların grup ve diğer(other) userler tarafından okunması iznini verir.

<br/><br/>CHOWN.
<br/>Dosya Sahibini veya grubunu değiştirmek için” chown” komutu kullanılır.
<br/><br/>USERADD.
<br/><br/>PASSWD.











<h1> STDIN, STDOUT, STDERR </h1>

<br/>Linux sistemlerinde giriş-çıkış işlemleri stdin, stdout, stderr akış araçlarıyla sağlanır. Bunlar terminalin bizimle iletişim kurmak için oluşturduğu 3 temel noktadır.

<br/>stdin --> Klavyeden ya da başka bir uygulamadan giriş içerir.
<br/>stdout --> Uygulamanın çıktısıdır.
<br/>stderr --> Hata mesajı göndermek için kullanılan çıktıdır.

<br/>Örneğin; klavyeden bir veri girdik. Bu önce uygulamanın Stdin akışına gider, uygulama buna cevap oluşturursa, bu cevabı stdout çıkışına gönderir. Terminalde bu çıkışı izlediği için bunu yakalar ve ekranda gösterir, aynı şekilde bu akış sırasında herhangi bir error oluşursa terminal bunu da yakalar ve ekranda gösterir.

<br/>Mesela terminale ls/deneme komutunu girdik ama bulunduğumuz dizinde böyle bir klasör yok. Stderr bir hata mesajı üretir ve "no such file or directory" çıktısını gönderir. Ama dizinde olan bir dosyayı komut olarak girseydik Stdout bunu yakalayacak ve o çıktıyı gönderecekti.

<br/>Docker ile ilgili de birkaç örnek verelim.
<br/>Terminale --> docker run -d --name app deneme/app komutunu girerek bir konteyner oluşturalım.
<br/>Konteynerimiz başlangıçta app uygulaması çalışacak şekilde ayarlı. App --> merhaba ben app. çıktısını bastırıyor. Bu çıktıyı önce stdout'a gönderiyor. Lakin bizim terminalimiz konteynerin terminaline bağlı değil ve konteyner -d ile arkaplanda çalıştığı için mesaj arkaplanada oluştu fakat biz çıktıyı terminalde göremedik. 

<br/>Docker logs tam bu durumu çözebilecek bir komut. Docker logs konteyner çalıştığı sürece, biz logs komutunu girene kadar oluşan tüm logları (stdout,stderr) yakalıyor ve onları komutu girince listeliyor ve bana göremediğim mesajları görebilme imkanı sunuyor.

<br/>Bir başka docker komutu daha girelim.
<br/>docker container run -d --name cont1 -p 80:80 nginx bu komutu girdikten sonra 127.0.0.1 adresine baktığımızda nginx'in mesajını göreceğiz. Nginx'in bu websayfsına erişirken oluşturduğu tüm logları aşağıdaki komutu girerek görebileceğiz.
<br/>docker logs cont1
<br/>Mesela 127.0.0.1/deneme.html diye olmayan bir dosya dizini girelim. Bu oluşan 404 hata mesajını da logların arasında görebileceğiz.

<br/>Normalde nginx'in deamonı logları stdout,stderr akışına direkt olarak atmaz, access.log ve error.log dosyalarına yazar. Bu dosyalar, nginx'te stdout ve stderr akışına symlink ile bağlanarak bu dosyadakilerin akışta da görünmesini sağlar.

<br/>docker exec -it con1 sh
<br/>cd var/log/nginx
<br/>ls ----> access.log error.log
<br/>ls-l yaparak da access.log ve error.log dosyalarının /dev/stdout ve /dev/stderr dosyalarına bağlandığını görebiliriz. İşte bu bağlama görevini de önceden de bahsettiğim gibi symlink gerçekleştirir.


