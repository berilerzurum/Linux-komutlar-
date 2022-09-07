# Linux komutları
<h2><br/>CAT:</h2>
<br/>Cat komutu dosya içeriğini, terminal ekranından okumamızı sağlayan komuttur.
<br/>Cat komutunun, bu işlemin yanı sıra başka yararları da mevcuttur. Bunlara da değineceğim.
<br/>Örneğin; Linux terminalinde deneme.txt dosyası oluşturalım.
<br/>“cat > deneme.txt” komutu ortamda deneme.txt dosyası yok ise önce dosyayı oluşturur ardından içine yazı yazabilmemizi sağlar.
<br/>Bu işlemden sonra cat komutu ile dosyayı okuyalım cat deneme.txt 
<br/>Lakin dosyayı yeni yarattığımız için içi boş olacak ve herhangi bir yazı ile karşılaşmayacağız. 
<br/>Bu noktada yine “cat” komutu ile dosyamıza yazımızı ekleyebiliriz. Bunu da;
<br/>cat > deneme.txt komutu ile yapabiliriz.
<br/>Yazımızı ekledikten sonda Ctrl+D ile dosyadan çıkabiliriz.
<br/>Eğer ortamda önceden oluşturulmuş deneme.txt dosyası bulunuyorsa cat > deneme.txt komutu, önceki deneme.txt dosyasının içindeki verileri siler ve yazacağımız yeni verileri deneme.txt dosyasına yazmamızı sağlar.
<br/>Eğer dosyanın üzerine yazmak istiyorsak cat >>deneme.txt komutunu kullanmamız gerekir. Bu şekilde eski veriler de yeni veriler de tutulmuş olur.
<br/>Konsolda bir dosyanın içeriğini görüntülemek yerine sonucu > kullanarak başka bir dosyaya yönlendirebilirsiniz. Komut satırı böyle olacaktır:
<br/>cat kaynak.txt > hedef.txt
<br/>Eğer hedef dosya bulunmuyorsa o zaman komut bu dosyayı yaratacak veya var olan dosyanın üzerine yazacaktır.
<br/>Mevcut konumdaki bütün metin dosyalarının içeriğini görüntülemek için aşağıdaki komutu terminal’de kullanın:
<br/>cat *.txt

<br/>Cat komutu satır sonlarını, $ karakterini her satırın sonunda görüntüleyerek işaretleyebilir. Bu özelliği kullanmak için cat komutuyla birlikte -E seçeneğini kullanın:
<br/>cat -E dosyaadi.txt

<br/>Cat komutuyla bir dosyanın içeriklerini her satırın başında rakamlarla görüntüleyebilirsiniz. Bu özelliği kullanmak için cat komutuyla birlikte -n seçeneğini kullanın:
<br/>cat -n dosyaadi.txt

<br/>Cat komutuyla ilgili daha fazla bilgi için cat’in el kılavuzu sayfasına man cat komutu ile ulaşabilirsiniz.

<br/>More
<br/>more komutu cat ile aynı ile vazifelidir. Ancak more komutunun bir avantajı tek sayfada gösterilemeyecek olan dosyalar okunurken boşluk tuşu ile kaydırma olanağı sağlamasıdır.
<br/>more file_path
<br/>Less
<br/>Less komutu da more komutu gibi dosyayı görüntülemeye yarar fakat birkaç farkla.
<br/>•	Less içerik içinde ileri - geri yönlü hareket edebilirken, more ile sadece ileri yönlü hareket edilebilir
<br/>•	Less tüm dosya içeriğini belleğe almadığı için büyük dosyaları okumak için daha uygundur
<br/>•	Less more'a göre daha gelişmiştir (metin içinde arama, zip dosyasını okuma vb..) ve more yerine artık less tercih edilmektedir
<br/>Head
<br/>Bir metin dosyasının ilk birkaç satırını görüntülemek için kullanılır. Örnek:
<br/>head dosya.txt

<br/>Tail
<br/>Bir metin dosyasının son birkaç satırını görüntülemek için kullanılır. Örnek:
<br/>tail dosya.txt

<br/>head ve tail komutları için varsayılan değer 10'dur. Ancak istenirse bu değer değiştirilebilir. Örnekler:
<br/>head -n 5 dosya.txt
<br/>tail -n 25 dosya.txt

<br/>Birinci örnekte dosyanın başından itibaren 5 satır görüntülenir. İkincisinde ise aynı dosyanın sonundan itibaren 25 satır görüntülenir. Eğer dosyanın satır sayısı belirtilen sayıdan az ise (veya sayı belirtilmediğinde 10'dan az ise) dosyada olan kadar satır görüntülenir.
