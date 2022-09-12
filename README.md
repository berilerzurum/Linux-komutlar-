# Linux komutları

## _Dosya/dizin ile ilgili komutlar_
- cat
- more
- less
- head
- tail
- cd
- mkdir
- mv
- cp
- rm
- touch

<br/><br/><br/>

### 1) CAT

Cat komutu dosya içeriğini, terminal ekranından okumamızı sağlayan komuttur.
Cat komutunun, bu işlemin yanı sıra başka yararları da mevcuttur. Bunlara da değineceğim.


Örneğin; Linux terminalinde deneme.txt dosyasını oluşturup içine bir veya daha çok metin satırı ekleyelim ve Ctrl+C veya Ctrl+D ile çıkalım:
```shell
$ cat > deneme.txt
dosyanın içine
bu satırları yazıyorum
^C
```
- komutu ortamda deneme.txt dosyası olsa da olmasa da önce dosyayı oluşturur ardından içine yazı yazabilmemizi sağlar.
 
 `cat deneme.txt` komutu ile dosyayı okuyalım.
 
- Aynı şekilde birden fazla satırı Ctrl karakteri ile işaretler göndererek yazmamak için aşağıdaki şekilde EOF (End Of File) kullanabiliriz:

```shell
$ cat << EOF >> deneme.txt
dosyanın içine
bu satırları yazıyorum
EOF
```
 <p align="center">
  <img src="image/4.png" />
</p>


- Eğer ortamda önceden oluşturulmuş `deneme.txt` dosyası bulunuyorsa `cat > deneme.txt` komutu, önceki deneme.txt dosyasının içindeki verileri siler ve yazacağımız yeni verileri deneme.txt dosyasına yazmamızı sağlar.
- Eğer dosyanın üzerine yazmak istiyorsak **`cat >>deneme.txt`** komutunu kullanmamız gerekir. Bu şekilde eski veriler de yeni veriler de tutulmuş olur.
Bu yere kadar olan komutların terminaldeki örneklerine aşağıdaki linkten ulaşabilirsiniz.

![image](https://user-images.githubusercontent.com/50303910/189531045-e5b5eaf8-5f45-4c28-ae47-ab6b71ef5d87.png)

- Konsolda bir dosyanın içeriğini görüntülemek yerine, sonucu ">" kullanarak başka bir dosyaya yönlendirebilirsiniz. Komut satırı böyle olacaktır:
```shell
$ cat kaynak.txt > hedef.txt
```
-Eğer, hedef dosya bulunmuyorsa o zaman komut bu dosyayı yaratacak veya var olan dosyanın üzerine yazacaktır.

- Cat ile ilgili bir başka komut ise, mevcut konumdaki bütün metin dosyalarının içeriğini görüntülemek için kullandığımız komut. Bunun için aşağıdaki komutu terminal’de kullanın:
```shell
 $ cat *.txt
 ```

- Cat komutu satır sonlarını, "$" karakterini her satırın sonunda görüntüleyerek işaretleyebilir. Bu özelliği kullanmak için cat komutuyla birlikte -E seçeneğini kullanabiliriz.
```shell
$ cat -E dosyaadi.txt
 ```

- Cat komutuyla bir dosyanın içeriklerini her satırın başında rakamlarla (satır numaralarıyla) görüntüleyebilirsiniz. Bu özelliği kullanmak için cat komutuyla birlikte -n seçeneğini kullanın:
 ```shell
$ cat -n dosyaadi.txt
```
 <p align="center">
  <img src="image/2.1.png" />
</p>


-Cat komutuyla ilgili daha fazla bilgi için cat’in kılavuz sayfasına man cat komutu ile ulaşabilirsiniz.





<br/><br/><br/>
### 2) More
- more komutu cat ile aynı ile vazifelidir. Ancak more komutunun bir avantajı, tek sayfada gösterilemeyecek olan dosyalar okunurken, boşluk tuşu ile kaydırma olanağı sağlamasıdır.
- 
#### Syntax;

**_more `file_path`_** 

- Ek olarak more komutu;
```shell
 $ more +5 dosya.txt
 ```
şeklinde kullanılırsa 5’inci satırdan itibaren dosya içeriğini çekmemizi sağlar.

```shell
 $ more +/”kelime” dosya.txt
  ```
 şeklinde kullanılırsa belirtilen kelime ile başlayan satırı çekmemizi sağlar.
 
 
<br/><br/><br/>
 
 

### 3) Less
- Less komutu da more komutu gibi dosyayı görüntülemeye yarar fakat birkaç farkla.

1. 	Less içerik içinde ileri - geri yönlü hareket edebilirken, more ile sadece ileri yönlü hareket edilebilir
2.  Less tüm dosya içeriğini belleğe almadığı için büyük dosyaları okumak için daha uygundur
3.	 Less more'a göre daha gelişmiştir (metin içinde arama, zip dosyasını okuma vb..) ve more yerine artık less tercih edilmektedir.


•"G" : basarsak sayfa sonuna gider.

•"g" : basarsak sayfa başına gider.

•“16g” : ile 16.satıra gider.

•“u” : sayfa yarı yukarı

•“d” : sayfa yarı aşağı

•“k” : bir satır yukarı

•“j” : bir satır aşağı

 
<br/><br/><br/>
 
 
 
### 4) Head

Bir metin dosyasının ilk birkaç satırını görüntülemek için kullanılır. Örnek:
```shell
$ head dosya.txt
```


<br/><br/><br/>


### 5) Tail

Bir metin dosyasının son birkaç satırını görüntülemek için kullanılır. Örnek:
```shell
$ tail dosya.txt
```
- head ve tail komutları için varsayılan değer 10'dur. Ancak istenirse bu değer değiştirilebilir. Örnekler:
```shell
$ head -n 5 dosya.txt
```
```shell
$ tail -n 25 dosya.txt
```
- Birinci örnekte dosyanın başından itibaren 5 satır görüntülenir. 
- İkincisinde ise aynı dosyanın sonundan itibaren 25 satır görüntülenir. Eğer dosyanın satır sayısı belirtilen sayıdan az ise (veya sayı belirtilmediğinde 10'dan az ise) dosyada olan kadar satır görüntülenir.

<br/> <p align="center">
  <img src="image/tail.png" />
</p>


Tail komutuna yukarıdaki seçenekleri de ekleyerek, komutu daha spesifik işlemler için kullanabiliriz.

#### Syntax;

 **_tail [options] `files`_**  
 
1.  **-n** komutunu yukarıda örneklendirmiştik. Satır olarak sınırlayıp çıktıyı verir. Aşağıdaki komut örneği ile dosyanın son 5 satırı görüntülenir. 
 ```shell
$ tail -n 5 dosya.txt 
 ```
 
2.  **-c** komutu da dosya görüntülemeyi byte olarak sınırlayarak çıktıyı verir. Aşağıdaki komut örneği ile dosyadan son 5 byte görüntülenir.
 ```shell
$ tail -c 5 dosya.txt 
 ```
 
3.  **-q** komutu ile birden çok dosya kullanırken, dosya adlarının çıktısını gizleyebiliriz.
 ```shell
$ tail -q dosya.txt
 ```
4.  **-v** komutu -q komutunun tam tersine, dosya adlarının çıktısını verir.
 ```shell
$ tail -v dosya.txt
 ```
<p align="center">
  <img src="image/1.png" />
</p>

5. **retry** komutu : Eğer dosyaya erişim yoksa tekrar dener, dosya yeni oluşturulduğu durumlar söz konusu olabilir. Kontrol edilmesini sağlar.
 
6. **f** komutu dosyaya eklenen verilerin çıktısını verir. Yani dosya içeriğini canlı olarak gösterir. Biz dosyayı okurken, sürekli yeni eklemeler yapılıyorsa bunları canlı olarak görebilmemizi sağlar.
 
- Birim zaman başına çok sayıda erişim varsa bu yaklaşım pratik değildir. Bu durumda, günlük o kadar hızlı değişir ki terminal verilerle dolup taşar.
 
- Canlı kuyruğun geçerli yürütmesini iptal etmek içinse "Ctrl + C" tuşuna basılması gerekir.
```shell
$ tail -f dosya.txt
 ```
7. **--pid=PID** komutu
-f seçeneğiyle birlikte kullanıldığında, belirtilen işlem kimliğine sahip işlem(PID), sona erdiğinde tail komutu sonlandırılır. Dosya yazma programı sonlandırıldığında, canlı kuyruğu iptal etmek için kullanışlıdır.
 
```shell 
$ tail -f dosya.txt –pid=1
 ```

 
<br/><br/><br/>

 
 
### 6) Çalıma Dizinini Değiştirmek (cd) 
 
- Mevcut çalışma dizinini değiştirmek için cd(change directory) komutu kullanılır. Bu komut, kullanıcıların sistem dizinleri arasında gezinmesini sağlar. 

#### Syntax;
 
 **_cd `DIRNAME`_** 
 
- Mesela bulunduğumuz konumdan desktop konumuna geçmek istiyoruz. Bunun için aşağıdaki komutu girmemiz yeterlidir.
```shell 
$ cd /home/user/Desktop
 ```
- Yukarıdaki komutun eşdeğeri 
 
 ```shell 
 $ cd ~/Desktop
  ```
 komutudur. ” ~ “ işareti kök dizini gösterir yani /home/user/ dizinidir.
 
 1. cd ~ komutu /home/user dizinine gitmemizi sağlar.
 2. cd – komutu bir önceki bulunduğumuz dizine geçmemizi sağlar. 
 3. cd .. komutu /home dizinine geçer.

 
 
 
 

<br/><br/><br/>
### 7) Dizin Yaratmak (MKDIR)

- mkdir (make directory) yeni bir dizin oluşturmak için kullanılan komuttur. 
 
#### Syntax;
 
**_mkdir `dizin_adı`_** 
 
- Yukarıda yazıldığı gibi kullanıldığında yeni dizin şu anki dizinin içinde oluşturulur. 
 
- -p : (--parents) Eğer yoksa, gerekli üst dizinleri de oluşturur. Eğer bu dizinler zaten varsa bir hata iletisi göstermez. 
  -p 'nin kullanılmasına bir örnek: `mkdir -p /geçici/a/b/c`
 Eğer `/geçici/a` dizini zaten varsa fakat `/geçici/a/b` dizini yoksa, mkdir , `/geçici/a/b`'yi oluşturduktan sonra `/geçici/a/b/c` dizinini oluşturulur.

- -v : (--verbose) Oluşturulan her dizini ekranda gösterir. Çoğunlukla -p ile birlikte kullanılır.
- -m : Oluşturulan dizinin, erişim izinlerini belirler. Erişim izinleri ya sayısal olarak ya da r/w/x şeklinde belirtilmelidir. Genellikle bazı dizinlerin erişime engellenmesinde kullanılır.

- Aşağıdaki örnekte tam erişimli dosya yaratma işleminin komutlarını görebiliriz.
```shell  
$ mkdir -m 777 newDir
```
Ya da
 
 ```shell 
 $ mkdir -m=rwx <file> 
 ```
 komutlarını kullanabiliriz.
 
- Sadece <ins> okuma ve yazma </ins> işlemi için "mkdir -m=rw `file`"
 
- Sadece <ins>yazma </ins> işlemi için "mkdir -m=r `file`"
 
- Sadece <ins>okuma </ins> işlemi için "mkdir -m=w `file`"
 
- Sadece <ins>execute </ins> işlemi için "mkdir -m=x `file`"
 
 
 
 
 

<br/><br/><br/>
### 8) Dosya/Dizin Taşımak/Yeniden İsimlendirmek (mv)

`mv` (move) komutu dosya ve dizinleri yeniden adlandırmak ve/veya taşımak için kullanılabilir. 

 #### SYNTAX; 
 
**_mv [eski] [yeni]_** 
 
```shell
$ mv newDir ~/Documents/Dirs
```
 
Dosya adını değiştirmek için aşağıdaki komut kullanılır. 
 ```shell
$ mv newDir ChangedDir
 ```
newdir olan dosya adını ChangedDir dosya adına çevirir.
 
 
 
<br/><br/><br/>
 

### 9) Dosya ve dizinleri Kopyalamak (cp)
 
- Dosya ve dizinleri kopyalamaya yarayan bir araç komutudur. 
 
 ```shell
$ cp newDir ~/Documents/Dirs
 ```
- Komut, newDir dizininin içeriğini ~/Documents/Dirs içine kopyalayacaktır. newDir'in bulunduğu yerden kaldırılmayacağını unutmayın. Sadece kopyalanır.
  
- cp komutunun;
 
1. Bir dosyayı başka bir dosyaya kopyalamaya,
  <p align="center">
  <img src="image/6.png" />
</p>
 
2. Birden çok dosyayı bir dizinin içine kopyalamaya veya
 
3. Bir dizinin içeriğini, tamamen başka bir dizinin içine kopyalamak gibi farklı işlevler görmesi için, yanına eklenen argümanlarla sağlanabilecek üç ana modu vardır;

a) Bir dosyayı başka bir dosyaya kopyalamak:
 ```shell
$ cp kaynakdosya hedefdosya
   ```
b)  Dosya veya dosyaları bir dizinin içine kopyalamak:
 ```shell
$ cp kaynakdosya... hedefdizin
   ```
c) Bir dizinin içeriğini başka bir dizinin içine kopyalamak (-r veya -R argümanları kullanılmak zorundadır):
 ```shell
$ cp -r|-R kaynakdizin hedefdizin
 ```
- Peki, bulunduğumuz dizindeki tüm *.sql uzantılı dosyaların oluşturulmuş /db_yedek isimli bir başka klasöre kopyalanmasını istersek;
 ```shell
$ cp *.sql db_yedek/
   ```
 cp'nin diğer kullanımlarına birkaç örnek ise -a -v ve -R parametreleridir.
 
- -a dosyaya ait file mode, ownership, timestamps ve eğer mümkünse attributes: context, links, xattr verilerini aktarır.
- -v işlemle ilgili süreci döker.
- -R ya da -r ; klasör yapısını olduğu gibi kopyalar. Dizin ağacındaki tüm dosyaları, yani bir dizin ve onun alt dizinindeki tüm dosyaları kopyalar.

 
 
 
 
<br/><br/><br/>
 
### 10) Dosya Kaldırmak (rm) 
 
- Artık ihtiyacımız olmayan dosyaları kaldırmak için rm komutunu kullanırız.
 
#### Syntax;
 
 **_rm `filename`_**
  
- Birden fazla dosyayı tek seferde kaldırmak istersek;
  ```shell
  $ rm dosya1 dosya2 dosya3  
  ```
- -f (Silmeyi Zorla): Bir dosya yazmaya karşı korumalıysa, rm onayın kaldırılmasını ister. -f seçeneği bu küçük korumayı geçersiz kılar ve dosyayı zorla kaldırır.
  
<p align="center">
  <img src="image/7.png" />
</p>
  
- -r komutu ile dosyanın içindeki ve onun tüm alt dizinindeki dosyaları siler.
 
<p align="center">
  <img src="image/8.png" />
</p>
  
- rmdir -> boş klasörleri silmek için kullanılır. -p parametresi ile birlikte kullanılınca üst dizinleri de siler.
 
- rm -i -> interaktif modda çalışır ve sileceği her dosya için onay ister.
 
- rm -rf /*  -> root dizinini ve altındaki bütün dosyaları siler.

 
 
<br/><br/><br/>
 
### 11) Dosya Yaratmak (touch) 
 
- Touch komutu dosya yaratmak içindir.
 
#### Syntax;
 
**_touch `filename`_**
 
- Eğer bulunduğumuz dizinde oluşturmak istediğimiz dosya isimli dosya yok ise;
 --> Yeni bir dosya yaratır. 
- Dizinde aynı isimde dosya zaten bulunuyorsa;
 --> Sadece dosyanın oluşturulma zamanı(timestamp) güncellenir.

 <p align="center">
  <img src="image/ts1.png" />
</p>
 
- Birden çok dosya yaratmak istersek dosya adlarını ard arda yazmamız yeterlidir.
```Shell
 $ touch dosya1 dosya2 dosya3
 ```
 
 ```Shell
 $ touch test{1..10} 
  ```
- Bu komut, 1’den 10’a kadar test dosyası yaratmamızı sağlar (test1 test2 test3 … test10)
   <p align="center">
  <img src="image/ts3.png" />
</p>
 
 ```Shell
 $ touch test_{a..j}
 ```
 
- Aşağıdaki komut ise, a’dan j’ye kadar test dosyası yaratmamızı sağlar (test_a test_b test_c … test_j)
 <p align="center">
  <img src="image/ts2.png" />
</p>


<br/><br/><br/>



## _Genel Linux komutları_
- pwd,  
- whoami,
- whereis,
- whatis.


<br/><br/><br/>

### 1) Current(Şuanki) Dizini Öğrenme (pwd) 

pwd Linux komutu, kökten (/) başlayarak geçerli (o anki bulunan, current) çalışma dizini yolunu yazdırır.
```Shell
$ pwd
-> /home/user/Desktop
```


<br/><br/><br/>
### 2) whoami

- Bu komut çağrıldığında mevcut kullanıcının kullanıcı adını görüntüler.
<p align="center">
  <img src="image/9.png" />
</p>




<br/><br/><br/>
### 3) whereis
- whereis, belirli bir komut için binary (ikili), source (kaynak) ve manuel sayfa dosyalarının konumunu bulmanızı sağlayan bir komut satırı yardımcı programıdır.
  
#### Syntax;

  **_whereis [SEÇENEKER]  `filename`_**
  
- Herhangi bir seçenek olmadan kullanıldığında, argüman olarak belirtilen komut için, binary (ikili), source (kaynak) ve manuel dosyalarını arar.

- Varsayılan olarak whereis, ortam değişkenlerinde listelenen sabit kodlanmış yollarda ve dizinlerde komutun dosyalarını arar.
  
- whereis komutunun aradığı dizinleri bulmak için -l seçeneğini kullanabiliriz (whereis -l).

Örneğin, CAT komutu hakkında bilgi almak için aşağıdaki komutu yazabiliriz.
```Shell
$ whereis cat
```
<p align="center">
  <img src="image/10.png" />
</p>

- /usr/bin/cat  binary (ikili) dosyanın yolu,
- /usr/share/man/man1/cat.1.gz ise man dosyasının yeridir.


- Ayrıca, whereis komutuna birden fazla argüman sağlayabilirsiniz.
<p align="center">
  <img src="image/11.png" />
</p>

- Yalnızca komutun  binary (ikili) dosyalarını aramak için -b seçeneğini kullanabiliriz.
<p align="center">
  <img src="image/12.png" />
</p>

- Yalnızca source dosyaları için -s, yalnızca man dosyalarının yeri için -m seçeneğini kullanabiliriz.

- -u seçeneği, olağandışı girdilerin nerede aranacağını söyler. İstenen her türden, (binary (ikili), manuel ve kaynak) tam olarak bir girişi olmayan dosyalar, olağandışı dosyalar (komutlar) olarak kabul edilir.

- Örneğin, /bin dizinindeki kılavuz sayfaları olmayan veya birden fazla belgeye sahip tüm binary (ikili) dosyaları aramak için aşağıdaki komutu yazabiliriz.
```Shell
$ whereis -m -u *
```




### 4) whatis

- whatis komutu aranan içeriği kütüphane içerisinde arayarak sonucu ekrana yansıtır.
```Shell
$ whatis ping
```
<p align="center">
  <img src="image/13.png" />
</p>




<br/><br/><br/>

## _Sıkıştırılmış dosya ile ilgili komutlar_ 
- tar,
- gzip,
- unzip 

<br/><br/><br/>

### 1) .tar
  
- Tar komutu, bir grup dosyayı bir arşive sıkıştırmak için kullanılır. Komut ayrıca tar arşivlerini çıkarmak, korumak veya değiştirmek için de kullanılır.
- Tar dosyaların veya klasörlerin özelliklerini değiştirmez. Sıkıştırma işlemi yapılırken izinler ve diğer özellikler sabit kalır.
  
#### Syntax:

**_tar [options] [archive-file] [file or directory to be archived]_**

<br/>
Options:
<br/>•-c : Creates archive (.tar file)
<br/>•-x : Extracts the archive
<br/>•-f : creates archive with given filename
<br/>•-t : displays or lists files in archived file
<br/>•-u : archives and adds to an existing archive file
<br/>•-v : Displays verbose information
<br/>•-A : Concatenates the archive files
<br/>•-z : compresses the tar file using gzip
<br/>•-j : compresses the tar file using bzip2
<br/>•-W : Verifies an archive file
<br/>•-r : updates or adds file or directory in already existing .tar file


#### a) Linux’da Bir .tar Arşiv Dosyası Oluşturma

```Shell
$ tar -cvf ornekArsiv.tar /home/ornekArsiv  
```
 -->Bu örnekte sıkıştırılması gereken dizin /home/ornekArsiv‘dir ve bunun sonucu olarak ornekArsiv.tar oluşacaktır.
 
```Shell
$ tar cfv archive.tar file1 file2 file3
```
--> dosyalardan (file1, file2, file3) arşiv yaratır.

```Shell
$ tar cfv archive.tar *.txt 
```
-> Geçerli dizindeki tüm .txt dosyalarının sıkıştırılmamış bir arşivini oluşturur.



<br/>

#### b) .tar.gz Dosyası Oluşturma:

```Shell
$ tar -cvzf ornekArsivArchive.tar.gz /home/ornekArsiv
```

#### c) Alternatif olarak .tar.gz dosyasına oldukça benzer olan .tgz dosyası oluşturabilirsiniz. Bunun bir örneğiyse:

```Shell
$ tar -cvzf ornekArsiv.tgz /home/ornekArsiv
```

#### d) tar.bz2 Dosyası Oluşturma:
- .bz2 dosyası gzip’e kıyasla daha fazla sıkıştırılma sağlar. 
- Ancak, sıkıştırma ve sıkıştırma işlemini geri almak daha uzun sürecektir. Bunu oluşturmak için -j seçeneğini kullanmanız gerekir. Bu işlemin bir örneğiyse:

```Shell
$ tar -cvjf ornekArsiv.tar.bz2 /home/ornekArsiv
```

#### e) .tar Dosyalarını Açma
- Linux tar komutu ayrıca bir dosyanın içindekileri çıkarmak için kullanılabilir. Aşağıdaki komut dosyaları mevcut dizine çıkaracaktır:

```Shell
$ tar -xvf Arsiv.tar 
```
-> (Options: x = extract, f = file, v = verbose)

- Eğer dosyaları farklı bir dizine çıkarmak istiyorsanız -C seçeneğini kullanabilirsiniz. Bunun bir örneğiyse aşağıdaki gibidir:

```Shell
$ tar -xvf ornekArsiv.tar -C /home/ExtractedFiles/

```

- Arşiv oluşturulduktan sonra tek bir dosya çıkartabilirsiniz. Bunun bir örneği aşağıdaki gibidir:

```Shell
$ tar -xvf ornekArsiv.tar example.sh
```
  
-  Eğer birden fazla dosya çıkarmak istiyorsanız aşağıdaki formatta bir komut kullanın:

```Shell
$ tar -xvf ornekArsiv.tar "file1" "file2"
```



#### f) Arşiv oluşturulduktan sonra içerikleri aşağıdakine benzer bir komut kullanarak listeleyebilirsiniz:

```Shell
$ tar -tvf ornekArsiv.tar 
```
--> arşivdeki tüm dosyaları gösterir.


#### g) Belirli türden dosyaları çıkarabildiğiniz gibi var olan bir arşive dosya da ekleyebilirsiniz. Bunu yapmak için karşılığı append olan -r seçeneğini kullanmalısınız. Tar hem dosya hem de dizin ekleyebilir.

- Var olan ornekArsiv.tar‘a example.jpg dosyasını eklediğimiz örnek:
```Shell
$ tar -rvf ornekArsiv.tar example.jpg
```





<br/><br/><br/>

### 2) unzip

Sıkıştırılmış zip dosyalarını çıkartır (extract). 
#### Syntax;

```Shell
$ unzip file.zip
```



<br/><br/><br/>

### 3) .gzip
- Gzip, bir dosyanın boyutunu azaltmanıza ve orijinal dosya modunu, sahipliği ve zaman damgasını korumanıza izin veren en popüler sıkıştırma algoritmalarından biridir. 
- 
#### Syntax;

<br/>
```Shell
$ gzip filename 
```
a)Yukarıdaki komut ile filename dosyasının sıkıştırılmış dosyası oluşturulur ve eski(sıkıştırılmamış) dosya silinir.

b) Eğer önceki dosyanın da korunmasını istiyorsak ; 

```Shell
$ gzip -k filename
```
- Ya da,
```Shell
$ gzip -c filename > filename.gz  
```
komutları ile eski dosyayı koruyabiliriz.

c) Dizindeki tüm dosyaları sıkıştırmak istersek;
```Shell
$ gzip -r directory
```

d) Çoklu dosya sıkıştırma  
```Shell
$ gzip file1 file2 file3
 ```
e)  Decompressing 

- "gzip" ile, .gz dosyasını çıkartmak için (extract), -d seçeneği kullanılır:

```Shell
$ gzip -d filename.gz
```

- Diğer bir seçenek ise “gunzip”. 
```Shell
$ gunzip filename.gz
```
  
  
  
  <br/><br/><br/><br/>
  
## _Network(ağ) ile ilgili komutlar_
- netstat, 
- nslookup,
- netcat 
  
  
  <br/><br/><br/>
  
### 1)netsat

-Netstat, sistem yöneticileri tarafından ağ yapılandırmasını ve etkinliğini değerlendirmek için kullanılan bir komut satırı aracıdır.

<br/>

a) 
```Shell
$ netstat -a | more
```
--> dinlenen ve dinlenmeyen tüm soketleri gösterir.

b)
```Shell
$ netstat -at 
```
-->tüm TCP portlarını listeler.

c)
```Shell
$ netstat -au 
```
-->tüm UDP portlarını listeler.

d)
```Shell
$ netstat -l 
```
--> Sadece dinlenen portları listeler.

e)
```Shell
$ netstat -lt 
```
--> sadece dinlenen TCP portlarını listeler.

f)
```Shell
$ netstat -lu
```
--> sadece dinlenen UDP portlarını listeler.

g)
```Shell
$ netstat -s 
```
--> tüm portların istatistiklerini listeler.

h)
```Shell
$ netstat -r 
```
--> Kernel routing (yönlendirme) bilgilerini listelemek için kullanılır.

i)
```Shell
$ netstat -i 
```
--> Ağ arayüzlerini (network interfaces) listeler.

j)
```Shell
$ netstat -e  
```
--> Ethernet İstatistiklerini Gösterir.

  <br/><br/><br/>

### 2) nslookup

- (name server lookup ) Alan adı ve IP adresi eşleşmesi bulmak veya DNS kayıtlarını sorgulamak/incelemek için kullanılabilen bir komut satırı aracıdır.


a) Aşağıdaki komut microsoft.com’un IP ‘sini sorgular;
```Shell
$ nslookup microsoft.com
```
- Alan adı yerine IP adresini vererek yukarıdaki işlemi tersten de yapabiliriz. Örneğin, komut:
```Shell
$ nslookup 134.170.185.46
```
b) Aşağıdaki komut microsoft.com’un mail servisini sorgular.
```Shell
$ nslookup -query=mx microsoft.com
```
c) Aşağıdaki komut microsoft.com’un nameserverlarını sorgular;
```Shell
$ nslookup -type=ns microsoft.com
```
d) Aşağıdaki komut SOA kaydını sorgular;
```Shell
$ nslookup -type=soa microsoft.com
```



### 3) netcat

- Netcat’in komut halini “nc” olarak kullanıyoruz. Bu komutun temel amacı networkler arasındaki veri okuma / yazma işlemlerine dair işlemlerdir.

#### Netcat’in Temel SYNTAX’ı:

**_$ nc [options] host port_**

- Host: Hedefin IP adresidir.
- Port: Hedefin port numarası ya da numaralarıdır. Yani birden fazla port dinlenebilir.
- Options:

-l  --> (listen mode) dinleme modu

-L   --> (Listen harder) Netcat’in sadece windows için hazırlanan sürümlerinde geçerlidir. Client tarafı connection’ı sonlandırsa bile dinleme modunu tekrar başlatır. 
Böylece Netcat’i ısrarlı bir dinleyici haline getirmiş olur.

-u  -->  (UDP mode) ön tanımlı olarak TCP gelir. Bunun yerine UDP kullanmak için bu opsiyonu kullanabiliriz.

-p  --> (Local port) Listen modundayken dinlenen portun, client modundayken tüm paketlerin gönderileceği kaynak portun belirtildiği opsiyondur.

-e  -->  Eğer connection olursa sonrasında program çalıştığında STDIN ve STDOUT ile iletişim kurmak için kullanılan opsiyondur

-n  -->  DNS lookup’larda diğer tarafın makinelerinin isimlerinde değişikliklik/oynama olamaması için kullanılacak opsiyon.

-z  -->  Zero-I/O modudur. Herhangibir datanın yollanmamasıdır. Sadece payload dışında bir paketin yollanması için kullanılan opsiyondur

-wN  -->  Connection’ın timeout olması yani süresinin dolması halinde STDIN kapandıktan sonra N saniye daha beklenir. Bir Netcat client ya da listener’ı bu opsiyon ile yeni bir connection açmak için N saniye bekleyecektir. Eğer bu süre içinde yeni bir connection oluşmazsa Netcat çalışmayı durduracaktır.

-v  --> (Be verbose) Connection sırasında Standard Error’da olan mesajların ayrıntılı biçimde yazılmasını söyleyen opsiyondur.

-vv  -->  (Be very verbose) Standard Errror’da -v opsiyonundan daha fazla detaylı yazılmasının söylendiği opsiyonel durumdur.

– <ins> Temel Netcat Client: </ins>

```Shell
$ nc [Hedef IP adresi] [Port]
```
Burada client modda hedef IP üzerindeki istenilen portta bir connection başlatmış oluruz.

– <ins> Temel Netcat Listener </ins>
```Shell
$ nc -l -p [Local Port]
```
- Burada listener modunda istenilen yerel portta, bir Netcat Listener’ı oluşturmuş oluruz.
- Hem client hem de listener modda veri STDIN’den alınır ve network’den STDOUT’a verilir.






<br/><br/><br/><br/>
## _Kullanıcı işlemleri ile ilgili komutlar_ 

- chmod,
- chown, 
- useradd,
- passwd
- 
<br/><br/><br/>


### 1) chmod

- Linux sistemlerde kullanıcıların dosyalara erişim haklarını belirlemek için “chmod” komutu kullanılınır. Chmod un tam karşılığı change moddur.
- Chmod erişim izinleri herzaman rwx şeklinde sıralanmaktadır.

a) r – Okuma izni ( Read permission )
b) w – Yazma izni ( Write permission )
c) x – Çalıştırma izni ( Execute permission )


#### <ins> Bazı chmod örnekleri : </ins>

- rwx  ---> Okuma, yazma ve çalıştırma erişim izinlerinin hepsi var.
- rw-  ---> Okuma ve yazma izinleri var, çalıştırma için izin yok.
- r-x  ---> Okuma ve çalıştırma izinleri var, yazma için izin yok.
- -wx  ---> Okuma için izin yok, yazma ve çalıştırma izinleri var.
- r–   ---> Sadece okuma hakkı var.
- -w-  ---> Sadece yazma hakkı var.
- –x   ---> Sadece çalıştırma hakkı var.
- —    ---> Hiçbir erişim hakkı yok.

####  <ins> Dosya tür çeşitlerini şu şekilde sıralayabiliriz :  </ins>

- * Normal bir dosya
- d Dizin
- b Özel blok dosyası
- c Özel karakter dosyası
- l Sembolik bağlantı dosyası
- P Özel isimlendirilmiş pipe dosyası

####  <ins> Chmod izinleri için Operatörler </ins>

- – İzinleri kaldır ( remove chmod permission )
- + İzinleri ekle ( add chmod permission )
- = İzinleri koy ( set chmod permission )

Örneğin;
```Shell
$ chmod +r deneme 
``` 
- deneme dosyasına okuma(r) izni vermiş olduk.

```Shell
$ chmod go+r deneme* 
```
- ( * ) joker parametresi ile deneme ile başlayan tüm dosyaların grup ve diğer(other) userler tarafından okunması iznini verir.





<br/><br/><br/>

### 2)chown

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





  <h2><br/><ins><i>IP ile ilgili komutlar (ifconfig,iptables,ip a, ip link, ip r, ip n, traceroute) </i></ins></h2> 
<br/><h3><br/><ins>IFCONFIG.</h3></ins>
<br/>Argümansız “ifconfig” komutu, tüm aktif arayüz ayrıntılarını görüntüler. ifconfig komutu ayrıca bir sunucunun atanan IP adresini kontrol etmek için de kullanılır.
<br/><p align="center">
  <img src="image/ifcon (1).png" />
</p>
<br/>-a argümanıyla birlikte aşağıdaki ifconfig komutu, sunucudaki tüm etkin veya etkin olmayan ağ arabirimlerinin bilgilerini görüntüler. eth0, lo, sit0 ve tun0 için sonuçları görüntüler.
<br/> <p align="center">
  <img src="image/ifcon (2).png" />
</p>
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




