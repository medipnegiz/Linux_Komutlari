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
* [Paket Yükleme Islemleri](#paket-yükleme-islemleri)
* [Filtre Kullanim Komutlari](#filtre-kullanim-komutlari)
* [Sed, Awk ve Crontab Komutlari](#sed-awk-ve-crontab-komutlari)
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

### • Dosyanin ilk 4 satirini listelemek icin kullanilir
```bash
head -4 test.txt
```

### • Dosyanin son 10 satirini görüntülemek icin kullanilir
```bash
tail test.txt
```

### • Dosyanin son 3 satirini görüntülemek icin kullanilir
```bash
tail –3 test.txt
```

### • Dosyanin icini görüntülemek icin kullanilir
```bash
cat test.txt
```

### • Dosyalari birlestirerek görüntülemek icin kullanilir
```bash
cat test1.txt test2.txt
```

### • Iki dosyayi birlestirir ve “file” isminde dosya olusturarak icine kaydeder
```bash
cat test1.txt test2.txt > file
```

### • “Deneme” isminde dosya olusturur ve komut satirindan icine ekleme yapilir (Ctrl + d ile cikis yapilir)
```bash
cat > deneme.txt
```

### • “Deneme” dosyasi icindekileri “test” adinda bir dosya olusturarak icine kopyalar
```bash
cat deneme.txt > test.txt
```

### • Dosya icerigini tersten baslayarak görüntüler
```bash
tac deneme.txt
```

### • Dosya icerigini bir seferde bir ekran olarak görüntüler
```bash
more deneme.txt
```

### • Tüm yazilari indirir ama satir satir inerek gösterir
```bash
ls --help | more
```

### • Bir dosyanin icerigini görüntülememize ve dosya icerisinde gezinmemizi saglar
```bash
less deneme.txt
```

### • Terminal kadar yazi gösterir ve satir satir inilir. “q” ile cikilir
```bash
ls --help | less
```

### • Bulundugumuz dizinde bulunan tüm dosyalari alt klasörler ile birlikte listeler
```bash
find .
```

### • Home klasörü icerisindeki test.txt dosyasinin tam uzantisini görüntüler
```bash
find /home –name test.txt
```

### • Lesson klasörü icindeki “den” ile baslayan bütün dosyalari listeler (Büyük-kücük harf duyarli)
```bash
find /lesson –name den\*
```

### • Lesson klasörü icindeki “.png” ile biten bütün dosyalari listeler
```bash
find /lesson –name *.png
```

### • Lesson klasörü icindeki “den” ile baslayan (büyük-kücük harf fark etmez) bütün dosyalari listeler
```bash
find /lesson –iname den\*
```

### • Dosya icerisinde “naber” kelimesi olan tüm satiri görüntüler
```bash
grep ‘naber’ deneme.txt
```
```bash
o	Grep –i			--> 	Büyük/kücük harf duyarsiz sekilde görüntüler
o	Grep –n			-->	Eslesen dizeleri satir numaralari ile görüntüler
o	Grep –v			-->	Eslesmeyen satirlari görüntüler
o	Grep –c			-->	Kac satir eslesdiyse sayisini döndürür
o	Grep –o “ali”		-->	Dosya icinde sadece eslesen kelimeyi getirir
o	Grep –w			-->	Sadece kelime olarak arar. Tam kelime olarak bulur
o	Grep “^li”		-->	“li” ile baslayan satirlari listeler
o	Grep “dur$”		-->	sonu “dur “ ile biten satirlari listeler
```

### • İcerisinde ‘naber’ gecen dosyalarin isimlerini listeler (-l : listele,   -R : alt dosya ve klasörler dahil)
```bash
grep –iRl ‘naber’ 
```

### • İcinde ‘is’ olan bütün satirlari listeler. Dosya farketmeksizin
```bash
grep ‘is’ * 
```

### • Dosya icinde ‘ali’ ile eslesen satiri ve öncesindeki 3 satir daha listeler
```bash
grep -A3 'ali' clarusway.txt
```

### • Dosya icinde ‘veli’ ile eslesen satiri ve sonrasinda 3 satir daha listeler
```bash
grep -B3 'veli' clarusway.txt
```

### • Dosya icinde ‘can’ ile eslesen satiri, öncesinde ve sonrasinda 3 satir daha listeler
```bash
grep -C3 'can' clarusway.txt
```

### • Dosya icerisinde “lin” isminden sonra sadece “u” olanlari listeler
```bash
grep lin[u] clarusway.txt
```

### • Dosya icerisinde “lin” isminden sonra sadece harf olanlari listeler
```bash
grep lin[a-z] clarusway.txt
```

### • Dosya icerisinde “lin” isminden sonra sadece rakam olanlari listeler
```bash
grep lin[0-9] clarusway.txt
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

### • Daha önce kullanilan “find” komutlarini listeler
```bash
history | grep ‘find’
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
!!! –L --> location belirtmek icin    -o --> ciktiyi dosya olarak kaydetmek icin kullanilir.
```bash
curl –L https://raw.githubusercontent.com/awsdevopsteam -o /home/ubuntu/deneme
```

### • Bu komut icine girilen degeri istenilen sayida tekrarlamak icin kullanilir
```bash
echo edip | xargs –I {} echo {} {} 	# büyük i
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

### • Kullanicin id bilgisini görüntülemek icin kullanilir
```bash
id edip
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

# PAKET YÜKLEME ISLEMLERI

### • Linuxte yüklü bütün paketleri güncellemek icin kullanilir. "-y --> yes" tekrar onay almadan güncellemesini saglar
```bash
sudo yum update -y
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
git -- version
```

### • Linux makineden git uygulamasini kaldirmak icin kullanilir. Uygulamanin baglantili dosyalarini kaldirmaz. Version kisminda git versionu görünür
```bash
sudo yum remove git
```

### • Ubuntu makinede git uygulamasini kaldirmak icin kullanilir
```bash
sudo apt remove git 
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

## Go to [Index](#index)

# FILTRE KULLANIM KOMUTLARI

### • Listeleme yaparken “-n” ile satir sayilari ile beraber gösterir
```bash
cat –n ali.txt
```

### • Dosya icerigini tersten baslayarak listeler
```bash
tac edip.txt
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

### • Normalde asagiya yeni satirda listelenecek olan metinleri tek bir satirda arada bir bosluk ile listeler
```bash
cat count.txt | tr '\n' ' '
```

### • “tr” komutu ile birlikte kullanilan “-d” sil anlamindadir. Edip dosyasi icindeki belirli harfleri silmek icin kullanilir. Sadece cikti olarak gösterir, ana dosya etkilenmez
```bash
cat edip.txt | tr –d aeiou
```

### • Dosya icerisindeki bütün harfleri büyük olacak sekilde yazdirir. Dosya etkilenmez, sadece ciktida degisir
```bash
cat clarusway.txt | tr [a-z] [A-Z]
```

### • Tüm bosluklardan sonra “enter” eklemek icin kullanilir
```bash
cat edip.txt | tr [:space:] '\n'
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

# SED, AWK VE CRONTAB KOMUTLARI

### • Bu komut ali.txt dosyasi icindeki ilk “linux” ifadesini bulur ve onu “ubuntu” olarak degistirir. Büyük-kücük harf duyarli degil. (-i) degisikligi dosyaya uygular ve kaydeder
```bash
sed –i ‘s/linux/ubuntu/’ ali.txt
```

### • Ali.txt dosyasindaki bütün “linux” ifadelerini “ubuntu” olarak degistirir. (i) büyük-kücük duyarsiz, (g) bütün ifadeleri degistir
```bash
sed ‘s/linux/ubuntu/ig’ ali.txt
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

### • Ahmet dosyasinin sadece 3. Satirini listeler
```bash
awk ‘{print $3}’ ahmet.txt
```

### • Ahmet dosyasinin icindeki "aksam" ile baslayan bütün satirlari listeler
```bash
awk ‘/aksam/ {print $0}’ ahmet.txt
```

### • Ahmet dosyasinin 7. Sütununda “can” ifadesi varsa o satiri komple listeler
```bash
awk '{ if($7 == "can") print $0}' ahmet.txt
```

### • Zaman olarak planli yapmak istedigimiz islemler icin crontab dosyasini düzenlemek icin kullanilan bir komuttur
```bash
crontab –e
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

### • Crontab dosyasinda kayitli komutlari listelemek icin kullanilir
```bash
crontab –ls
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
