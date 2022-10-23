# LINUX – PLUS KOMUTLARI


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
Su ec2-user
```

### • Komutun manuel kitapcigini görüntülemek icin kullanilir
```bash
Man ls
```

### • Komutun kullanimi hakkinda bilgi almak icin kullanilir
```bash
Info ls
```

### • Komutun islevi hakkinda kisa bilgi almak icin kullanilir
```bash
Whatis ls
```

### • Komutlarin tam bir listesini almak icin kullanilir
```bash
Apropos ls
```

### • Komutun ve ek parametrelerinin hakkinda bilgi almak icin kullanilir
```bash
Ls --help
```

### • Burada “-p” parametresi ile eger “deneme” klasörü yoksa hata vermez, olusturur ve onun da icine “edip” klasörü olusturur
```bash
Mkdir –p /home/deneme/edip
```

### • Dosyanin ilk 10 satirini görüntülemek icin kullanilir
```bash
Head test.txt
```

### • Dosyanin ilk 4 satirini listelemek icin kullanilir
```bash
Head -4 test.txt
```

### • Dosyanin son 10 satirini görüntülemek icin kullanilir
```bash
Tail test.txt
```

### • Dosyanin son 3 satirini görüntülemek icin kullanilir
```bash
Tail –3 test.txt
```

### • Dosyanin icini görüntülemek icin kullanilir
```bash
Cat test.txt
```

### • Dosyalari birlestirerek görüntülemek icin kullanilir
```bash
Cat test1.txt test2.txt
```

### • Iki dosyayi birlestirir ve “file” isminde dosya olusturarak icine kaydeder
```bash
Cat test1.txt test2.txt > file
```

### • “Deneme” isminde dosya olusturur ve komut satirindan icine ekleme yapilir (Ctrl + d ile cikis yapilir)
```bash
Cat > deneme.txt
```

### • “Deneme” dosyasi icindekileri “test” adinda bir dosya olusturarak icine kopyalar
```bash
Cat deneme.txt > test.txt
```

### • Dosya icerigini tersten baslayarak görüntüler
```bash
Tac deneme.txt
```

### • Dosya icerigini bir seferde bir ekran olarak görüntüler
```bash
More deneme.txt
```

### • Tüm yazilari indirir ama satir satir inerek gösterir
```bash
Ls --help | more
```

### • Bir dosyanin icerigini görüntülememize ve dosya icerisinde gezinmemizi saglar
```bash
Less deneme.txt
```

### • Terminal kadar yazi gösterir ve satir satir inilir. “q” ile cikilir
```bash
Ls --help | less
```

### • Bulundugumuz dizinde bulunan tüm dosyalari alt klasörler ile birlikte listeler
```bash
Find .
```

### • Home klasörü icerisindeki test.txt dosyasinin tam uzantisini görüntüler
```bash
Find /home –name test.txt
```

### • Lesson klasörü icindeki “den” ile baslayan bütün dosyalari listeler (Büyük-kücük harf duyarli)
```bash
Find /lesson –name den\*
```

### • Lesson klasörü icindeki “.png” ile biten bütün dosyalari listeler
```bash
Find /lesson –name *.png
```

### • Lesson klasörü icindeki “den” ile baslayan (büyük-kücük harf fark etmez) bütün dosyalari listeler
```bash
Find /lesson –iname den\*
```

### • Dosya icerisinde “naber” kelimesi olan tüm satiri görüntüler
```bash
Grep ‘naber’ deneme.txt
```
```bash
o	Grep –i			 	Büyük/kücük harf duyarsiz sekilde görüntüler
o	Grep –n				Eslesen dizeleri satir numaralari ile görüntüler
o	Grep –v				Eslesmeyen satirlari görüntüler
o	Grep –c				Kac satir eslesdiyse sayisini döndürür
o	Grep –o “ali”			Dosya icinde sadece eslesen kelimeyi getirir
o	Grep –w				Sadece kelime olarak arar. Tam kelime olarak bulur
o	Grep “^li”			“li” ile baslayan satirlari listeler
o	Grep “dur$”			sonu “dur “ ile biten satirlari listeler
```

### • İcerisinde ‘naber’ gecen dosyalarin isimlerini listeler (-l : listele,   -R : alt dosya ve klasörler dahil)
```bash
Grep –iRl ‘naber’ 
```

### • İcinde ‘is’ olan bütün satirlari listeler. Dosya farketmeksizin
```bash
Grep ‘is’ * 
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

### • dosya icerisinde “lin” isminden sonra sadece “u” olanlari listeler
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

•	Ls –R | grep .txt
Sonu ‘.txt’ ile biten dosyalari listelemek icin kullanilir

•	Sudo apt-get install mlocate
Locate komutunu yükler. Bu komut ile tüm bilgisayarda konum belirtmeden arama yapilir

•	Locate deneme.txt
Tüm bilgisayarda “deneme.txt” ara ve konumunu yazdirir

•	Sudo updatedb
Locate komutu günceller, böylece yeni eklenen veya silinen dosyalarin komunu yazdirilabilir

•	History | grep ‘find’
Daha önce kullanilan “find” komutlarini listeler

•	Which pwd
Bu komutun hangi dizinde kayitli oldugunu gösterir

•	Whereis pwd
Bu komut dosyasinin nerede oldugunu gösterir

•	wget https://raw.githubusercontent.com/awsdevopsteam/route-53/master/ken.jpg
“wget” komutu ilgili sayfadan belirtilen dosyayi indirir ve bulundugu klasöre kaydeder. Github alinan dosyalarin “raw” halini indirmemiz lazim.

•	Curl https://raw.githubusercontent.com/awsdevopsteam/route-53/master/index.html
Bu komut ile bir web sayfasini Linux komut sistemi üzerinden sorgulayabilir ve görüntüleyebiliriz

•	Curl –L https://raw.githubusercontent.com/awsdevopsteam -o /home/ubuntu/deneme
–L --> location belirtmek icin    -o --> ciktiyi dosya olarak kaydetmek icin kullanilir.
Burada sayfadan verileri alir ve /home/ubuntu/ altinda “deneme” olarak kaydeder


•	Echo edip | xargs –I {} echo {} {} 	# büyük i
Bu komut icine girilen degeri istenilen sayida tekrarlamak icin kullanilir


ORTAM DEGISKENLERI

!!! Asagidaki degiskenler büyük harfle ve basinda $ isareti ile girilmelidir.
•	PATH
Bu değişken, sisteminizin yürütülebilir dosyaları aradığı, iki nokta üst üste (:) ile ayrılmış bir dizin listesi içerir.

•	USER
Kullanici adi

•	HOME
Kullanicinin ana dizininin varsayilan yolu

•	EDITOR
Varsayilan text editörünün yolu

•	UID
Kullanici bensersiz ID

•	TERM
Varsayilan terminal ayari

•	SHELL
Kullanici tarafindan kullanilan kabuk

•	LANG
Gecerli yerel ayarlar

Komut satiri:
•	Printenv  -(yada)-  env
Bütün veya belirtilen ortam degiskenlerini listeler

•	Set
Tüm shell ve environment degiskenleri listeler

•	Printenv USER
USER degiskenini görüntelemek icin kullanilir

•	Echo $USER
USER degiskenini görüntülemek icin kullanilir

•	EDIPP=mahmutedipnegiz
Büyük harfler ile yeni bir degisken tanimlanabilir. Arada bosluk olmaz!!!


•	HOME=/home/ec2-user/edip
“cd” komutunu calistirinca bundan sonra gidecegi ana dizini tanimladik.

•	Unset EDIPP
Daha önceden tanimli bir degiskeni silmek icin kullanilir

•	Export 
Kabuk degiskenlerini diger kabuklara aktarmak icin kullanilir

•	Export EDIP=mahmutedipnegiz
Degiskeni cevresel degisken olarak tanimlar. Cercevesini genisletir

•	Echo $PATH
Komutlarin yolunu gösterir. Girilen program ve komutlar önce bu klasörlere bakilir ve varsa calistirir.

•	PATH=$PATH:/games/Pubg
Program calistirmak icin Yola yeni bir klasör eklenir. Artik komut calistirmak icin bu klasöre de bakar. Arada (:) olmak zorunda.

•	HOME=$HOME/home/Desktop
Ana dizine ekleme yapar. Eski dizin sabit kalir yeni dizini sona ekler. Üzerine yazmak icin degisken tekrar tanimlanmalidir.

•	Source my_script.sh  -(yada)-  . my_script.sh
Yazmis oldugumuz kod dosyasini bulundugumuz SHELL ortaminda calistirir. Execute olarak izin verilmeli.

•	./my_script.sh
Yazmis oldugumuz kod dosyasini farkli bir SHELL de calistirir, bizim bulundugumuz SHELL ortamina etki etmez. Execute olarak izin verilmeli.

•	vim .bashrc
bu komut ile ALIAS tanimlamasi yapariz ve SHELL her baglanmada otomatik olarak icindekileri tanimlar ve calistirir.

•	MYVAR="my name is $HOME"
Bu degiskeni yazdirince $HOME kismini komut olarak algilar ve yazdirir. (“) icine yazilan ifadelerde komut varsa ona komut olarak islem yapar.

•	MYVAR=’my name is $PATH’
Bu degiskeni yazdirince $HOME kismini metin olarak algilar ve yazdirir. (‘) icine yazilan herseyi metin olarak algilar ve yazdirir.

•	MYVAR=’”my name is \$PATH”
Bu degiskeni yazdirince $HOME kismini metin olarak algilar ve yazdirir. (\) kendinden sonrakini komut olarak algilamasini engeller








KULLANICI KOMUTLARI

•	Who
Sisteme kac kullanici bagli oldugunu listeler

•	W
Sisteme kac kullanici bagli ve ne yapiyor onu listeler

•	Sudo nano /etc/login.defs
Kullanici olusturma ile alakali configuration dosyasi acilir ve degisiklikler yapilabilir

•	Sudo Adduser edip
Yeni bir kullanici eklemek icin kullanilir

•	Su edip
Kullanici degistirmek icin kullanilir

•	Sudo useradd -m -d /home/edip -c "edip negiz" edip
Kullanici eklemenin bir diger yöntemi
o	–m		ana dizinin olusturulmasini saglar
o	–d		ana dizinin adini ayarlamak icin kullanilir
o	–c 		bir aciklama eklemek icin kullanilir


•	sudo passwd edip
Kullaniciya sifre tanimlamak icin kullanilir

•	sudo passwd –expire edip
Kullanicin sifresi süresi doldurulur ve ilk giriste sifre degistirmesi istenir.

•	sudo userdel –r edip 
Kayitli bir kullaniciyi silmek icin kullanilir. (-r) kullanicinin ana dizinini de siler. Normal silmede ana dizin durur sadece kullanici silinir

•	id edip
Kullanicin id bilgisini görüntülemek icin kullanilir

•	cat /etc/passwd
Kayitli tüm kullanici bilgilerini listeler

•	sudo usermod –c “aws solution archtitect” edip
Kullanicinin özelliklerini degistirmek icin kullanilir

•	Sudo usermod –l murat edip
“Edip” kullanici adini “Murat” olarak degistirir

•	sudo cat /etc/shadow
Kullanıcı parolaları şifrelenir ve “/etc/shadow” dosyasında saklanır. Bu dosya sadece okunur ve sadece root tarafından erişilebilir.


•	Sudo groupadd linux
Yeni bir grup olusturmak icin kullanilir

•	Sudo usermod –a –G linux edip
Kullanicilari gruplara eklemek icin kullanilir. (-a) append, kullanicinin eski gruplarindan cikmadan yeni gruba eklemesini saglar

•	Sudo cat /etc/group
Kullanicilar birkac gruba ait olabilir. Bu komut ile gruplar ve kullanicilari listelenir

•	Sudo groups
Kullanicinin hangi grupta oldugunu listeler

•	Sudo groupmod –n aws linux
Daha önceden var olan “linux” grubunun adini “aws” olarak degistirir

•	Sudo gpasswd –a edip aws
“Aws” grubuna edip kullanicisini ekler

•	Sudo gpasswd –d edip aws
“Aws” grubundan “edip” kullanicisini siler



PAKET YÜKLEME ISLEMLERI


•	Sudo yum update (Linux)
Linuxte yüklü bütün paketleri güncellemek icin kullanilir. Herseyi tekrar onay olmadan günceller.

•	Sudo apt update (Ubuntu)
Ubuntu makinelerde güncelleme yapmak icin kullanilir. Güncellenecek dosyalari listeler ve bizden onay ister.

•	Sudo apt upgrade (Ubuntu)
Ubuntu makinelerde güncellemesi sorgulanan dosyalarin güncellenmesi icin kullanilir.

•	Sudo yum install git (Linux)
Linux makineye git uygulamasi yüklemek icin kullanilir

•	Git -- version
Git uygulamasinin versiyonunu ögrenmek icin kullanilir

•	Sudo yum remove git (Linux)
Linux makineden git uygulamasini kaldirmak icin kullanilir. Uygulamanin baglantili dosyalarini kaldirmaz. Version kisminda git versionu görünür.

•	Sudo apt remove git (Ubuntu)
Ubuntu makinede git uygulamasini kaldirmak icin kullanilir

•	Sudo yum autoremove git –y (Linux)
Linuxte git uygulamasini tüm ek baglantilari ve yapilandirma paketleri ile birlikte onay istemeden kaldirir

•	Sudo apt purge git (Ubuntu)
Ubuntuda “Git” uygulamasini ve yapilandirma paketlerinin hespini kaldirir

•	Sudo yum info git (Linux)
Linuxte “Git” uygulamasi hakkinda bilgileri listelemek icin kullanilir


•	Sudo apt info git (Ubuntu)
Ubuntuda “Git”  uygulamasi hakkinda bilgileri listeler

•	Sudo yum list | more (Linux)
Linux icin yüklü olan ve yüklenebilir bütün paketleri listeler

•	Sudo yum list git (Linux)
Linuxte “Git” uygulamasinin yüklü dosyalarini ve versiyonunu listeler. Daha güncel bir versiyonu varsa onu da listeler

•	Sudo yum list installed | more (Linux)
Linuxte yüklü olan bütün uygulamalari listelemek icin kullanilir

•	Sudo apt list --installed (Ubuntu)
Ubuntu da yüklü olan bütün uygulamalari listelemek icin kullanilir

•	Sudo yum --showduplicates list git (Linux)
Linuxte “Git” uygulamasinin yüklenebilir tüm sürümlerini listelemek icin kullanilir

•	Sudo yum install git-2.14.5-1.amzn2 (Linux)
Linuxte “Git” uygulamasinin istenilen versiyonunu yüklemek icin kullanilir

•	Sudo yum update git –y (Linux)
Linuxte “Git” uygulamasini güncellemek icin kullanilir. Onay istemez.




FILTRE KULLANIM KOMUTLARI

•	Cat –n ali.txt
Listeleme yaparken “-n” ile satir sayilari ile beraber gösterir

•	Tac edip.txt
Dosya icerigini tersten baslayarak listeler

•	Cat edip.txt | tee ahmet.txt
“Tee” komutu ile dosya icerisine yazi ekler ve ekranda gösterir

•	Cat edip.txt | grep guzel
“cat” ile dosya icerigini listeler ve grep onlari filtreleyerek sadece “guzel” olan yeri listeler. “-w” ile sadece “guzel” satirini listeler, sonrasinda ifade varsa listelenmez. “-v” parametresi ile belirtilen kelime haric hepsini listeler.


•	grep naber -A 3 clarusway edip.txt
Dosya icerisinde “clarusway” arar ve “-A” (after) parametresi ile buldugu satirdan sonraki 3 satiri daha listeler. “-B”  (before) komutu ile önceki satirlari listeler. “-c” parametresi belirtilen kelime ile baslayan kac tane var sayar. “-wc” sadece belirtilen kelimeden kac tane var sayar.

•	ls * -l | cut -d' ' -f3
listelenen icerigin sadece belirli sütunlarini listelemek icin kullanilir. “cut” komutu sütunlara göre filtrelemek icin kullanilir. “-f3” kacinci sütunu alacagini belirler. “ d’ ‘ “ komutu ne ile ayrilmis oldugunu belirtmek icin kullanilir

•	cat /etc/passwd | cut -d: -f1
Kullanicilari listeler ve “:” ile ayrilan kelimelerden sadece birinci sütunu listeler.

•	Cat << SON > clarusway.txt 
“<<” isaretinden sonra kelime girilirse yazma islemini bitir anlamindadir. “SON” gördügü yerde yazma islemi sonra erer.

•	Cat clarusway.txt | tr ae OR
“tr” komutu ile icerisinde aktarilan metindeki harfleri degistirmek icin kullanilir. Burada “a”  “O” ve 
“e”  “R” harfine dönüsür. Sadece listelerken dönüsüm olur ana dosya degismez.

•	cat count.txt | tr '\n' ' '
Normalde asagiya yeni satirda listelenecek olan metinleri tek bir satirda arada bir bosluk ile listeler

•	cat edip.txt | tr –d aeiou
“tr” komutu ile birlikte kullanilan “-d” sil anlamindadir. Edip dosyasi icindeki belirli harfleri silmek icin kullanilir. Ana dosya etkilenmez.

•	cat clarusway.txt | tr [a-z] [A-Z]
Dosya icerisindeki bütün harfleri büyük olacak sekilde yazdirir.

•	cat edip.txt | tr [:space:] '\n'
tüm bosluklardan sonra “enter” eklemek icin kullanilir

•	Wc edip.txt
Edip dosyasi icindeki satir, kelime ve karakter olarak sayisini gösterir.
o	Wc –l	 sadece satir sayisini verir
o	Wc –c	 sadece karakter sayisini verir
o	Wc –w   sadece kelime sayisini verir

•	Sort ali.txt 
Dosya icerigini harf sirasina göre listeler. “-r” ile tersten yazdirabiliriz. “-u” ile ifadeleri uniq olacak sekilde listeler. “-f” büyük/kücük harf duyarsiz sekilde siralar. “-n” sonuclari sayisal siraya göre listeler.

•	Sort ahmet.txt | uniq
“Uniq” komutu her kelimeden birer tane gelecek sekilde listeler. ## sort komutu ile birlikte kullanilmasi zorunludur.

•	Comm file1.txt file2.txt 
İki dosyanin kesisimini almak icin kullanilir. İlk sütun sadece dosya 1 de olanlar. İkinci sütun sadece dosya 2 de olanlar. Ücüncü sütun iki dosyada da olanlari listeler. ## sort komutu ile birlikte kullanilmasi zorunludur.

•	Cd /home && ls && cat
Tek satirda birden fazla komut verilebilir. “&&” ilk komut basarili ise diger komutu calistirir. Ard arda bir sürü komut verilebilir.

•	Cd /home ; ls ; cat
Tek satirda birden fazla komut verilebilir. “;” ilk komut basarili olmasa bile diger komutu calistirir. Ard arda bir sürü komut verilebilir

•	Cd /home || ls || cat
Tek satirda birden fazla komut verilebilir. “||” ilk komut basarili degilse diger komutu calistirir veya ilk komut basarili olursa sonraki komutu yapmaz. Ard arda bir sürü komut verilebilir

•	Echo $?
Bir önceki girilen komut hatali ise hata kodunu yazdirir. Hata yok ise “0” döndürür.

•	rm edip.txt && echo 'silindi' || 'hata'
Islem yaparken “ && ve ||” birlestirerek kullanilabilir. Dogru olursa “&&” devreye girecek, yanlis olursa “||” devreye girecek.

•	Echo edip # burasi yorum satiridir
“#” isareti ile komut sonuna yorum satiri eklenebilir

•	Echo ahmet can \# artik yorum olamaz
“\” bu isaret kendinden sonra gelen özel karakterin özel gücünü elinden alir ve islevsiz yapar.

•	Echo –e “ahmet \n murat”
“-e” parametresi (\n) komutunu aktif hale getirir

•	./myscript 1> cikti.txt 2> error.txt
“1 --> standart output” cikti degerini cikti.txt icine kaydet
“2 --> standart error” ciktida hata varsa hatayi error.txt icine kaydet




SED, AWK VE CRONTAB KOMUTLARI

•	Sed –i ‘s/linux/ubuntu/’ ali.txt
Bu komut ali dosyasi icindeki ilk “linux” ifadesini bulur ve onu “ubuntu” olarak degistirir. Büyük-kücük harf duyarli degil. (-i) degisikligi dosyaya uygular ve kaydeder.

•	Sed ‘s/linux/ubuntu/ig’ ali.txt
Ali dosyasindaki bütün “linux” ifadelerini “ubuntu” olarak degistirir. (i) büyük-kücük duyarsiz sekilde, (g) bütün ifadeleri degistir

•	Sed ‘s/linux/ubuntu/2’ ali.txt
Ali dosyasindaki buldugu 2. “linux” ifadesini “ubuntu” yapar

•	Sed ‘3 s/linux/ubuntu/g’ ali.txt
Sadece 3. satirdaki bütün “linux” ifadelerini “ubuntu” olarak degistirir.


•	Awk ‘{print}’ ahmet.txt
Bu komut da “cat” komutu gibi dosya listelemek icin kullanilir

•	Awk ‘{print $3}’ ahmet.txt
Ahmet dosyasinin sadece 3. Satirini listeler.

•	Awk ‘/aksam/ {print $0}’ ahmet.txt
Ahmet dosyasinin icindeki aksam ile baslayan bütün satirlari listeler

•	awk '{ if($7 == "can") print $0}' ahmet.txt
Ahmet dosyasinin 7. Sütununda “can” ifadesi varsa o satiri komple listeler.

•	Crontab –e
Zaman olarak planli yapmak istedigimiz islemler icin crontab dosyasini düzenlemek icin kullanilan bir komuttur. 

* * * * *  date >> /home/ec2-user/veriler.log 
1 2 3 4 5       yildizlar zaman bakimindan ayarlamak icin kullanilir. Hicbir deger girilmezse dakika basi islem yapar.
o	1    bu kisim dakika icin kullanilir
o	2    bu kisim saat girmek icin kullanilir
o	3    bu kisim ayin kacinda onu belirtmek icin kullanilir
o	4    bu kisim ay girmek icin kullanilir
o	5    bu kisim ayin gününü belirtmek icin kullanilir

•	Crontab –e
25 12 * * * sudo yum install git –y
•	Bu komut saat 12:25 te git uygulamasini yükler

•	Crontab –ls
Crontab dosyasinda kayitli komutlari listelemek icin kullanilir




SHELL SCRIPT KOMUTLARI


•	Matematik islemlerinde sembollerin yerine kullanilan komutlar
o	–lt	 	<
o	–gt		>
o	–le		<=
o	–ge		>=
o	–eq		==
o	–ne		!=
o	–z		bos string
o	–n		bos olmayan string

•	Bir Linux dosyasıyla ilişkili çeşitli özellikleri test etmek için kullanılabilecek birkaç operatörler.
o	–d		directory
o	–e		exist
o	–f 		Ordinary file 
o	–r		readable 
o	–s 		size is > 0 bytes
o	–w		writable
o	–x		executable


•	“if .. then” komut satiri kullanimi bu sekildedir. Komutun calismasi icin dosyanin “chmod +x” ile calistirilabilir hale getirilmesi gerekir.

#!/bin/bash
              if ["foo" = "foo"]; then
  	echo “bunlar birbirine esit”
              fi


•	“if .. then .. else” komut satiri kullanimi bu sekildedir.

if [ $num -eq 5  ] 	 #  (($num + 5)) “aritmetik(toplama vb.) islem varsa kullanilir”
then
	echo “sayi 5 e esittir”
elif (( $num < 5 )) 	– yada –	   [$num –lt 5]
then
    echo "sayi 5 ten az"
else
    echo "sayi 5 ten fazla"
fi

•	Ic ice “if..then..else” komut kullanimi bu sekildedir.

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

•	“If..then..else” dosyasinda “degil, or, and” kullanimi asagidaki ifadeler ile olur.
o	! 		degil
o	&&		and
o	||		or

#!/bin/bash
read -p "Adinizi girin: " NAME
read –s –p "Sifreinizi girin: " SIFRE	# “-s” sifre girerken görünmemesini saglar
if [ $NAME = $(whoami) ] && [ $SIFRE = 12345 ]
then
        echo -e "\nWelcome $(whoami)"		# “-e” icerideki \n gibi islemleri aktif eder
else
        echo -e "\nYanlis giris"
fi
•	“For” döngü kullanimi bu sekildedir. Bir dize içindeki bir dizi 'kelime' ve ‘sayilar’ üzerinde yineleme yapmanızı sağlar.
#!/bin/bash
for i in $( ls ); do	# $(ls) yada `ls`   ikisi de ayni.   `pwd`/*   klasördeki tüm dosyalarin konumlari
   echo item: $i
done

------------------------------------------------------------------

A =  (“S3” “EC2” “Lambda” “Glacier” “CloudFront” “Kinesis”)
for x in S3 EC2 Lambda Glacier CloudFront Kinesis	# $x[@]  tüm listeyi gezer. @ tüm liste anlamindadir.
do
  echo "Amazon Service: $x"
done

------------------------------------------------------------------ 

#!/bin/bashs
echo "Numbers:"
for number in {1..10}	      # 1 den 10 a kadar sayi üretir	
do
   echo $number
done


•	“While” kosul dogru ise islem yapar, yanlis olursa islemi sonlandirir. “done” komutu ile döndügen cikilir.

#!/bin/bash
COUNTER=0
 while [  $COUNTER -lt 10 ]; do
     echo The counter is $COUNTER
     let COUNTER=++COUNTER		# ((COUNTER++) ifadesi de kullanilabilir
done


•	“Until” kosul yanlis ise islem yapar, dogru oldugu zaman döngüden cikar. “done” komutu ile döngüden cikilir.

#!/bin/bash
number=1
until [[ $number -ge 10 ]];do
        echo $number
        ((number++))
done
echo "Now, number is $number"


•	“Select..case..esac” kullanimi asagidadir. Kendisi otomatik numaralandirir ve  secimi uygular. (If ifadesinin farkli bir versiyonudur)

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


•	Fonksiyon tanimlamasi bu sekildedir. Calistirmak icin sadece fonksiyonu cagirmak yeterlidir.

#!/bin/bash
function cikis () {
   exit
}
function hello () {
   echo Hello People!
}
Hello
cikis
---------------------------------------------

#!/bin/bash
welcome (){		# function yazmadan direk fonksiyon ismi verilebilir
    echo "Welcome to Linux Lesson"
}
welcome








DERSTEKI CALISMALAR

•	Önce klasör var mi diye kontrol ediyoruz, eger klasör yoksa o isimde klasör olusturuyor
#!/bin/bash
if [ -z "$(ls | grep edip)" ]; then	# “-z” bos ise anlamindadir.
        mkdir edip
        echo "Edip klasörü olusturuldu"
else
        echo "Böyle bir klasör var"
fi


•	Istenilen program var mi diye version üzerinden kontrol ediyor yoksa indiriyor
#!/bin/bash
git --version
if [[ $? == 0 ]]
then
          echo " Already exits"
else
          yum update -y
  	    yum install git
fi


•	Girilen sayinin büyük olup olmamasina göre islem yapan fonksiyon
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


•	100 e kadar olan tam sayilarin toplamini veren program
#!/bin/bash
sonuc=0
for i in {1..100}
do
    ((sonuc=sonuc+i))
done
echo $sonuc
