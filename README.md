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
</br> <p align="center">
  <img src="Ekran Görüntüsü (728).png" />
</p> 

<br/><br/>Konsolda bir dosyanın içeriğini görüntülemek yerine sonucu > kullanarak başka bir dosyaya yönlendirebilirsiniz. Komut satırı böyle olacaktır:
<br/>• cat kaynak.txt > hedef.txt
<br/>Eğer hedef dosya bulunmuyorsa o zaman komut bu dosyayı yaratacak veya var olan dosyanın üzerine yazacaktır.
<br/><br/>Mevcut konumdaki bütün metin dosyalarının içeriğini görüntülemek için aşağıdaki komutu terminal’de kullanın:
<br/>• cat *.txt

<br/><br/>Cat komutu satır sonlarını, $ karakterini her satırın sonunda görüntüleyerek işaretleyebilir. Bu özelliği kullanmak için cat komutuyla birlikte -E seçeneğini kullanın:
<br/>•cat -E dosyaadi.txt

<br/><br/>Cat komutuyla bir dosyanın içeriklerini her satırın başında rakamlarla (satır numaralarıyla) görüntüleyebilirsiniz. Bu özelliği kullanmak için cat komutuyla birlikte -n seçeneğini kullanın:
<br/>•cat -n dosyaadi.txt
<br/> https://github.com/berilerzurum/Linux-komutlar-/blob/9296e7cef055acee93659c54efbe9337e02c3d1d/image/2.1.png

<br/><br/>Cat komutuyla ilgili daha fazla bilgi için cat’in kılavuz sayfasına man cat komutu ile ulaşabilirsiniz.
<br/>

Cat’in bir diğer kullanımı da << EOF >> ile olan kullanımıdır. Bu komutta çok satırlı olarak dosyaya metin ekleyebilmemizi sağlar. EOF komutunu yazarak dosyayı işimiz bittikten sonra kapatabiliriz.
Bunun örneğini de aşağıdaki linkten bulabilirsiniz.
<br/> https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/4.png



<br/><h3><ins>More</ins></h3>
<br/>more komutu cat ile aynı ile vazifelidir. Ancak more komutunun bir avantajı, tek sayfada gösterilemeyecek olan dosyalar okunurken, boşluk tuşu ile kaydırma olanağı sağlamasıdır.
<br/>• more file_path
 <br/>Ek olarak more komutu;
<br/>more +5 dosya.txt
<br/>5’inci satırdan itibaren dosya içeriğini çekmemizi sağlar.
<br/>>> more +/”kelime” dosya.txt
<br/>belirtilen kelime ile başlayan satırı çekmemizi sağlar.

<br/><h3><ins>Less</ins></h3>
<br/>Less komutu da more komutu gibi dosyayı görüntülemeye yarar fakat birkaç farkla.
<br/>•	Less içerik içinde ileri - geri yönlü hareket edebilirken, more ile sadece ileri yönlü hareket edilebilir
<br/>•	Less tüm dosya içeriğini belleğe almadığı için büyük dosyaları okumak için daha uygundur
<br/>•	Less more'a göre daha gelişmiştir (metin içinde arama, zip dosyasını okuma vb..) ve more yerine artık less tercih edilmektedir
<br/> G : basarsak sayfa sonuna gider.
<br/> g : basarsak sayfa başına gider.
<br/>“16g” : ile 16.satıra gider.
<br/>“u” : sayfa yarı yukarı
<br/>“d” : sayfa yarı aşağı
<br/>“k” : bir satır yukarı
<br/>“j” : bir satır aşağı

 
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

<br/> https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/tail.png


<br/>Tail komutuna yukarıdaki linkteki seçenekleri de ekleyerek, komutu daha spesifik işlemler için kullanabiliriz.
<br/>tail [options] <files>
<br/>• -n komutunu yukarıda örneklendirmiştik. Satır olarak sınırlayıp çıktıyı verir.
<br/>-> tail -n 5 dosya.txt komutu ile dosyanın son 5 satırı görüntülenir. 
<br/>• -c komutu da dosya görüntülemeyi byte olarak sınırlayarak çıktıyı verir.
<br/>->tail -c 5 dosya.txt komutu ile dosyadan son 5 byte görüntülenir.
<br/>• -q komutu ile birden çok dosya kullanırken, dosya adlarının çıktısını gizleyebiliriz.
<br/>->tail -q dosya.txt
<br/>• -v komutu -q komutunun tam tersine, dosya adlarının çıktısını verir.
<br/>->tail -v dosya.txt
<br/>v ve -q komutlarının örneklerine aşağıdaki linkten ulaşabilirsiniz.
<br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/1.png
 <br/>
<br/>• –retry komutu : Eğer dosyaya erişim yoksa tekrar dener, dosya yeni oluşturulduğu durumlar söz konusu olabilir. Kontrol edilmesini sağlar.
<br/>• -f komutu dosyaya eklenen verilerin çıktısını verir. Yani dosya içeriğini canlı olarak gösterir. Biz dosyayı okurken sürekli yeni eklemeler yapılıyorsa bunları canlı olarak görebilmemizi sağlar.
<br/>Birim zaman başına çok sayıda erişim varsa bu yaklaşım pratik değildir. Bu durumda, günlük o kadar hızlı değişir ki terminal verilerle dolup taşar.
 Canlı kuyruğun geçerli yürütmesini iptal etmek içinse "Ctrl + C" tuşuna basılması gerekir.
<br/>->tail -f dosya.txt
<br/>• --pid=PID komutu
<br/>-f seçeneğiyle birlikte kullanıldığında, belirtilen işlem kimliğine sahip işlem(PID), sona erdiğinde tail komutu sonlandırılır. Dosya yazma programı sonlandırıldığında, canlı kuyruğu iptal etmek için kullanışlıdır.
<br/>->tail -f dosya.txt –pid=1



<br/>

<h3><br/><ins>CD.</h3></ins>
<br/>Mevcut çalışma dizinini değiştirmek için cd(change directory) komutu kullanılır. Bu komut, kullanıcıların sistem dizinleri arasında gezinmesini sağlar. 
<br/>SYNTAX;
<br/>•cd [DIRNAME]
<br/> Mesela bulunduğumuz konumdan desktop konumuna geçmek istiyoruz. Bunun için aşağıdaki komutu, dizin adını girmemiz yeterlidir.
<br/>cd /home/user/Desktop

<br/>Bu komutun eşdeğeri  “cd ~/Desktop” komutudur.” ~ “ işareti kök dizini gösterir yani /home/user/ dizinidir.
 <br/>•cd ~ komutu /home/user dizinine gitmemizi sağlar.
 <br/>•cd – komutu bir önceki bulunduğumuz dizine geçmemizi sağlar. 
<br/> •cd .. komutu /home dizinine geçer.

<br/>
<h3><br/><ins>MKDIR.</h3></ins>
<br/>mkdir (make directory) yeni bir dizin oluşturmak için kullanılan komuttur. Syntax;
<br/>mkdir dizin_adı  şeklindedir.
<br/> Yukarıda yazıldığı gibi kullanıldığında yeni dizin şu anki dizinin içinde oluşturulur. 
<br/> • -p : (--parents) Eğer yoksa, gerekli üst dizinleri de oluşturur. Eğer bu dizinler zaten varsa bir hata iletisi göstermez. 
<br/>-p 'nin kullanılmasına bir örnek:
<br/>mkdir -p /geçici/a/b/c
<br/>Eğer /geçici/a dizini zaten varsa fakat /geçici/a/b dizini yoksa, mkdir , /geçici/a/b 'yi oluşturduktan sonra /geçici/a/b/c dizinini oluşturulur.

<br/> • -v : (--verbose) Oluşturulan her dizini ekranda gösterir. Çoğunlukla -p ile birlikte kullanılır.
<br/> • -m : Oluşturulan dizinin, erişim izinlerini belirler. Erişim izinleri ya sayısal olarak ya da r/w/x şeklinde belirtilmelidir. Genellikle bazı dizinlerin erişime engellenmesinde kullanılır.

<br/>•Aşağıdaki örnekte tam erişimli dosya yaratma işleminin komutu var.
<br/>mkdir -m 777 newDir
<br/>Bu komut mkdir -m=rwx <file> komutuna eş değerdir.
 
<br/>•Sadece okuma ve yazma işlemi için "mkdir -m=rw <file>"
<br/>•Sadece yazma işlemi için "mkdir -m=r <file>"
<br/>•Sadece okuma işlemi için "mkdir -m=w <file>"
<br/>•Sadece execute işlemi için "mkdir -m=x <file>"

<br/><h3><br/><ins>RMDIR.</h3></ins>
<br/>Mkdir’in tam tersine varolan dizini kaldırmak için kullanılır. SYNTAX;
<br/>•rmdir [DIRNAME]

<br/><h3><br/><ins>MV.</h3></ins>
<br/>mv(move) komutu dosya ve dizinleri taşımak için kullanılır, ayrıca dosya ve dizinleri yeniden adlandırmak için de kullanılabilir. SYNTAX; 
<br/>mv [eski] [yeni]
<br/>mv newDir ~/Documents/Dirs  
<br/>Dosya adını değiştirmek için; newdir olan dosya adını ChangedDir dosya adına çevirir.
<br/>mv newDir ChangedDir

<br/><h3><br/><ins>CP.</h3></ins>
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

<br/><h3><br/><ins>RM.</h3></ins>
<br/>Artık ihtiyacımız olmayan dosyaları kaldırmak için rm komutunu kullanırız.
<br/>rm myfile
<br/>Birden fazla dosyayı tek seferde kaldırmak istersek;
<br/>  rm dosya1 dosya2 dosya3  ; şeklinde komut girebiliriz.
<br/>-f (Silmeyi Zorla): Bir dosya yazmaya karşı korumalıysa, rm onayın kaldırılmasını ister. -f seçeneği bu küçük korumayı geçersiz kılar ve dosyayı zorla kaldırır.
<br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/7.png
<br/>-r komutu ile dosyanın içindeki ve onun tüm alt dizinindeki dosyaları siler.
<br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/8.png
<br/>rmdir -> boş klasörleri silmek için kullanılır.
<br/>rm -i -> interaktif modda çalışır ve sileceği her dosya için onay ister.
<br/>rm -rf /*  -> root dizinini ve altındaki bütün dosyaları siler.

<br/><h3><br/><ins>TOUCH.</h3></ins> 
<br/>Touch komutu dosya yaratmak içindir.
<br/>touch <filename>
<br/>Eğer bulunduğumuz dizinde oluşturmak istediğimiz dosya isimli dosya yok ise,
<br/>Yeni bir dosya yaratır. Dizinde aynı isimde dosya zaten bulunuyorsa, sadece dosyanın oluşturulma zamanı(timestamp) güncellenir.
<br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/ts1.png
<br/>Birden çok dosya yaratmak istersek dosya adlarını ard arda yazmamız yeterlidir.
<br/>touch dosya1 dosya2 dosya3
<br/>touch test{1..10} Bu komut, 1’den 10’a kadar test dosyası yaratmamızı sağlar (test1 test2 test3 … test10)
<br/>touch test_{a..j} Bu komut, a’dan j’ye kadar test dosyası yaratmamızı sağlar (test_a test_b test_c … test_j)
<br/> https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/ts3.png
 <br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/ts2.png

<br/><h3><br/><ins>>PWD.</h3></ins>
<br/>pwd Linux komutu, kökten (/) başlayarak geçerli (o anki bulunan, current) çalışma dizini yolunu yazdırır.
<br/>$pwd 
<br/>/home/user/Desktop

<br/><h3><br/><ins>WHOAMI.</h3></ins>
<br/>Bu komut çağrıldığında mevcut kullanıcının kullanıcı adını görüntüler.
<br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/9.png

<br/><h3><br/><ins>WHEREIS.</h3></ins>
<br/>whereis, belirli bir komut için binary (ikili), source (kaynak) ve manuel sayfa dosyalarının konumunu bulmanızı sağlayan bir komut satırı yardımcı programıdır. <br/>SYNTAX;
<br/>whereis [SEÇENEKLER] DOSYA-ADI...
<br/>Herhangi bir seçenek olmadan kullanıldığında, argüman olarak belirtilen komut için, binary (ikili), source (kaynak) ve manuel dosyalarını arar.

<br/>Varsayılan olarak whereis, ortam değişkenlerinde listelenen sabit kodlanmış yollarda ve dizinlerde komutun dosyalarını arar. 
<br/>whereis komutunun aradığı dizinleri bulmak için -l seçeneğini kullanabiliriz (whereis -l).

<br/>Örneğin, CAT komutu hakkında bilgi almak için aşağıdaki komutu yazabiliriz.
<br/>whereis cat
<br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/10.png
<br/>/usr/bin/cat  binary (ikili) dosyanın yolu, /usr/share/man/man1/cat.1.gz ise man dosyasının yeridir.
<br/>Ayrıca, whereis komutuna birden fazla argüman sağlayabilirsiniz.
<br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/11.png
<br/>Yalnızca komutun  binary (ikili) dosyalarını aramak için -b seçeneğini kullanabiliriz.
<br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/12.png
<br/>Yalnızca source dosyaları için -s, yalnızca man dosyalarının yeri için -m seçeneğini kullanabiliriz.
<br/>-u seçeneği, olağandışı girdilerin nerede aranacağını söyler. İstenen her türden, (binary (ikili), manuel ve kaynak) tam olarak bir girişi olmayan dosyalar, olağandışı dosyalar (komutlar) olarak kabul edilir.
<br/>Örneğin, /bin dizinindeki kılavuz sayfaları olmayan veya birden fazla belgeye sahip tüm binary (ikili) dosyaları aramak için aşağıdaki komutu yazabiliriz.
<br/>whereis -m -u *

<br/><h3><br/><ins>WHATIS.</h3></ins>
<br/>whatis komutu aranan içeriği kütüphane içerisinde arayarak sonucu ekrana yansıtır.
<br/>#whatis ping
<br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/13.png


<br/><h3><br/><ins>TAR.</h3></ins>
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

<br/><h3><br/><ins>UNZIP.</h3></ins>
<br/>Sıkıştırılmış zip dosyalarını çıkartır (extract). SYNTAX;
<br/>unzip file.zip

<br/><h3><br/><ins>GZIP.</h3></ins>
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

<br/><h3><br/><ins>NETSTAT.</h3></ins>
<br/>Netstat, sistem yöneticileri tarafından ağ yapılandırmasını ve etkinliğini değerlendirmek için kullanılan bir komut satırı aracıdır.
<br/># netstat -a | more  --> dinlenen ve dinlenmeyen tüm soketleri gösterir.
<br/>#netstat -at  -->tüm TCP portlarını listeler.
<br/># netstat -au -->tüm UDP portlarını listeler.
<br/>#netstat -l --> Sadece dinlenen portları listeler.
<br/># netstat -lt --> sadece dinlenen TCP portlarını listeler.
<br/># netstat -lu --> sadece dinlenen UDP portlarını listeler.
<br/># netstat -s --> tüm portların istatistiklerini listeler.
<br/># netstat -r --> Kernel routing (yönlendirme) bilgilerini listelemek için kullanılır.
<br/># netstat -i --> Ağ arayüzlerini (network interfaces) listeler.
<br/>#netstat -e  --> Ethernet İstatistiklerini Gösterir.


<br/><h3><br/><ins>NSLOOKUP.</h3></ins>
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

<br/><h3><br/><ins>NETCAT.</h3></ins>
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

<br/><h3><br/><ins>CHMOD.</h3></ins>
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

<br/><h3><br/><ins>CHOWN.</h3></ins>
<br/>Dosya Sahibini veya grubunu değiştirmek için” chown” komutu kullanılır.
<br/>Bir dosyanın sahipliğini değiştirmek için temel komut:
<br/>chown kullanici dosyaadi
<br/>Aynı dosya chownOrnegi.txt içinse sahipliği kökten, deneme adlı başka bir kullanıcıya değiştirmenize izin verir. Bu komutun bir örneği aşağıdaki gibidir:
<br/>chown deneme chownOrnegi.txt
<br/>Komut grubu değiştirmek için düzenlenebilir. Sahipliği ve grubu değiştirmek için temel formatsa:
<br/>chown kullanici[:grup] dosyaadi
<br/>Eğer aynı dosyayı chownOrnegi.txt deneme adlı sahibe ve grup1 adlı grupla değiştirmek istersek o zaman komut da böyle olacaktır:
<br/>chown deneme: grup1 chownOrnegi.txt
<br/>Eğer yalnızca grup değiştirilecekse sahipliği atlayabilirsiniz. Örnek olarak komut satırına bu komutu girin:
<br/>chown :grup1 chownOrnegi.txt
<br/>Tıpkı dosyalar gibi dizinler için de sahipliği ve grubu değiştirebilirsiniz. Bu komutun bir örneği böyledir:
<br/>chown deneme /TestUnix
<br/>Chown komutunun yinelemeli kullanımı tüm dizin ve alt dizinlerin sahipliğini veya grubunu kesin olarak değiştirir.

<br/>Yinelemeli bir kullanım içinse -R seçeneğini kullanmanız gerekir. İşte bu komutun bir örneği:
<br/>chown -R [KULLANICI][:GRUP] Dizin
<br/>Eğer TestUnix olarak çok alt dizinli bir dizine sahipseniz aşağıdaki komut bütün dizinlerin ve alt dizinlerin sahipliğini deneme kullanıcısına verecektir.
<br/>chown -R deneme /TestUnix
<br/>Linkler için chown:
<br/>chown deneme symlink

<br/><h3><br/><ins>USERADD.</h3></ins>
<br/>Linux makinenizi birden fazla kişi kullanıyorsa veya birden çok kullanıcıya erişim sağlayan bir sunucuyu yönetiyorsanız, kullanıcı oluşturmak için useradd komutu gereklidir. SYNTAX;
<br/>#sudo useradd [options] USERNAME
<br/>Örneğin; sudo useradd test 
<br/>Herhangi bir seçenek olmadan çalıştırıldığında useradd, /etc/default/useradd dosyasında belirtilen varsayılan ayarları kullanarak yeni bir kullanıcı hesabı oluşturur. 
<br/>Bu, test adında bir kullanıcı yaratacaktır, ancak bu sınırlı bir işlemdir ve ana dizini veya şifresi gibi başka yararlı şeyler yaratmaz!
<br/>Varsayılan ana dizine sahip bir kullanıcı oluşturmak için aşağıdaki seçeneği kullanın:
<br/>sudo useradd -m test
<br/>Bu kullanıcının artık bir /home/test dizini var.
<br/>Ana dizini değiştirmek için, aşağıdaki komutu girebilirsiniz.
<br/>sudo useradd -m -d /alternatif test

<br/><h3><br/><ins>PASSWD.</h3></ins>
<br/>passwd komutunu kullanarak yukarıda oluşturduğumuz test kullanıcısı için bir parola eklersiniz:#sudo passwd test. 
<br/>Bu, sizden kullanıcı için bir şifre girmenizi isteyecektir.

<br/><h3><br/><ins>IFCONFIG.</h3></ins>
<br/>Argümansız “ifconfig” komutu, tüm aktif arayüz ayrıntılarını görüntüler. ifconfig komutu ayrıca bir sunucunun atanan IP adresini kontrol etmek için de kullanılır.
<br/>https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/ifcon%20(1).png
<br/>-a argümanıyla birlikte aşağıdaki ifconfig komutu, sunucudaki tüm etkin veya etkin olmayan ağ arabirimlerinin bilgilerini görüntüler. eth0, lo, sit0 ve tun0 için sonuçları görüntüler.
<br/> https://github.com/berilerzurum/Linux-komutlar-/blob/cc67a0f30f9e37509633c25a1f53c6f59f42907b/image/ifcon%20(2).png
<br/>Belirttiğiniz bir interface'in bilgilerini görüntüleyebilirsiniz. (eth0 , eth1 vs.)
<br/>Örneğin; ifconfig eth0
<br/>Bir interface 'i aktif etmek için ifconfig kullanabilirsiniz. bunun için up parametresini kullanıyoruz.  ifconfig eth0 up
<br/>Tam tersi interface’i kapatmak içinse down parametresini kullanıyoruz.
<br/> - ifconfig eth0 down
<br/>Belirttiğimiz interface 'e ip atamak için kullanabiliriz. 
<br/>	İfconfig eth0 172.16.25.125
<br/>Belirttiğiniz interface 'e subnet mask 'ı  atamak için kullanabiliriz.
<br/>ifconfig eth0 netmask 255.255.255.224
<br/>Belirttiğiniz interface 'e broadcast ip'i atamak için kullanabiliriz.
<br/>ifconfig eth0 broadcast 172.16.25.63
<br/>Belirttiğiniz interface 'e ip , mask ve broadcast 'i tek satırda verebiliriz
<br/>ifconfig eth0 172.16.25.125 netmask 255.255.255.224 broadcast 172.16.25.63
<br/>ifconfig yardımcı programı, alias özelliğini kullanarak ek ağ arabirimlerini yapılandırmanıza olanak tanır.Örneğin; eth0'ın alias ağ arabirimini eklemek için aşağıdaki komut kullanılır.
<br/> Alias ağ adresinin aynı subnet maskesinde olduğunu lütfen unutmayın. Örneğin, eth0 ağ ip adresiniz 172.16.25.125 ise, alias ip adresi 172.16.25.127 olmalıdır.
<br/>ifconfig eth0:0 172.16.25.127
<br/>Alias network interface’i kaldırmak içinse aşağıdaki komutu girmeniz yeterlidir.
<br/>ifconfig eth0:0 down




<br/><h3><br/><ins>IPTABLES</h3></ins>
<br/>Siber olaylardan korunmaya öncelikle kendi alacağımız tedbirler ile başlamalıyız. Dosya izinlerimizi kontrol etmeli, kullandığımız yazılımların güncel olup olmadığına kendimizin karar vermesi lazım. Network trafiğimizin de kontrolünü ilk aşamada kendi belirlediğimiz kuralların yazılması ile başlamalıyız. Iptables komutu işte tam bu konuda bize yardımcı olan bir yapıdır. İşletim sistemlerinde dışarıdan gelebilecek zararlara karşı koruma sağlayan bazı yapılar bulunur. Bu yapılara örnek olarak güvenlik duvarları diyebiliriz. Windows için sistemde hazır olarak bulunan güvenlik duvarı Windows Defender’dır. Linux işletim sistemlerinde ise hazırda bulunan güvenlik duvarı ise iptables’tır.
<br/>Bu güvenlik duvarı sistemde görev yapan servislerin çalıştığı portlar üzerinde çalışır. İnternete bağlandığımız zaman ağ trafiği üzerindeki bütün veriler paketler halinde gönderilir. Linux kernel yapısında bu gelen ve giden trafik üzerinde hareket eden paketlerin paket filtreleme tablosu kullanarak daha önceden yazılan kurallara göre filtreleme yapabilmemizi sağlayan bir arayüz bulunur.
<br/>Iptables, bu paket filtreleme tablolarını kurmamızı, yönetmemizi ve incelememizi sağlar.
<br/>Iptables ile ağınıza gelen network trafiğini kontrol edebilir veya başka bir adrese yönlendirebilir.
<br/>Birden fazla tablo belirlenebilir ve her tablo birden fazla zincir yapısına sahip olabilir.
<br/>Zincir kuralların bütünüdür.
<br/>Her kural, ağ trafiği üzerinden gelen her bir paketin bu kurala uyduğundan ne yapılacağına karar veren bir yol haritasıdır.
<br/><br/>Kuralı sağlayan veya sağlamayan pakete ne olur?
<br/>ACCEPT (KABUL ET): Paketin ağ trafiği üzerinden geçmesine izin verir
<br/>DROP (REDDET): Paketin ağ trafiği üzerinden geçmesine izin vermez. Paketi gönderen kişiye paketin engellendiği haber edilmez.
<br/>REJECT (KABUL ETME): Paketin ağ trafiği üzerinden geçmesine izin vermez. Paketi gönderen kişiye paketin engellendiği haber edilir.
<br/>RETURN (GERİ ÇEVİR): Şimdiki zincirin pas geçilmesi ve çağrıldığı zincirde bir sonraki kurala geçilmesi gerektiği anlamına gelir.

<br/><br/>Paketlerin Yönleri nelerdir ?
<br/>INPUT: Gelen paketlerin kontrol edileceğini belirtmek için kullanırız. Gelen paketler port numarası, protokol türü ve source IP değerine göre engellenebilir veya paketin geçişine izin verilir.
<br/>FORWARD: Sistem tarafından yönlendirilen paketlerin kontrolü için kullanılır.
<br/>OUTPUT: Giden paketleri kontrolü için kullanılır.

<br/><br/>Iptables Genel Kural Yapısı
<br/>iptables -A <paketin yönü> -i <interface> -p <protokol tipi> -s <kaynak> — dport <port no.> -j <pakete ne olacak?>
<br/>A = Hangi zincir tipine eklemek istediğimizi belirtiyoruz. Input, Output, Forward zincirlerinden biri olabilir.
<br/>D = Belirtilen kuralın silinmesi için kullanılır. Yani daha önceden –A ile eklediğimiz kuralı bu sefer –D parametresi koyarak silebiliriz.
<br/>i = Hangi interface için bu kuralı uygulayacağımız söylüyoruz.
<br/>p = Hangi protokol için uygulayacağımız söylüyoruz. TCP, UDP vb. protokoller olabilir.
<br/>s = Gelen paketlerin IP adreslerini kontrol edilmesi için yazılır.
<br/>j = Bu paketin ne olacağı ile alakalı durumu belirtiriz. Paket ACCEPT, DROP veya RETURN edilebilir.

<br/><br/>Iptables Örnekleri
<br/>Spesifik Bir IP adresini engellemek
<br/>→ iptables -A INPUT -s xxx.xxx.xxx.xxx -j DROP
<br/>Açıklamak gerekirse INPUT a gelen paketlerden source IP adresi xxx.xxx.xxx.xxx olan paketleri DROP yani kabul etme diyoruz. Yani bir IP adresinin zararlı olduğunu biliyorsak bu komutu kullanabiliriz.
<br/>→iptables -A INPUT -p tcp -s xxx.xxx.xxx.xxx -j DROP
<br/>Bu örnekte ise bir IP adresinin bize TCP paketleri atmasını engellemek için yazdığımız bir kuraldır. İlk kuralda herhangi bir paket tipi atarsa paket direk DROP edilecekti. Ama buradaki kuralda sadece TCP paketi atarsa engellemeyi tercih etmişiz.
<br/>Engellenen IP adresinin Engeleni Kaldırmak (Kural Silmek)
<br/>→ iptables -D INPUT -s xxx.xxx.xxx.xxx -j DROP
<br/>Önceki örnekte –A parametresi ile bu kuralı eklemiştik. Şimdi daha sonra eğer karar değiştirirsek yani kuralı silmek istersek bu önceden yazmış olduğun kuralın aynısını yazarak bu sefer –D parametresi ile silebiliriz
<br/>Belli bir portu engellemek
<br/>→iptables -A OUTPUT -p tcp — dport <port numarası> -j DROP
<br/>Kullanmadığınız portların durumunu belirtin. Kendiniz için alabileceğiniz en büyük güvenlik önlemi budur. Eğer bir portu kullanmayacaksınız onu manuel olarak kapatmanız gerekir. Böylelikle olası bir saldırı durumda dışarıya veri sızıntısını engelleyebilirsiniz.
<br/>→iptables -A INPUT -p tcp — dport xxx -j DROP
<br/>Bu kuralda ise benim bilgisayarımdan dışarıya giden ve xxx portunu kullanan tüm paketler drop edilir. Bu kuralın mantığı ise dışarıdan gelen herhangi bir paketin xxx numaralı port ile olan iletişimini kesiyorum. Gelen paketleri DROP ediyorum.
<br/>Ping İsteklerinin Engellenmesi
<br/>→iptables -A INPUT -p icmp -i eth0 -j DROP
<br/>Günümüzde zafiyet taraması yapan araçlar bir ağda çalışan bilgisayarın varlığını tespit edebilmek için o bilgisayarlara ping paketi gönderir. Bu pakete cevap verilirse de saldırgan sizin o ağ içinde olan bir bilgisayar diye işaretleyerek hedef haline gelirsiniz. Biz de bu durumdan kurtulmak için gelen ping paketlerini engelleyebiliriz. Ping paketleri icmp protokolünü kullanır ve eth0 ise bizim kendi network kartımızın interface değeridir.
<br/>DoS ataklardan korunmak
<br/>→iptables -A INPUT -p tcp — dport 80 -m limit — limit 25/minute — limit-burst 100 -j ACCEPT
<br/>Iptables ile network kartımıza gelen trafiği yönetebileceğimiz söylemiştik. DoS saldırılarından korunmak üzere kendimiz de bir şeyler yapabiliriz. 80 portunu HTTP bağlantısı kullanır. Dışarıdan gelen ve 80 portunu kullanan paketlerden sayısı dakika başına belirledğimiz sayısı aşmadığı sürece kabul edilmesini söylediğimiz kuralı yazdık.


<br/><h3><br/><ins>TRACEROUTE.</h3></ins>
<br/>Tracert bir sorgulama komutudur. Neyi sorguladığına gelecek olursak hedefe giden yoldaki durakları gösterir. Paket transferi sırasında hatanın kaynağını bulmada yardımcı olur. Tracert bu işlemi yaparken İnternet Denetim İletisi Protokolü (ICMP) ve Ip yaşam süresi (TTL) değerlerini kullanılır. Bu komut Windowsta “tracert <IP address>” ile çalışır.
<br/>En sık kullanılan parametreler
<br/>-d: IP adreslerinin bilgisayar çözümlenmesini yapmadan sonuç verir. Yani 212.156.38.21.static.turktelekom.com.tr [212.156.38.21] yerine sadece 212.156.38.21 verir.
<br/>-j: ana bilgisayar listesi (Ana bilgisayar listesinde zorunlu olmayan kaynak yolunu belirtir)
<br/>-h: en fazla atlama sayısı (Hedef aranırken kullanılacak en fazla atlama sayısını belirtir)
<br/>-w: zaman aşımı (Her yanıt için milisaniye olarak belirtilen zaman aşımı değeri kadar bekler)

<br/><h3><br/><ins>IP komutları.</h3></ins>
<br/>IP komutu, sistem ve ağ yöneticileri için bir Linux ağ aracıdır. IP, İnternet Protokolü anlamına gelir ve adından da anlaşılacağı gibi, araç ağ arayüzlerini <br/>yapılandırmak için kullanılır.
<br/>Daha eski Linux dağıtımları, benzer şekilde çalışan ”ifconfig“ komutunu kullanırdı. Ancak ifconfig, ip komutuna kıyasla sınırlı bir yetenek yelpazesine sahiptir.
<br/>SYNTAX;
<br/>ip [OPTION] OBJECT {COMMAND | help}
<br/>Sık kullanılan objeler;
<br/>1. link (l) –network interfaceleri görüntülemek ve değiştirmek için kullanılır.
<br/>2. address (addr/a) –protocol addreslerini (IP, IPv6) görüntülemek ve değiştirmek için kullanılır.
<br/>3. route (r) –routing tablosunu görüntülemek ve değiştirmek için kullanılır.
<br/>4. neigh (n) – komşu nesneleri (ARP tablosu) görüntülemek ve işlemek için kullanılır.

<br/><br/>Örneğin;
<br/>Link için;<br/>
<br/>Mevcut tüm aygıtların link-layer bilgilerini görmek için şu komutu kullanın:
<br/>ip link show
<br/>Belirli bir aygıt için bilgileri görüntülemesini istiyorsanız, aşağıdakini yazın:
<br/>ip link show dev [cihaz]
<br/>Tüm ağ arabirimlerinin istatistiklerini (aktarılan veya bırakılan paketler, hatalar gibi ayrıntılar) görmek için şunu kullanın:
<br/>ip -s link
<br/>Yalnızca çalışan arayüzlerin listesini görmek için şunu kullanın:
<br/>ip link ls up
<br/>Bir ağ arayüzünü (çevrimiçi) açmak istiyorsanız, şu komutu kullanın:
<br/>ip link set[interface] up
<br/>Aşağıdakileri girerek bir arayüzü (çevrimdışı) devre dışı bırakın:
<br/>ip link set[interface] down

<br/>Address için;
<br/><br/>IPv4 addreslerini listelemek için:
<br/>ip -4 addr
<br/>IPv6 addreslerini listelemek için:
<br/>ip -6 addr
<br/>Bir arayüze IP atamak istersek:
<br/>ip addr add [ip_address] dev [interface]
<br/>Bir interfce’e broadcast address eklemek istersek;
<br/>ip addr add brd [ip_address] dev [interface]
<br/>Bir interface den IP adresini kaldırmak istersek;
<br/>ip addr del [ip_address] dev [interface]

 <br/>Route için;
<br/><br/>Tüm route girişlerini listelemek istersek;
<br/>ip route -ya da- ip route list
<br/>Yukarıdaki komutlarla çıktı, kerneldeki tüm route girişlerini görüntüler. Aramayı daraltmanız gerekirse, SELECTOR nesnesini ekleyin:
<br/>ip route list SELECTOR
<br/>Distinct network için;
<br/>ip route list [ip_address]
<br/>Belirli bir cihazda erişilebilen routing tablosuna yeni bir giriş eklemek için;
<br/>ip route add [ip_address] dev [interface]  
<br/>Ya da gateway aracılığı ile;
<br/>ip route add [ip_address] via [gatewayIP]
<br/>Varolan routing table’ı silmek için aşağıdaki komutları deneyin.
<br/>ip route del [ip_address]
<br/>ip route del default
<br/>ip route del [ip_address] dev [interface]

 <br/>Neigh için;
<br/><br/>neighbor table’ları görüntülermek için;
<br/>ip neigh show
<br/>yeni giriş eklemek için;
<br/>ip neigh add [ip_address] dev [interface]
<br/>ARP girişini silmek için;
<br/>ip neigh del [ip_address] dev [interface]











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



 
 ![tail](https://user-images.githubusercontent.com/50303910/189340611-55ade941-6c41-42dd-baf2-5c15edbe4e36.png)
 
 <p align="center">
  <img src="image/ifcon (2).png" />
</p>
