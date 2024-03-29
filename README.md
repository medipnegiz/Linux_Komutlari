# A'DAN Z'YE LINUX KOMUTLARI [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

<hr>
<p align="center">
	<img alt="Git" src="https://logodownload.org/wp-content/uploads/2022/05/linux-logo.png" height="190" width="555">
</p>
<hr>

# Index 

* [Genel Komutlar](#genel-komutlar)
* [Ortam Degiskenleri](#ortam-degiskenleri)
* [Kullanici Komutlari](#kullanici-komutlari)
* [Paket Yükleme ve Kaldirma Islemleri](#paket-yükleme-ve-kaldirma-islemleri)
* [Filtre Kullanim Komutlari](#filtre-kullanim-komutlari)
* [Dosya Sikistirma ve Acma Komutlari](#dosya-sikistirma-ve-acma-komutlari)
* [Sed, Awk ve Crontab Komutlari](#sed-awk-ve-crontab-komutlari)
* [Sistem ile Ilgili Komutlar](#sistem-ile-ilgili-komutlar)
* [Uzak Bilgisayar Baglanti Komutlari](#uzak-bilgisayar-baglanti-komutlari)
* [Shell Script Komutlari](#shell-script-komutlari)
* [Dersteki Calismalar](#dersteki-calismalar)

<hr>

# GENEL KOMUTLAR

### • Bir önce yazilan komuta isaret ederek yönetici olarak calistirir
```bash
sudo !!
```

### • Root kullanici olarak baglanir ve simge “#” dönüsür
```bash
sudo su
```

### • “Su” Switch-User demektir. Bu komut ile kullanici profilini gecis yapilir
```bash
su ec2-user
```

### • O anki durumda kullanicinin kim oldugunu ögrenmek icin kullanilir
```bash
whoami
```

### • Komutun manuel kitapcigini görüntülemek icin kullanilir
```bash
man ls
```

### • Komutun kullanimi hakkinda bilgi almak icin kullanilir
```bash
info ls
```

### • Komutun islevi hakkinda kisa bilgi almak icin kullanilir
```bash
whatis ls
```

### • Komutlarin tam bir listesini almak icin kullanilir
```bash
apropos ls
```

### • Komutun ve ek parametrelerinin hakkinda bilgi almak icin kullanilir
```bash
ls --help
```

### • Burada “-p” parametresi ile eger “deneme” klasörü yoksa hata vermez, olusturur ve onun da icine “edip” klasörü olusturur
```bash
mkdir –p /home/deneme/edip
```

### • Dosyanin ilk 10 satirini görüntülemek icin kullanilir
```bash
head test.txt
```
```bash
o head -4 test.txt		-->	Dosyanin ilk 4 satirini listelemek icin kullanilir
```

### • Dosyanin son 10 satirini görüntülemek icin kullanilir
```bash
tail test.txt
```
```bash
o tail –3 test.txt		-->	Dosyanin son 3 satirini görüntülemek icin kullanilir
```

### • Dosyanin icini görüntülemek icin kullanilir
```bash
cat test.txt
```
```bash
o cat -b deneme.txt			-->	Dosyanin tüm satirlarini numaralandirarak listeler
o cat -n deneme.txt			-->	Dosyanin sadece dolu satirlarini numaralandirarak listeler
o cat test1.txt test2.txt		-->	Dosyalari birlestirerek görüntülemek icin kullanilir
o cat test1.txt test2.txt > file	-->	Iki dosyayi birlestirir ve “file” isminde dosya olusturarak icine kaydeder
o cat > deneme.txt			-->	“Deneme” isminde dosya olusturur ve komut satirindan icine ekleme yapilir (Ctrl + d ile cikis yapilir)
o cat deneme.txt > test.txt		-->	“Deneme” dosyasi icindekileri “test” adinda bir dosya olusturarak icine kopyalar
```

### • Dosya icerigini tersten baslayarak görüntüler
```bash
tac deneme.txt
```

### • Dosya icerigini bir seferde bir ekran olarak görüntüler
```bash
more deneme.txt
```

### • Gecerli dizindeki klasörlerin ve dosyaların listesini gösterir
```bash
ls
```
```bash
o ls -a			-->	dizindeki gizli dosyalari da göstermek icin kullanilir
o ls -l			-->	dizindeki dosya iceriklerini detaylari ile birlikte gösterir
o ls -h			-->	dizindeki dosyalari insanin okuyabilecegi sekilde listeler
o ls -ls		-->	dizindeki dosyalarin boyutuna göre siralama yapar
o ls -t			-->	dizindeki dosyalari tarihe göre siralar
o ls -r			-->	dizindeki dosyalari tersten siralayarak gösterir
o ls *.*		-->	sadece klasör icindeki dosyalari ve uzantilari gösterir
o ls -l *.doc*		-->	sadece ".doc" uzantili dosyalari listeler
o ls *			--> 	dizindeki dosyalari icindekiler ile birlikte listeler
o ls *[Mm]*		-->	dizindeki isminin icinde "m" gecen bütün dosyalari listeler
o ls ????		-->	Soru isareti sayisi kadar uzunlukta olan isimli dosyalari listeler
```

### • Tüm yazilari indirir ama satir satir inerek gösterir
```bash
ls --help | more
```

### • Terminal kadar yazi gösterir ve satir satir inilir. “q” ile cikilir
```bash
ls --help | less
```

### • Komutun kullanim ve ek bilgilerini listeler
```bash
man pwd
```

### • Komutun kullanim ve ek bilgilerini listeler
```bash
info chmod
```

### • Bir dosyanin icerigini görüntülememize ve dosya icerisinde gezinmemizi saglar
```bash
less deneme.txt
```

### • Bu komut ile klasörler arasi gecis yapariz
```bash
cd /home/ubuntu
```
```bash
o cd /			-->	bu komut ile kök dizine gidilir
o cd, cd ~, cd $home	-->	bu komutlarin hepsi ayni anlamdadir ve ana dizine gider
o cd ..			-->	bir üst dizine gecmek icin kullanilir
o cd -			-->	bir önceki dizine gecmek icin kullanilir
o cd edip\dosya		-->	adi "edip dosya" olan klasöre gecmek icin kullanilir. "\" isareti bosluk(space) anlamindadir
```

### • Dosya yada klasör silmek icin kullanilir (ici dolu klasörleri silmez)
```bash
rm edip.txt
```
```bash
o rm -r			-->	(recursive) bu komut ic ice klasör silmek icin kullanilir (ici dolu olsa da siler)
o rm -f			--> 	(force) silme isleminde zorlamak icin kullanilir
o rmdir			-->	bu komut ile ici bos klasörler silinebilir
o rmdir -p edip/dene	-->	(parents) ic ice klasör silmek icin kullanilir
```

### • Klasör olusturmak icin kullanilir
```bash
mkdir edip
```
```bash
o mkdir dosya{1..5}		-->	ilk ismi "dosya" olan bes adet klasör olusturur (dosya1, dosya2 ...)
o mkdir .gizli			--> 	ismin basindaki "." ile gizli klasör olusturulur
o mkdir -p edip/dene		-->	(parents) ic ice klasör olusturmak icin kullanilir
o mkdir -m 444 edip		-->	(mode) edip adinda sadece yazma izinleri olan bir klasör olusturur
```

### • Sembolik link olusturmak icin kullanilir. Dosyanın birden fazla kopyasının olmasını değil ama birden fazla yerden erişilmesini istiyorsak, dosyayı bu farklı konumlara kopyalamak yerine birer sembolik(-s) link(ln) oluşturulabilir.
```bash
ln -s /opt/test/ec2/ linkdeneme		-->	Klasörün icinden "/opt/test/ec2/" adresine ulasmak icin "linkdeneme" icine gitmek yeterli
```

### • Istenilen uzantiya sahip dosya olusturmak icin kullanilir
```bash
touch edip.txt edip.yml
```

```bash
o touch -t 20072008		-->	Dosyanin olusturulma tarihini istedigimiz bir tarih olarak yapmamizi saglar
```

### • Bir dosyanin adini degistirmek veya bir dosyayi tasimak icin kullanilir
```bash
mv edip.doc ali.doc
```
```bash
o mv edip.doc n/can.doc		-->	Dosyayi bir yere tasimak icin kullanilir. Istersek ismini tasima sirasinda degistirebiliriz
```

### • Bir dosyayi bir yerden baska bir yere kopyalamak icin kullanilir. Istersek kopyalama sirasinda isim degistirebiliriz
```bash
cp edip.doc home/ali.doc
```

### • edip_doc klasörünü sahip olduğu tüm dosyalar ile birlikte başka bir dizine kopyalamak icin kullanilir
```bash
cp -avR edip_doc home/test/edip_doc
```
```bash
o -a 		-->	Dosyaya ait file mode, ownership, timestamps verilerini aktarır
o -v		-->	Islemle ilgili süreci döker
o -R		-->	Klasör yapısını olduğu gibi kopyalar (gizli dosyalar dahil)
o -f		-->	Gerekirse hedef dosyayı kaldırarak kopyalamaya zorlamak icin kullanilir
o -i		-->	Kopyalanacak yerde ayni dosyadan varsa üzerine yazmadan önce sorar
o -l		-->	Dosyalari belirtilen konuma kopyalamak yerine arada bag olusturur (Bir nevi kisayol)
o -n		-->	Kopyalanacak yerde ayni dosyadan varsa üzerine yazma anlamindadir
o -u		-->	Eger kopyalanacak dosya kaynaktaki dosyadan daha yeni ise güncelle anlamindadir
```

### • Dosya varsa onu acar eger yoksa yeni dosya olusturur ve "nano" uygulamasinda acar
```bash
nano edip.txt
```

### • Dosya varsa onu acar eger yoksa yeni dosya olusturur ve "vim" uygulamasinda acar
```bash
vim edip.txt
```

### • Ekrana istedigimiz yaziyi yazdirmak icin kullanilir
```bash
echo "selam naber"
```
```bash
o echo "merhaba" > ali.txt		-->	ali.txt dosyasi varsa icini temizler ve bunu yazar yoksa olusturur yazar
o echo "merhaba" >> ali.txt		-->	ali.txt dosyasi varsa dosyanin en sonuna metni ekler yoksa olusturur yazar
o echo "" can.txt			-->	can.txt dosyasinin icini temizlemek icin kullanilir
o echo -n edip.txt			-->	normalde echo komutu satir sonuna enter ekler. "-n" parametresi ile enter eklenmesi engellenir
```

### • Linuxte yazilan komutlari listelemek icin kullanilir
```bash
history
```
```bash
o history 10			-->	girilen son 10 kodu listeler
o history | grep touch		-->	touch ile ilgili girilen komutlari listeler
o history !15			-->	15. girilen kodu tekrar calistirmak icin kullanilir
```

### • (changemode) Dosya izinlerini degistirmek icin kullanilir. Burada "edip" dosyasina calisma izni verir
```bash
chmod +x edip.sh
```
```bash
- (rwx)(rw-)(r--)
1   2    3    4	

o 1 		-->	dosyanin ne oldugunu belirtir
o 2		-->	user icin calistirma izinleri
o 3 		-->	group icin calistirma izinleri
o 4		--> 	digerleri icin calistirma izinleri
```
```bash
o 0		-->	tüm izinler kapali
o 1		-->	sadece calistirma izni verir
o 2		-->	sadece yazma izni verir
o 3		-->	yazma - calistirma izinlerini verir
o 4		-->	sadece okuma izni verir
o 5		-->	okuma - calistirma izinlerini verir
o 6		-->	okuma - yazma izinlerini verir
o 7 		--> 	okuma - yazma - calistirma izinlerini verir
```
```bash
o chmod -x edip.sh		-->	burada tüm kullanicilarin calistirma iznini alir	
o chmod +rw edip.sh		-->	tüm kullanicilar icin okuma ve yazma izni verir
o chmod 777 edip.sh		-->	burada dosyaya tüm kullanicilar icin bütün izinleri verir 
o chmod ugo=rwx	edip.sh		--> 	u >> user, g >> group, o >> other.  Tüm kullanicilar icin bütün izinleri verir 
o chmod ug=r edip.sh		--> 	dosyaya sadece user ve group icin okuma izni verir 
```

### • Ekrani temizlemek icin kullanilir
```bash
clear
```

### • Bir komutu kisayol olarak tanimlamak icin kullanilir
```bash
alias edip="ls -al"
```

### • Tanimli bir alias kisayolunu silmek icin kullanilir
```bash
unalias edip
```

### • Bulundugumuz dizinde bulunan tüm dosyalari alt klasörler ile birlikte listeler
```bash
find .
```
```bash
o find /home –name test.txt		-->	Home klasörü icerisindeki test.txt dosyasinin tam uzantisini görüntüler
o find /lesson –name den\*		-->	Lesson klasörü icindeki “den” ile baslayan bütün dosyalari listeler (Büyük-kücük harf duyarli)
o find /lesson –name *.png		-->	Lesson klasörü icindeki “.png” ile biten bütün dosyalari listeler
o find /lesson –iname den\*		-->	Lesson klasörü icindeki “den” ile baslayan (büyük-kücük harf fark etmez) bütün dosyalari listeler
```

### • Dosya icerisinde “naber” kelimesi olan tüm satiri görüntüler
```bash
grep ‘naber’ deneme.txt
```
```bash
o Grep –i			--> 	Büyük/kücük harf duyarsiz sekilde görüntüler
o Grep –n			-->	Eslesen dizeleri satir numaralari ile görüntüler
o Grep –v			-->	Eslesmeyen satirlari görüntüler
o Grep –l			-->	Listele anlamindadir
o Grep –R			-->	Alt dosya ve klasörler dahil eder
o Grep –c			-->	Kac satir eslesdiyse sayisini döndürür
o Grep –w			-->	Sadece kelime olarak arar. Tam kelime olarak bulur
o Grep –o “ali”			-->	Dosya icinde sadece eslesen kelimeyi getirir
o Grep “^li”			-->	“li” ile baslayan satirlari listeler
o Grep “dur$”			-->	Sonu “dur “ ile biten satirlari listeler
o grep –iRl ‘naber’		-->	İcerisinde ‘naber’ gecen dosyalarin isimlerini listeler 
o grep ‘is’ *			-->	İcinde ‘is’ olan bütün satirlari dosya farketmeksizin listeler
o grep -A3 'ali' dene.txt	-->	Dosya icinde ‘ali’ ile eslesen satiri ve öncesindeki 3 satir daha listeler
o grep -B3 'veli' dene.txt	-->	Dosya icinde ‘veli’ ile eslesen satiri ve sonrasinda 3 satir daha listeler
o grep -C3 'can' dene.txt	-->	Dosya icinde ‘can’ ile eslesen satiri, öncesinde ve sonrasinda 3 satir daha listeler
o grep lin[u] dene.txt		-->	Dosya icerisinde “lin” isminden sonra sadece “u” olanlari listeler
o grep lin[a-z] dene.txt	-->	Dosya icerisinde “lin” isminden sonra sadece harf olanlari listeler
o grep lin[0-9] dene.txt	-->	Dosya icerisinde “lin” isminden sonra sadece rakam olanlari listeler
```

### • “cd” komutunun help dosyasi icinde “director” gecen satirin önce-sonra 3 satir listeler
```bash
cd --help | grep –C3 ‘director’
```

### • Sonu ‘.txt’ ile biten dosyalari listelemek icin kullanilir
```bash
ls –R | grep .txt
```

### • Locate komutunu yükler. Bu komut ile tüm bilgisayarda konum belirtmeden arama yapilir
```bash
sudo apt-get install mlocate
```

### • Tüm bilgisayarda “deneme.txt” ara ve konumunu yazdirir
```bash
locate deneme.txt
```

### • Locate komutu günceller, böylece yeni eklenen veya silinen dosyalarin komunu yazdirilabilir
```bash
sudo updatedb
```

### • Bu komutun hangi dizinde kayitli oldugunu gösterir
```bash
which pwd
```

### • Bu komut dosyasinin nerede oldugunu gösterir
```bash
whereis pwd
```

### • “wget” komutu ilgili sayfadan belirtilen dosyayi indirir ve bulundugu klasöre kaydeder. Github alinan dosyalarin “raw” halini indirmemiz lazim
```bash
wget https://raw.githubusercontent.com/awsdevopsteam/route-53/master/ken.jpg
```

### • "curl" komutu ile bir web sayfasini Linux komut sistemi üzerinden sorgulayabilir ve görüntüleyebiliriz. "wget" ile aynidir fark olarak "curl" komutu daha fazla dosya ve internet yolu destekler
```bash
curl https://raw.githubusercontent.com/awsdevopsteam/route-53/master/index.html
```

### • Burada sayfadan verileri alir ve /home/ubuntu/ altinda “deneme” olarak kaydeder 
```bash
curl –L https://raw.githubusercontent.com/awsdevopsteam -o /home/ubuntu/deneme
```
```bash
o –L 		--> 	(Location) yer belirtmek icin    
o -o 		--> 	(output) ciktiyi dosya olarak kaydetmek icin kullanilir
o -s		-->	(silent) sessiz mod anlamindadir. Ilerleme yada hata gösterme demektir
o -f		-->	(fail) sunucu hatalarinda sessiyce basarisiz olmasi icin kullanilir
o -S		--<	(show-error) eger basarisiz olursa bir hata mesaji almak icin kullanilir
```

### • Bu komut icine girilen degeri istenilen sayida tekrarlamak icin kullanilir
```bash
echo edip | xargs –I {} echo {} {} 	# büyük i
```

### • Bu komut belirli bir süre aralığında bir komutu tekrar tekrar çalıştırmak için kullanılır. 
```bash
watch -n 1 'ls -al'
```
```bash
o -n 		--> 	tekrarlama aralığını saniye cinsinden belirtir    
o 1 		--> 	kac saniyede araliklarla ekrani yenileyecegini belirtir
o 'ls -al'	-->	calistirilacak komut girilir
```

## Go to [Index](#index)

# ORTAM DEGISKENLERI

## !!! Asagidaki degiskenler büyük harfle ve basinda $ isareti ile girilmelidir

### • Bu değişken, sisteminizin yürütülebilir dosyaları aradığı, iki nokta üst üste (:) ile ayrılmış bir dizin listesi içerir
```bash
$PATH
```

### • Kullanici adi
```bash
$USER
```

### • Kullanicinin ana dizininin varsayilan yolu
```bash
$HOME
```

### • Varsayilan text editörünün yolu
```bash
$EDITOR
```

### • Kullanici bensersiz ID
```bash
$UID
```

### • Varsayilan terminal ayari
```bash
$TERM
```

### • Kullanici tarafindan kullanilan kabuk
```bash
$SHELL
```

### • Gecerli yerel ayarlar
```bash
$LANG
```

## Komut satiri:

### • Bütün ortam degiskenlerini veya belirtilen ortam degiskenlerini listeler
```bash
printenv  -(yada)-  env
```

### • Tüm shell ve environment degiskenleri listeler
```bash
set
```

### • USER degiskenini görüntelemek icin kullanilir
```bash
printenv USER
```

### • USER degiskenini görüntülemek icin kullanilir
```bash
echo $USER
```

### • Büyük harfler ile yeni bir degisken tanimlanabilir. Arada bosluk olmaz!!!
```bash
EDIPP=mahmutedipnegiz
```

### • “cd” komutunu calistirinca bundan sonra gidecegi ana dizini tanimladik
```bash
HOME=/home/ec2-user/edip
```

### • Daha önceden tanimli bir degiskeni silmek icin kullanilir
```bash
unset EDIPP
```

### • Kabuk degiskenlerini diger kabuklara aktarmak icin kullanilir
```bash
export
```

### • Degiskeni cevresel degisken olarak tanimlar. Cercevesini genisletir
```bash
export EDIP=mahmutedipnegiz
```

### • Komutlarin yolunu gösterir. Girilen program ve komutlar önce bu klasörlere bakar ve varsa calistirir
```bash
echo $PATH
```

### • Program calistirmak icin Yola yeni bir klasör eklenir. Artik komut calistirmak icin bu klasöre de bakar. Arada (:) olmak zorunda
```bash
PATH=$PATH:/games/Pubg
```

### • Ana dizine ekleme yapar. Eski dizin sabit kalir yeni dizini sona ekler. Üzerine yazmak icin degisken tekrar tanimlanmalidir
```bash
HOME=$HOME/home/desktop
```

### • Yazmis oldugumuz kod dosyasini bulundugumuz SHELL ortaminda calistirir. Execute olarak izin verilmeli
```bash
source my_script.sh  -(yada)-  . my_script.sh
```

### • Yazmis oldugumuz kod dosyasini farkli bir SHELL de calistirir, bizim bulundugumuz SHELL ortamina etki etmez. Execute olarak izin verilmeli ???
```bash
./my_script.sh
```

### • Bu komut ile ALIAS tanimlamasi yapariz ve SHELL her baglanmada otomatik olarak icindekileri tanimlar ve calistirir
```bash
vim .bashrc
```

### • Bu degiskeni yazdirince $HOME kismini komut olarak algilar ve yazdirir. (“) icine yazilan ifadelerde komut varsa ona komut olarak islem yapar
```bash
MYVAR="my name is $HOME"
```

### • Bu degiskeni yazdirince $PATH kismini metin olarak algilar ve yazdirir. (‘) icine yazilan herseyi metin olarak algilar ve yazdirir
```bash
MYVAR=’my name is $PATH’
```

### • Bu degiskeni yazdirince $PATH kismini metin olarak algilar ve yazdirir. (\) kendinden sonraki komutun özel gücünü alir ve metin olarak algilatir
```bash
MYVAR=’”my name is \$PATH”
```

### • Bu komut ile shell'de tanimlanan degiskenleri yeni dosyaya value olarak yazdirabiliriz
```bash
envsubst < edip.txt > ali.txt
```
```bash
edip.txt	>> Selam $ABC
export ABC="kanka"

* buradan sonra "envsubst" komutu calisirsa ali.txt dosyasina söyle bir deger yazilir

envsubst < edip.txt > ali.txt		-->	var olan bir dosyanin sonuna ekleme yapmak icin ">>" kullanilabilir
ali.txt		>> selam kanka
```

## Go to [Index](#index)

# KULLANICI KOMUTLARI

### • Sisteme kac kullanici bagli oldugunu listeler
```bash
who
```

### • Sisteme kac kullanici bagli ve ne yapiyor onu listeler
```bash
w
```

### • Dosyalarin sahipligini degistirmek icin kullanilir. Kullanici yada group yazilabilir
```bash
chown “ali -yada- group1” “deneme.xt”
chown ali:okul deneme.txt	-->	dosya sahibi(ali) ve group(okul) bir seferde verilebilir
```

### • Belirtilen user tarafından açılmış dosyaları listeler
```bash
lsof -u “edip”
```

### • Kullanici olusturma ile alakali configuration dosyasi acilir ve degisiklikler yapilabilir
```bash
sudo nano /etc/login.defs
```

### • Yeni bir kullanici eklemek icin kullanilir
```bash
sudo Adduser edip
```

### • Kullanici degistirmek icin kullanilir
```bash
su edip
```

### • Kullanici eklemenin bir diger yöntemi
```bash
sudo useradd -m -d /home/edip -c "edip negiz" edip
```
```bash
o –m		-->	ana dizinin olusturulmasini saglar
o –d		-->	ana dizinin adini ayarlamak icin kullanilir
o –c 		-->	bir aciklama eklemek icin kullanilir
```

### • Kullaniciya sifre tanimlamak icin kullanilir
```bash
sudo passwd edip
```

### • Kullanicin sifresi süresi doldurulur ve ilk giriste sifre degistirmesi istenir
```bash
sudo passwd –expire edip
```

### • Kayitli bir kullaniciyi silmek icin kullanilir. (-r) kullanicinin ana dizinini de siler. Normal silmede ana dizin durur sadece kullanici silinir
```bash
sudo userdel –r edip 
```

### • Kullanicin ID bilgisini görüntülemek icin kullanilir
```bash
id edip
```
```bash
o id -g		-->	Mevcut group ID listeler
o id -G		-->	Tüm group ID listeler
o id -u		-->	Mevcut user ID listeler
```

### • Kayitli tüm kullanici bilgilerini listeler
```bash
cat /etc/passwd
```

### • Kullanicinin özelliklerini degistirmek icin kullanilir (user modify).  "-c --> comment" kullaniciya yorum eklemek icin kullanilir
```bash
sudo usermod –c “aws solution archtitect” edip
```

### • “Edip” kullanici adini “Murat” olarak degistirir
```bash
sudo usermod –l murat edip
```

### • Kullanıcı parolaları şifrelenir ve “/etc/shadow” dosyasında saklanır. Bu dosya sadece okunur ve sadece root tarafından erişilebilir
```bash
sudo cat /etc/shadow
```

### • Yeni bir grup olusturmak icin kullanilir
```bash
sudo groupadd linux
```

### • Kullanicilari gruplara eklemek icin kullanilir. (-a) append, kullanicinin eski gruplarindan cikmadan yeni gruba eklemesini saglar "-G" parametresi ile beraber kullanilir
```bash
sudo usermod –a –G linux edip
```

### • Kullanicilar birkac gruba ait olabilir. Bu komut ile gruplar ve kullanicilari listelenir
```bash
sudo cat /etc/group
```

### • Kullanicinin hangi grupta oldugunu listeler
```bash
sudo groups
```

### • Daha önceden var olan “linux” grubunun adini “aws” olarak degistirir
```bash
sudo groupmod –n aws linux
```

### • “Aws” grubuna edip kullanicisini ekler
```bash
sudo gpasswd –a edip aws
```

### • “Aws” grubundan “edip” kullanicisini siler
```bash
sudo gpasswd –d edip aws
```

## Go to [Index](#index)

# PAKET YÜKLEME VE KALDIRMA ISLEMLERI

### • Linuxte yüklü bütün paketleri güncellemek icin kullanilir
```bash
sudo yum update -y
```
```bash
o -y 		--> 	(yes) tekrar onay almadan güncellemesini saglar
o -q		-->	(quiet) ilerleme asamalarini atlar
```

### • Ubuntu makinelerde güncelleme yapmak icin kullanilir. Güncellenecek dosyalari listeler ve bizden onay ister
```bash
sudo apt update 
```

### • Ubuntu makinelerde güncellemesi sorgulanan dosyalarin güncellenmesi icin kullanilir
```bash
sudo apt upgrade 
```

### • Linux makineye git uygulamasi yüklemek icin kullanilir
```bash
sudo yum install git
```

### • Git uygulamasinin versiyonunu ögrenmek icin kullanilir
```bash
git --version
```

### • Linux makineden git uygulamasini kaldirmak icin kullanilir. Uygulamanin baglantili dosyalarini kaldirmaz. Version kisminda git versionu görünür
```bash
sudo yum remove git
```

### • Ubuntu makinede git uygulamasini kaldirmak icin kullanilir
```bash
sudo apt remove git 
```

### • Ubuntu makinede önbellekte tutulan eski ve indirilmiş paketlerin temizlenmesini sağlar
```bash
sudo apt-get clean -y
```

### • Ubuntu makinede indirilmiş paketlerin önbellekteki sürümlerini temizler, ancak yüklü olanları silmez
```bash
sudo apt autoclean -y
```

### • Linuxte git uygulamasini tüm ek baglantilari ve yapilandirma paketleri ile birlikte onay istemeden kaldirir
```bash
sudo yum autoremove git –y
```

### • Ubuntuda “Git” uygulamasini ve yapilandirma paketlerinin hespini kaldirir
```bash
sudo apt purge git
```

### • Linuxte “Git” uygulamasi hakkinda bilgileri listelemek icin kullanilir
```bash
sudo yum info git
```

### • Ubuntuda “Git”  uygulamasi hakkinda bilgileri listeler
```bash
sudo apt info git
```

### • Linux icin yüklü olan ve yüklenebilir bütün paketleri listeler
```bash
sudo yum list | more
```

### • Linuxte “Git” uygulamasinin yüklü dosyalarini ve versiyonunu listeler. Daha güncel bir versiyonu varsa onu da listeler
```bash
sudo yum list git
```

### • Linuxte yüklü olan bütün uygulamalari listelemek icin kullanilir
```bash
sudo yum list installed | more
```

### • Ubuntu da yüklü olan bütün uygulamalari listelemek icin kullanilir
```bash
sudo apt list --installed
```

### • Linuxte “Git” uygulamasinin yüklenebilir tüm sürümlerini listelemek icin kullanilir
```bash
sudo yum --showduplicates list git
```

### • Linuxte “Git” uygulamasinin istenilen versiyonunu yüklemek icin kullanilir
```bash
sudo yum install git-2.14.5-1.amzn2
```

### • Linuxte “Git” uygulamasini güncellemek icin kullanilir. Onay istemez
```bash
sudo yum update git –y
```

### • Debian tabanlı Linux dağıtımlarında paket yönetimi işlemlerini gerçekleştirmek için kullanılan bir komuttur
```bash
o dpkg -i <paket_adi>.deb	-->	Bu komut, belirtilen .deb uzantılı paket dosyasını kurar
o dpkg -r <paket_adi>		-->	Belirtilen paketi kaldırır
o dpkg -l			-->	Sistemde kurulu olan tüm paketleri listeler
o dpkg -p <paket_adi>		-->	Belirtilen paket hakkinda bilgi verir
o dpkg -S <dosya_adi>		-->	Belirtilen dosyanin hangi pakete ait oldugunu bulur
```

## Go to [Index](#index)

# FILTRE KULLANIM KOMUTLARI

### • Listeleme yaparken “-n” ile satir sayilari ile beraber gösterir
```bash
cat –n ali.txt
```

### • “Tee” komutu ile dosya icerisine yazi ekler ve ekranda gösterir ???
```bash
cat edip.txt | tee ahmet.txt
```

### • “cat” ile dosya icerigini listeler ve grep onlari filtreleyerek sadece “guzel” olan yeri listeler
```bash
cat edip.txt | grep guzel
```
```bash
o -w 		-->	sadece “guzel” satirini listeler, sonrasinda ifade varsa listelenmez
o -v  		-->	belirtilen kelime haric hepsini listeler
```

### • Dosya icerisinde “clarusway” arar ve “-A” (after) parametresi ile buldugu satirdan sonraki 3 satiri daha listeler. 
```bash
grep naber -A 3 clarusway edip.txt
```
```bash
o -B		-->	(before) komutu ile önceki satirlari listeler
o -c 		-->	(count) parametresi belirtilen kelime ile baslayan kac tane var sayar
o -wc 		-->	(wordcount) sadece belirtilen kelimeden kac tane var sayar
```

### • listelenen icerigin sadece belirli sütunlarini listelemek icin kullanilir
```bash
ls * -l | cut -d' ' -f3
```
```bash
o cut 		-->	komutu sütunlara göre filtrelemek icin kullanilir 
o -f3 		-->	kacinci sütunu alacagini belirler. Burada 3. sütunu alacak
o d’ ‘  	-->	komutu ne ile ayrilmis oldugunu belirtmek icin kullanilir
```

### • Kullanicilari listeler ve “:” ile ayrilan kelimelerden sadece birinci sütunu listeler
```bash
cat /etc/passwd | cut -d: -f1
```

### • Consoldan metin girerek yazmak icin kullanilir. “<<” isaretinden sonraki kelime girilirse yazma islemini bitir anlamindadir. “SON” gördügü yerde yazma islemi sonra erer
```bash
cat << SON > clarusway.txt 
```

### • “tr” komutu ile icerisinde aktarilan metindeki harfleri degistirmek icin kullanilir. Burada “a” --> “O” ve “e” --> “R” harfine dönüsür. Sadece listelerken dönüsüm olur ana dosya degismez
```bash
cat clarusway.txt | tr ae OR 
```
```bash
o cat edip.txt | tr '\n' ' '		-->	Normalde asagiya yeni satirda listelenecek olan metinleri tek bir satirda arada bir bosluk ile listeler
o cat edip.txt | tr –d aeiou		-->	“-d” sil anlamindadir. Edip dosyasi icindeki belirli harfleri silmek icin kullanilir. Sadece cikti olarak gösterir, ana dosya etkilenmez
o cat edip.txt | tr [a-z] [A-Z]		-->	Dosya icerisindeki bütün harfleri büyük olacak sekilde yazdirir. Dosya etkilenmez, sadece ciktida degisir
o cat edip.txt | tr [:space:] '\n'	-->	Tüm bosluklardan sonra “enter” eklemek icin kullanilir
```

### • Edip dosyasi icindeki satir, kelime ve karakter olarak sayisini gösterir
```bash
wc edip.txt
```
```bash
o wc –l		--> 	sadece satir sayisini verir
o wc –c		--> 	sadece karakter sayisini verir
o wc –w 	--> 	sadece kelime sayisini verir
```

### • Dosya icerigini harf sirasina göre listeler
```bash
sort ali.txt 
```
```bash
 o -r 		-->	tersten yazdirmak icin kullanilir
 o -u 		-->	ifadeleri uniq olacak sekilde listeler 
 o -f 		-->	büyük/kücük harf duyarsiz sekilde siralar 
 o -n 		-->	sonuclari sayisal siraya göre listeler
 ```

### • “Uniq” komutu her kelimeden birer tane gelecek sekilde listeler. !!! "sort" komutu ile birlikte kullanilmasi zorunludur
```bash
sort ahmet.txt | uniq
```

### • İki dosyanin kesisimini almak icin kullanilir. İlk sütun sadece dosya 1 de olanlar. İkinci sütun sadece dosya 2 de olanlar. Ücüncü sütun iki dosyada da olanlari listeler. !!! sort komutu ile birlikte kullanilmasi zorunludur
```bash
comm file1.txt file2.txt 
```

### • Iki dosya arasindaki farklari listelemek icin kullanilir
```bash
diff “test-1.txt” “test-2.txt”
```
```bash
 o -r 		-->	(recursive) bir klasörün icindeki dosyalari karsilastirmak icin kullanilir
 o -u 		-->	(Unified) formatinda farklari görüntülemek icin kullanilir
 ```

### • Tek satirda birden fazla komut verilebilir. “&&” ilk komut basarili ise diger komutu calistirir
```bash
cd /home && ls && cat
```

### • Tek satirda birden fazla komut verilebilir. “;” ilk komut basarili olmasa bile diger komutu calistirir
```bash
cd /home ; ls ; cat
```

### • Tek satirda birden fazla komut verilebilir. “||” ilk komut basarili degilse diger komutu calistirir veya ilk komut basarili olursa sonraki komutu yapmaz. (veya) anlamindadir
```bash
cd /home || ls || cat
```

### • Bir önceki girilen komut hatali ise hata kodunu yazdirir. Hata yok ise “0” döndürür
```bash
echo $?
```

### • Islem yaparken “ && ve ||” birlestirerek kullanilabilir. Dogru olursa “&&” devreye girecek, yanlis olursa “||” devreye girecek
```bash
rm edip.txt && echo 'silindi' || 'hata'
```

### • “#” isareti ile komut sonuna yorum satiri eklenebilir
```bash
echo edip # burasi yorum satiridir
```

### • “\” bu isaret kendinden sonra gelen özel karakterin özel gücünü elinden alir ve islevsiz yapar
```bash
echo ahmet can \# artik yorum olamaz
```

### • “-e” parametresi satir icerisindeki (\n) komutunu veya varsa diger komutlari aktif hale getirir
```bash
echo –e “ahmet \n murat”
```

### • “1 --> standart output” cikti degerini cikti.txt icine kaydet.  “2 --> standart error” ciktida hata varsa hatayi error.txt icine kaydet
```bash
./myscript 1> cikti.txt 2> error.txt
```

## Go to [Index](#index)

# DOSYA SIKISTIRMA VE ACMA KOMUTLARI

## "tar" komutu kullanimi

### • Bu komut dosyalari "tar" ile sikistirmak icin kullanilir
```bash
tar -zcvf my-file.tar.gz klasor1 dosya
```
```bash
o tar			-->	 dosyaları bir arşiv dosyasına eklemek için kullanılır
o -z			-->	 sıkıştırma işlemini gerçekleştirir
o -c			-->	 yeni bir arşiv dosyası oluşturur
o -v			-->	 arşiv işleminin ayrıntılarını ekranda gösterir
o -f			-->	 arşiv dosyasının adının belirlemesini sağlar
o my-file.tar.gz	-->	 oluşturulacak arşiv dosyasının adıdır
o klasor1 dosya		-->	 arşiv dosyasına dahil edilecek klasörler ve dosyaların adlarıdır
```

### • Bu komut sikistirilmis tar.gz dosyalarini acmak icin kullanilir
```bash
tar -zxvf my-file.tar.gz 
```
```bash
o -x			-->	 arşiv dosyasından dosyaların çıkarılması için "extract" modunu belirtir
```

### • Bu komut sikistirilmis tar.gz dosyalari belirli bir klasörün icine cikarmak icin kullanilir
```bash
tar -zxvf my-file.tar.gz -C /edip
```
```bash
o -C			-->	 arşiv dosyasındaki dosyaların çıkarılacağı dizini belirtir
```

## "zip" komutu kullanimi

### • Bu komut dosyalari "zip" ile sikistirmak icin kullanilir
```bash
zip -r dosya.zip dosya_yada_klasor
```
```bash
o zip			-->	 dosya veya klasörleri bir arşiv dosyasına sıkıştırmak için kullanılır
o -r			-->	 belirtilen klasörün içindeki tüm alt klasörleri de arşive eklemeyi sağlar
o dosya.zip		-->	 oluşturulacak arşiv dosyasının adıdır
o dosya_yada_klasor	-->	 sikistirilacak klasör yada dosyalar burada belirtilir
```

### • Bu komut "zip" ile sikistirilmis dosyalari cikarmak icin kullanilir
```bash
unzip dosya.zip
```

### • Bu komut "zip" ile sikistirilmis sifreli dosyalari cikarmak icin kullanilir
```bash
unzip -P sifre dosya.zip
```
```bash
o -P			-->	 sifre girilecegini belirtir
o sifre			-->	 dosyalari cikarmak icin gerekli sifre yazilir
```

## "gzip" komutu kullanimi

### • Bu komut dosyalari "gzip" ile sikistirmak icin kullanilir
```bash
gzip -9 my-file
```
```bash
o gzip			-->	 dosya veya klasörleri bir arşiv dosyasına sıkıştırmak için kullanılır
o -9			-->	 sıkıştırma seviyesini belirler ve en yüksek sıkıştırma seviyesini ifade eder
o -1			-->	 en hızlı sıkıştırma seviyesidir ve en düşük sıkıştırma oranını sağlar
o -6			-->	 varsayilan sikistirma seviyesidir
o my-file		-->	 sikistirilacak olan dosyayi belirtir. Sıkıştırılmış dosya "dosya.gz" adıyla aynı dizine kaydedilir ve orijinal dosya yerinde kalır
```

### • Bu komut "gzip" ile sikistirilmis dosyalari cikarmak icin kullanilir
```bash
gunzip dosya.gz
```

## "rar" komutu kullanimi

### • Bu komut dosyalari "rar" ile sikistirmak icin kullanilir
```bash
rar a -ap my-file.rar dosya_yada_klasor
```
```bash
o rar			-->	 dosya veya klasörleri bir arşiv dosyasına sıkıştırmak için kullanılır
o a			-->	 "add" kelimesinin kısaltmasıdır ve RAR arşivi oluşturma veya mevcut bir arşive dosya eklemek için kullanılir
o -a			-->	 sıkıştırma metodu olarak otomatik modun kullanılmasını sağlar
o -p			-->	 sıkıştırma parolasını "my-file.rar" dosyasına ekleme özelliğini etkinleştirir
o my-file.rar		-->	 oluşturulacak arşiv dosyasının adıdır
o dosya_yada_klasor	-->	 sikistirilacak klasör yada dosyalar burada belirtilir
```

### • Bu komut "rar" ile sikistirilmis dosyalari acmak icin kullanilir
```bash
unrar e -p Sifre my-file.rar
```
```bash
o e			-->	 arşiv dosyasındaki tüm dosyaların çıkarılmasını sağlar.
o -p			-->	 sifre girilecegini belirtir
o Sifre			-->	 dosyalari cikarmak icin gerekli sifre yazilir
```

## Go to [Index](#index)

# SED, AWK VE CRONTAB KOMUTLARI

### • Bu komut ali.txt dosyasi icindeki ilk “linux” ifadesini bulur ve onu “ubuntu” olarak degistirir. Büyük-kücük harf duyarli degil. 
```bash
sed –i ‘s/linux/ubuntu/’ ali.txt
```
```bash
o -i		-->	 degisikligi dosyaya uygular ve kaydeder
```

### • Ali.txt dosyasindaki bütün “linux” ifadelerini “ubuntu” olarak degistirir. 
```bash
sed ‘s/linux/ubuntu/ig’ ali.txt
```
```bash
o i		-->	 büyük-kücük duyarsiz 
o g		-->	 bütün ifadeleri degistir
```

### • Ali.txt dosyasindaki buldugu 2. “linux” ifadesini “ubuntu” yapar
```bash
sed ‘s/linux/ubuntu/2’ ali.txt
```

### • Sadece 3. satirdaki bütün “linux” ifadelerini “ubuntu” olarak degistirir
```bash
sed ‘3 s/linux/ubuntu/g’ ali.txt
```

### • Bu komut da “cat” komutu gibi dosya listelemek icin kullanilir
```bash
awk ‘{print}’ ahmet.txt
```
```bash
o awk ‘{print $3}’ ahmet.txt			-->	Ahmet dosyasinin sadece 3. Satirini listeler
o awk ‘/aksam/ {print $0}’ ahmet.txt		-->	Ahmet dosyasinin icindeki "aksam" ile baslayan bütün satirlari listeler
o awk '{ if($7 == "can") print $0}' ahmet.txt	-->	Ahmet dosyasinin 7. Sütununda “can” ifadesi varsa o satiri komple listeler
```

### • Zaman olarak planli yapmak istedigimiz islemler icin crontab dosyasini düzenlemek icin kullanilan bir komuttur
```bash
crontab –e
```

### • Crontab dosyasinda kayitli komutlari listelemek icin kullanilir
```bash
crontab –ls
```

### • Yildizlar zaman bakimindan ayarlamak icin kullanilir. Hicbir deger girilmezse dakika basi islem yapar
```bash
* * * * *  date >> /home/ec2-user/veriler.log 
```
```bash
* * * * *
1 2 3 4 5
o 1  		-->  	bu kisim dakika icin kullanilir
o 2  		-->  	bu kisim saat girmek icin kullanilir
o 3  		-->  	bu kisim ayin kacinda onu belirtmek icin kullanilir
o 4  		-->  	bu kisim ay girmek icin kullanilir
o 5  		-->  	bu kisim ayin gününü belirtmek icin kullanilir
```

### • Bu komut saat 12:25 te git uygulamasini yükler
```bash
crontab –e
25 12 * * * sudo yum install git –y 
```

## Go to [Index](#index)

# SISTEM ILE ILGILI KOMUTLAR

### • Bir bölümü bicimlendirmek icin kullanilir
```bash
mkfs
```

### • Bu komut bir işlem için CPU öncelik seviyesi ayarlamak için kullanılır
```bash
nice -n 19 git-backup
```
```bash
o -n		-->	(--classdata) işlem önceliğini belirtmek icin kullanilir 
o 19 		-->	islem önceligi seviyesi girilir. Islem önceliği seviyeleri -20 ile 19 arasındadır
			-20 en yüksek önceligi, 19 en düşük önceliği temsil eder. Default 0
o git-backup	-->	islemi önceligi belirlenen komut girilir		
```

### • Bu komut bir işlem için disk I/O önceliğini ayarlamak için kullanılır
```bash
ionice -c2 -n7 git-backup
```
```bash
o -c2		-->	(--class) işlem sınıfını belirtir. Bu öncelik seviyeleri üç sınıfa ayrılır
			1:real-time -> yüksek, 2:best-effort -> orta ve 3:idle -> düsük
o -n7 		-->	islem önceligi seviyesi girilir. Islem önceligi seviyeleri 0 ile 7 arasındadir
			0 en yüksek önceligi, 7 en düsük önceligi temsil eder.
```

### • Bilgisayarda ne kadar RAM kullanildigini gösterir
```bash
o top		-->	Liste seklinde gösterim yapar
o htop 		-->	daha görsel bir arayüze sahiptir ve bellek tüketimiyle ilgili daha fazla ayrıntı sağlar
```

### • Diskin kullanim durumunu listelemek icin kullanilir
```bash
free
```
```bash
o free -b 		-->	Disk kullanimini Byte olarak listeler
o free -k		-->	Disk kullanimini Kilobyte olarak listeler
o free -m		-->	Disk kullanimini Megabyte olarak listeler
o free -g		-->	Disk kullanimini Gigabyte olarak listeler
```

### • Islemci hakkinda bilgi almak icin kullanilir
```bash
cat /proc/cpuinfo
```

### • Bulundugumuz agin route ve table bilgilerini listeler
```bash
route
```

### • ICMP protokolünü kullanarak belirtilen hedefe gönderilen paketin kac atlamada hedefe ulastıgını gösterir
```bash
traceroute google.com
```

### • Karsidaki bir sunucuya ping atmak icin kullanilir
```bash
ping 192.168.2.1
```

### • Bu iki komut belirtilen adresin NS ve SOA kayitlarini siralamak icin kullanilir
```bash
nslookup github.com
```
```bash
dig google.com
```

### • Bu komut ping ve traceroute komutlarini kombine eder. Gercek zamanlı olarak gönderilen pakette gerceklesen veri kayiplarini ve gecikme sürelerini detayli olarak listeler
```bash
mtr google.com 
```
```bash
mtr -n --report google.com		-->	Hedefe sadece 10 paket atarak sonucu rapor halinde listeler. "-n" parametresi DNS çözümlemesini engeller
```

### • Internet baglantimizi göstermek icin kullanilir
```bash
netstat –n
```

### • Makinada bulunan tüm network interface’lerin durumunu sorgular ve interfacelerden gönderilen paketleri yakalar
```bash
o tcpdump --list-interfaces		-->	Tüm arayüzleri listeler
o tcpdump 				-->	Tüm arayüzlerin paket iletimini dinler
o tcpdump -i eth0			-->	Belirtilen arayüzün paket iletimini dinler
o tcpdump -i eth0 -c 10 		-->	Paket dinleme islemini 10 ile sinirlar
```

### • Anakartin üzerin takilan soketleri ve üreticilerini gösterir
```bash
lspci
```

### • Detayli bir sekilde bilgisayarin donanim özelliklerini gösterir
```bash
lshw
```

### • Calisan bir programi terminal üzerinden durdurmak icin numarasi girilir ve durdurulur
```bash
kill 43...
```

### • Bilgisayarda calisan programlar ve kullandiklari RAM orani listelenir
```bash
htop
```

### • CPU ve memory kullanımını gösterir, htop komutundan farklı olarak çıktıyı rapor halinde sunar
```bash
ps aux
```
```bash
o a		-->	 Tüm kullanıcıların islemlerini gösterir
o u		-->	 Islemin sahibini gösterir
o x 		-->	 Terminale baglı olmayan islemleri gösterir
```

## Go to [Index](#index)

# UZAK BILGISAYAR BAGLANTI KOMUTLARI

### • Uzaktaki bir bilgisayara baglanmak icin kullanilir
```bash
ssh -i ./edip.pem ec2-user@<IP-ADRESI>
```

### • Uzaktaki bir bilgisayara veri kopyalamak icin kullanilir
```bash
scp -i ./edip.pem ./edip.txt ec2-user@<IP-ADRESI>:/home/ubuntu/
```
```bash
o -p		-->	 Hedef adreste port bilgisi girmek için kullanılır
o -q		-->	 Yüzdelik dilimler ile arayüzde gösterilen transfer aşamasını kapatır/disable eder
o -r 		-->	 Klasör kopyalamak için kullanılır
o -v 		-->	 Hata ayıklama iletilerini görüntüler
o -c 		-->	 Sıkıştırmayı etkinleştirir
o -i 		-->	 Ortak anahtar kimlik doğrulaması veya özel anahtar (ssh key) dosyasını kullanmak için kullanılır
o -l 		-->	 Band genisligini limitlemek için kullanılabilir
```

## Go to [Index](#index)

# SHELL SCRIPT KOMUTLARI

### • Matematik islemlerinde sembollerin yerine kullanilan komutlar
```bash
o –lt		--> 	<
o –gt		-->	>
o –le		-->	<=
o –ge		-->	>=
o -eq		-->	==
o –ne		-->	!=
o –z		-->	bos string
o –n		-->	bos olmayan string
```

### • Bir Linux dosyasıyla ilişkili çeşitli özellikleri test etmek için kullanılabilecek operatörler
```bash
o –d		-->	directory
o –e		-->	exist
o –f	 	-->	Ordinary file 
o –r		-->	readable 
o –s	 	-->	size is > 0 bytes
o –w		-->	writable
o –x		-->	executable
```

### • “if .. then” komut satiri kullanimi bu sekildedir. Komutun calismasi icin dosyanin “chmod +x” ile calistirilabilir hale getirilmesi gerekir
```bash
#!/bin/bash
if ["foo" = "foo"]; then
	echo “bunlar birbirine esit”
fi
```

### • “if .. then .. else” komut satiri kullanimi bu sekildedir
```bash
if [ $num -eq 5  ] 	 #  (($num + 5)) “aritmetik(toplama vb.) islem varsa kullanilir”
then
	echo “sayi 5 e esittir”
elif (( $num < 5 )) 	– yada –	   [$num –lt 5]
then
    echo "sayi 5 ten az"
else
    echo "sayi 5 ten fazla"
fi
```

### • Ic ice “if..then..else” komut kullanimi bu sekildedir
```bash
#!/bin/bash
read -p "Bir sayi girin: " SAYI
if [ $SAYI -gt 10 ]
then
        echo "Sayi 10dan büyük"
        if (( $SAYI % 2 == 1 ))	# Matemaiksel islemlerde () seklinde kullanilir
        then
                echo "Sayi tek"
        else
                echo "Sayi cift"
        fi
else
        echo "Sayi 10 dan kücük"
fi
```

### • “If..then..else” dosyasinda “degil, or, and” kullanimi asagidaki ifadeler ile olur
```bash
o !	 	-->	degil
o &&		-->	and
o ||		-->	or
```
```bash
#!/bin/bash
read -p "Adinizi girin: " NAME
read –s –p "Sifreinizi girin: " SIFRE		# “-s” sifre girerken görünmemesini saglar
if [ $NAME = $(whoami) ] && [ $SIFRE = 12345 ]
then
        echo -e "\nWelcome $(whoami)"		# “-e” icerideki \n gibi islemleri aktif eder
else
        echo -e "\nYanlis giris"
fi
```

### • “For” döngü kullanimi bu sekildedir. Bir dize içindeki bir dizi 'kelime' ve ‘sayilar’ üzerinde yineleme yapmanızı sağlar
```bash
#!/bin/bash
for i in $( ls ); do		# $(ls) yada `ls`  --> ikisi de aynikomut.   
   echo item: $i		# `pwd`/*  --> klasördeki tüm dosyalarin konumlarini gösterir
done
```

------------------------------------------------------------------

```bash
A =  (“S3” “EC2” “Lambda” “Glacier” “CloudFront” “Kinesis”)
for x in S3 EC2 Lambda Glacier CloudFront Kinesis	
do
  echo "Amazon Service: $x"			# $x[@] --> tüm listeyi gezer. @ tüm liste anlamindadir
done
```

------------------------------------------------------------------ 

```bash
#!/bin/bashs
echo "Numbers:"
for number in {1..10}	      # 1 den 10 a kadar sayi üretir	
do
   echo $number
done
```

### • “While” kosul dogru ise islem yapar, yanlis olursa islemi sonlandirir. “done” komutu ile döndügen cikilir
```bash
#!/bin/bash
COUNTER=0
 while [  $COUNTER -lt 10 ]; do
     echo The counter is $COUNTER
     let COUNTER=++COUNTER		# ((COUNTER++) ifadesi de kullanilabilir
done
```

### • “Until” kosul yanlis ise islem yapar, dogru oldugu zaman döngüden cikar. “done” komutu ile döngüden cikilir
```bash
#!/bin/bash
number=1
until [[ $number -ge 10 ]];do
        echo $number
        ((number++))
done
echo "Now, number is $number"
```

### • “Select..case..esac” kullanimi asagidadir. Kendisi otomatik numaralandirir ve  secimi uygular. (If ifadesinin farkli bir versiyonudur)
```bash
#!/bin/bash
read -p "ilk numarayi girin: " ilk_num
read -p "ikinci numarayi girin: " iki_num
PS3="Islemi secin: "    	# PS3 degiskeni “select..case” döngüsü ile kullanilir 
select islem in toplama cikarma carpma bolme cikis
do
    case $islem in
        toplama)
            echo "sonuc= $(( $ilk_num + $iki_num ))"
        ;;
        cikarma)
            echo "sonuc= $(( $ilk_num - $iki_num ))"
        ;;
        carpma)
            echo "sonuc= $(( $ilk_num * $iki_num ))"
        ;;
        bolme)
            echo "sonuc= $(( $ilk_num / $iki_num ))"
        ;;
        cikis)
            echo "cikiliyor..."
            sleep 1
            break
        ;;
        *)		# baska bir ifade girilirse devreye girer.
            echo "Yanlis secim..."
        ;;
    esac
done
```

### • Fonksiyon tanimlamasi bu sekildedir. Calistirmak icin sadece fonksiyonu cagirmak yeterlidir
```bash
#!/bin/bash
function cikis () {
   exit
}
function hello () {
   echo Hello People!
}
Hello
cikis
```

---------------------------------------------

```bash
#!/bin/bash
welcome (){		# function yazmadan direk fonksiyon ismi verilebilir
    echo "Welcome to Linux Lesson"
}
welcome
```

## Go to [Index](#index)

# DERSTEKI CALISMALAR

### • Önce klasör var mi diye kontrol ediyoruz, eger klasör yoksa o isimde klasör olusturuyor
```bash
#!/bin/bash
if [ -z "$(ls | grep edip)" ]; then	# “-z” bos ise anlamindadir.
        mkdir edip
        echo "Edip klasörü olusturuldu"
else
        echo "Böyle bir klasör var"
fi
```

### • Istenilen program var mi diye version üzerinden kontrol ediyor yoksa indiriyor
```bash
#!/bin/bash
git --version
if [[ $? == 0 ]]
then
	echo " Already exits"
else
        yum update -y
	yum install git
fi
```

### • Girilen sayinin büyük olup olmamasina göre islem yapan fonksiyon
```bash
#!/bin/bash
read -p "Sayi girin..: " num
sayi () {
    if [[ $num -gt 9 ]]
    then
        return 5
    else
        return 0
    fi
}
sayi
echo $?
```

### • 100 e kadar olan tam sayilarin toplamini veren program
```bash
#!/bin/bash
sonuc=0
for i in {1..100}
do
    ((sonuc=sonuc+i))
done
echo $sonuc
```

## Go to [Index](#index)
