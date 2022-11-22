
# ***VSCode***
## IntelliSense - Emmet (Bkz: ul>li*10)
## Terminal Use 101
  - pwd (MacOS / Linux) / echo %cd% (Windows)
  - cd Desktop (Klasöre Zıplamaca)
  - cd .. (Klasörden Vınn)
  - cd <klasorismi> (Dizine Zıplamaca)
  - mkdir >klasöradı> (Yeni Klasör Oluşturmaca)
  - ls (Klasördeki dosyaları listeleme)
  - (ctrl + L --- Terminal'i temizlemece)
## MultiCursor Kullanımı (ctrl + D) (ESC ile kapanır!)
 - (Ctrl+Shift+L --- Aynı tag/kelimleri toptan seçmece)
 - (Ctrl+L --- Satırı seçmece)
 - (fn+home / fn+end --- Satırların başına/sonuna gitmece)
 - (Ctrl+ sağ/sol ok tuşu --- Kelimeler arası geçiş)
 - (Alt+Shift+Fare --- Manuel MultiCursor)
 - (Alt tuşuna basarken satırlara tek tek tıklama --- Tıklanan satırlarda cursor açar!)
 - (Alt tuşuna basarken yukarı/aşağı ok tuşu --- Satır taşıma!)
 - (Shift + sağ/sol ok tuşu --- Kelimeyi seçerek ilerler!)
 - (Shift + sağ/sol ok tuşu ile seçtikten sonra Ctrl +D --- Aynı tag/seçimlerde toptan değişiklik!)
## Klavye Kısayolları
  - Klavye kısayollarını kişiselleştirmek: File -> Preferences -> Keyboard Shortcuts
  - Proje dosyalarını açmak (Ctrl+P)
  - Ayarlar içinde arama (Ctrl+Shift+P)
  - Açık olan dosyayı kapatma (Ctrl+W)
  - Menü çubuğunu aç/kapa (Ctrl+B)
  - Bir ifadenin tamamını seçmek (Ctrl+Shift+Sol ok işareti)
  - Seçili olan ifadeyi bir alt satıra da kopyalamak (Alt+Shift) (!)
  - İmlecin yeri farketmeksizin bir alta satır açmak (Ctrl+Enter)
  - Quick Split (Ctrl+P sonrası Ctrl+Enter)
  - Hızlı yorum satırı (Ctrl+Shift+A)
  - Cümleyi yorum satırına çevirme (Ctrl+K+C)
## Snippets
  - Sürekli yazılan kod blokları için kısayol atama
  - CTRL + SHIFT + P   -->   Preferences: Configure User Snippets
  - https://code.visualstudio.com/docs/editor/userdefinedsnippets
## Ayarların Kişiselleştirilmesi
  - Ayarların json olarak görüntülenmesi
  - Popüler ayarların kopyalanması
  - Font seçimi yapılırken "monospace" olmasına dikkat edilmesi!
## Diğer Kod Editörleri (İndir ve dene!)
  - Sublime Text
  - Atom
  - IntelliJ IDEA
  - VSCodium

---


# ***GIT*** 
## GIT Kurulumu
 - sudo apt-get install git-all (Linux/MacOS)
 - GitBash install! (Windows)
## GIT Nedir?
 - Dağıtık haldeki dosyaları ve versiyon kontrol bilgileri depolama ve cihaz bağımsız erişim
 - "commit" yaparak SnapShot (anlık görüntü) özelliği ile istediğiniz zaman proje veya dosyaların o anki halini kayıt altına alabilirsiniz. Böylelikle ileride bir hata ile karşılaşırsanız herhangi bir zamandaki herhangi bir versiyona dönüş yapabilirsiniz.
  - SnapShot alındıktan sonra değişiklik yapılan dosyaları görebilirsiniz.
  - Takımların aynı projede beraber çalışmasına imkan verir. Kim neyi düzenledi? Ne ekledi? Ne çıkarttı? Son değişiklik ne zaman yapıldı? gibi bilgilere erişebilirsiniz. Bu sayede topluluk ile proje geliştirme süreçlerini kolaylaştırabilirisiniz.
  - Projede verisyonlanmasını istemediğiniz dosyaları belirtebilirsiniz. (node_modules, .mp4, .log, .env gibi) --> Bkz: gitignore

  - GitHub/GitLab/BitBucket: GIT versiyon kontrol sistemlerini kullanan hosting servislerid## GIT Bash ile GIT Temel Komutları (VSCode içinden Terminal --> New Terminal)  

  ![Git](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/git/git-bash-ile-git-temel-komutlari/figures/3-GitHub-cheat-sheet-graphic.jpg)
          
---
   *Henüz versiyon kontrolü altında olmayan bir projenin dizininde, boş bir git deposu oluşturmak için:*      
```bash
$ git init
```

        
        
*GIT’in bir çok konfigürasyon ve ayarı vardır, bunlardan ikisi user.name ve user.email olanıdır. Bu ayarları yapılandırmak için aşağıdaki komutları kullanırız. GIT'i ilk kurduğumuzda genellikle aldığımız ilk hata bu configurasyon ayarlarını yapmadığımız için gelir. Burada yazdığınız isim ve email ileride GitHub benzeri bir plat forma commit attığınızda da görüneceği için bunu bilerek isimlendirme yapmak yararlı olur. Ayrıca görüldüğü gibi bu ayarlar --global yani sistem genelinde geçerli ayarlardır. Proje bazlı bu ayarları değiştirebiliriz.*
```bash
$ git config --global user.name "Name Surname"
$ git config --global user.email "test@email.com"
```

*Bu ayarların tümünü görmek için:*
```bash
$ git config --list
```
        
↓ *Windows'ta şöyle bir hata olabilir:* ↓ 
```bash
warning: LF will be replaced by CRLF in kaynak/dosya/yolu"
```
*Bunu şöyle basit bir şekilde çözebiliriz:*
```bash
$ git config core.autocrlf true
```
---

### Temel Komutlara Değinelim

*Yeni eklenen veya üzerinde değişiklik yapılan dosyaları staged ortamına göndermek için kullanılır.*
```bash
$ git add <dosya veya klasor_name>
``` 
*Tek seferde bütün dosyaları eklemek (gitignore yoksa yapmazsan daha iyi) (. Tüm dosya uzantılarını ifade eder. / A da all anlamında!)*
```bash
$ git add .  veya  $ git add *  veya   $ git add -A . 
```  
*Staged ortamına eklenmiş bir dosyanın takibinin bırakılması yani untracked (izlenmeyen) hale getirilmesi sağlayan komuttur.*
```bash
$ git rm  --cached <dosya veya klasor_name>
```
*Bu da dosyayı klasörden silmek için*         
```bash
$ git rm <dosya veya klasor_name>
```
*Üzerinde çalışılan projenin o anki durumu hakkında bilgi verir. Yapılan değişiklikler, eklenen ve silinen dosyalar gibi bilgiler listelenir.*
```bash
$ git status
```
         
![GitStatusKomutuTerminalÇıktısı](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/git/git-bash-ile-git-temel-komutlari/figures/5-git-status-1.png)

- On branch main -> Main branch'ınde olduğumuzu,
- Changes to be commited -> Commit'lenmeye hazır değişiklikler olduğunu,
- Modified: index.html -> Index.html dosyasında değişiklik yaptığımızı,
- Deleted: styles.css -> styles.css dosyasını sildiğimizi bize belirtir.  

*Commit, staged ortamına alınan dosyaların Local Repository’e gönderilmesidir. En iyi uygulama yöntemi her kayıt sırasında yapılan değişiklikleri açıklayıcı bir mesaj eklemektir. Ayrıca her commit benzersiz bir kimliğe (unique ID) sahip olur. Bu sayede eski bir commit'e geri dönebilirsiniz ve herhangi bir kayıp yaşama ihtimaliniz kalmaz.*
```bash
$ git commit -m "ilk commit mesajı"
```
Projedeki commit geçmişini görüntülememizi sağlar. Bütün commit'ler, id'si, yazarı, tarihi ve mesajı ile beraber listelenir.
```bash
$ git log
```

![GitLogTerminalÇıktısı](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/git/git-bash-ile-git-temel-komutlari/figures/6-git-log.png)

*Local veya remote repository üzerinde yeni bir branch (dal) eklemek, silmek veya listelemek:*

*Projenize yeni bir branch eklemek için:*
```bash
$ git branch <branch_name>
```
*Tüm uzak ve yerel branch'lari listelemek için*
```bash
$ git branch -a
```
*Bir branch'ı silmek için*
```bash
$ git branch -d <branch_name>
```

*Branch’ler arası veya commit'ler arası geçiş yapmak istediğimizde:*

*Mevcutta var olan branch'a geçiş yapmak için:*
```bash
$ git checkout <branch_name>
```
*Yeni bir branch oluşturup, bu branch'a geçiş yapmak için:*         
```bash
$ git checkout -b <branch_name>
```
*Commitler arası geçiş yapmak için: (Eski bir versiyona dönmek istediğimiz zaman)*
```bash
$ git checkout <commit_ID>
```
*Başka bir branch'da olan değişiklikleri, bulunduğumuz branch ile birleştirmek istediğimizde:*          
```bash
$ git merge <branch_name>
```
*Mevcut bir Remote Repository'de bulunan dosyaların bilgisayarımızda bir kopyasının oluşturulması:*
```bash
$ git clone <remote_URL>
```
 *Projemizde aldığımız commit'leri, remote repository'e göndermek:*
 ```bash
$ git push origin master
 ```

*Burada bahsi geçen origin remote repository’nin kök dizinini belirtir ve sabit bir isimdir. master ise sizin çalıştığınız branch (dal)’ı belirtir.*

*Henüz remote repository’niz yoksa aşağıdaki komut ile local deponuzu uzak sunucudaki depoya bağlayabilirsiniz:*
```bash
$ git remote add origin http://uzak_deponun_adresi.git
```

*Repository üzerinde yapılan değişikliklerden sonra dosyalar arasında oluşan farklılıkları görmek için bazı komutlar:*
*Çalışma dizini ile repository (HEAD) arasındaki farklılıkları görmek için:*
```bash
$ git diff HEAD
```
*İki commit arasındaki farklılıkları görmek için:*
```bash
$ git diff <commit_id_1>..<commit_id_2>
```
*Çalışma dizini ve staged ortamı arasındaki farkları görmek için:*
```bash
$ git diff --staged
```
           
          
## VSCode'da Terminal Kullanmadan GIT Komutları
  
Activity Bar --> Source Control
![ActivityBarSourceControl](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/vs-code-icerisinde-terminal-kullanmadan-git-temel-komutlari/figures/1-git-init.png)

Yeni eklenen veya üzerinde değişiklik yapılan dosyaları staged ortamına göndermek için Stage Changes butonuna tıklamalıyız. (alt="Dosya isminin yanındaki +")
![Stage Changes Button](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/vs-code-icerisinde-terminal-kullanmadan-git-temel-komutlari/figures/2-git-add-1.png)

Birden fazla dosyamız olduğu zamanlarda eğer bütün değişiklikleri tek bir seferde staged ortamına göndermek istiyorsak Stage All Changes butonuna tıklamalıyız. (Changes sekmesinin yanındaki +)
![Stage All Changes](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/vs-code-icerisinde-terminal-kullanmadan-git-temel-komutlari/figures/2-git-add-2.png)

Staged ortamına dosyayı eklediğimizde aşağıdaki resimde olduğu gibi, dosyanın yanında "A" (1) (added) yazacaktır. Staged ortamına eklemediğimiz dosyalar olursa bu dosyaların yanında da "U" (2) (untracked) yazacaktır.
![Added/Untracked](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/vs-code-icerisinde-terminal-kullanmadan-git-temel-komutlari/figures/3-git-status-1.png)

Commit, staged ortamına alınan dosyaların Local Repository’e gönderilmesidir. En iyi uygulama yöntemi her kayıt sırasında yapılan değişiklikleri açıklayıcı bir mesaj eklemektir. Ayrıca her commit benzersiz bir kimliğe (unique ID) sahip olur. Dosyalarımızı commit'lemek için Message bölümüne (1) commit'imizi açıklayıcı bir mesaj yazmalıyız ve ardından Commit butonuna (2) basmalıyız.
![first-commit](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/vs-code-icerisinde-terminal-kullanmadan-git-temel-komutlari/figures/4-git-commit.png)

Commit'lenen dosya üzerinde değişiklik yaptığımızda, dosyanın yanında "M" (1) (modified) yazacaktır.
![Modified](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/vs-code-icerisinde-terminal-kullanmadan-git-temel-komutlari/figures/3-git-status-2.png)

Dosyamızda yapılan değişikliği görüntülemek için, Source Control bölümünde, dosyanın üzerine tıkladığımızda (1), iki farklı bölüm karşımıza geliyor. En sağdaki bölümde (3) dosyamızın üzerinde yapığımız değişiklileri görüntüleyebiliriz.
![YapılanDeğişikliklerinGörüntülenmesi](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/vs-code-icerisinde-terminal-kullanmadan-git-temel-komutlari/figures/5-git-diff.png)

Bu değişiklikleri eğer geri almak istersek, tekrar sol bölümdeki (2) gibi olmasını istiyorsak Discard Changes butonuna tıklamalıyız.
![DiscardChanges](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/vs-code-icerisinde-terminal-kullanmadan-git-temel-komutlari/figures/6-discard-changes.png)

Eğer remote repository'e bağlıysak ve commit'lerimizi remote repository'e göndermek istersek Views and More Actions (1) butonuna tıklayıp, Push (2) seçeneğini seçmeliyiz.

![Push](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/vs-code-icerisinde-terminal-kullanmadan-git-temel-komutlari/figures/7-git-push.png)

## .gitignore Dosyası ne İşe Yarar? Nasıl Kullanırız?     


.gitignore dosyası projemizin kök dizinine oluşturulan düz bir metin dosyasıdır. Adından anlaşıldığı gibi diyor ki beni göz ardı et. Daha doğrusu göz ardı etmek istediğin, local çalışma alanındaki takip edilmesini istemediğin, takım arkadaşların için gerekmeyen dosyaların varsa veya bu dosyaların boyutu reponuza atmanıza gerek olmayacak kadar büyük ölçekli ise buyur beni kullan diyor.

Peki nedir bu tür dosyalar ?
- Paket yöneticisinden indirilen bağımlılıklar,
- image ve video dosyalarınız(dosya boyutları çok fazla olabilir)
- IDE eklentileri( örneğin .vscode)
- Sadece kendi çalışma alanınızda olması gereken başkaları tarafından görülmemesi gereken dosyalarınız (veritabanınıza ilişkin konfigürasyonlar)
- API anahtarları, kimlik bilgileri veya hassas bilgiler içeren dosyalar(.env)
- Çalışma dizinizdeki geçici dosyalar
- Log dosyaları
- Yararsız sistem dosyaları (örneğin MacOS işletim sisteminin .DS_Store dosyası )
- dist gibi oluşturulan dosyalar
- Veya herhangi bir dosyanız da olabilir.

**Nasıl oluşturulur?**  
  
Reponuzu oluştururken verilen seçeneklerde add gitignore file dosyasına tıklayarak reponuzla beraber oluşturabilirsiniz. Aynı şekilde editörünüzde .gitignore şeklinde de oluşturabilirsiniz.

**Terminalden:**

Proje dizininize cd komutu ile gelerek;
*@MacOS / Linux*
```bash
$ touch .gitignore 
```
*@Windows*
```bash
$ echo some-text or nothing > .gitignore
```
Buradaki some-text or nothing kısmı .gitignore dosyasına yazılmasını istediğiniz metini ekler. Hiçbir şey de yazmayabilirsiniz.


Nasıl çalışır, nasıl kullanılmalı?

.gitignore dosyasının her satırına takip edilmesini istemediğimiz dosyaları veya dizinleri yazarak göz ardı edebiliriz.

Tabii bu dosyaları yazarken bize kolaylık sağlayan bazı formatlar var. İşte onlar:
- .env
- node-modules/ dist/ logs/
- log files/
- /build (production)
- /node_modules (dependencies)

------------------
Ek:

- Dizinleri ise klasörün sonuna `/` işareti ekleyerek  belirtiriz. 
- `*` yıldız karakteriyle ise belirtilen ilk örnekte `.log` uzantısına sahip dosyaların tümünü, ikinci örnekte ise `files` klasör içerisindeki bütün dosyaları izlemeyi bırakacaktır. 
- Eğer ki bir klasörümüzü içerisindeki bir dosya haricinde izlenmesini istemiyorsak `!` işareti ile bunu sağlayabiliriz. Bu örnekte `files` klasörü içerisindeki `example.txt` haricindeki dosyalar izlenmeyecektir. Files klasörü içerisindeki sadece **example.txt** git akışında görülecektir.

- !files/example.txt
- Yukarıdaki örnekte dikkat edilmesi gereken önemli bir ayrıntıyı açıklayacak olursak eğer ki daha öncesinde `files` klasörü `.gitignore` dosyasına eklenmişse sonrasında ise `!`  içerisindeki dosya ile işlem yapmak işe **yaramayacaktır.**
- files/ !files/example.txt

- `.gitignore` dosyasında yorum satırı oluşturmak için ise `#` karakteri kullanılır.

---------------------------------------------
- Eğer projenizi `git add .` veya `git commit ` etmişseniz sonrasında  `.gitignore`  dosyasına eklemek istediğiniz dosyayı ekleseniz de bu işlem gerçekleşmeyecektir ve o dosyanız reponuzda hala GIT ile takip edilecektir. Tabi her şeyin bir çözümü olduğu gibi bu sorunu da çözmenin bir yolu var. İşte o çözüm:

```bash
$ git rm --cached FILENAME
```

Hani olur da derseniz ben belli dosyalarımı her seferinde .gitignore dosyasına eklemek istemiyorum bunu tek seferde halledebilir miyim ? Tabii ki.. (Burada kastımız başka başka projeler için her seferinde eklememek.)

Windows kullanıcısı iseniz C:\Users\{myusername}\ adresine giderek .gitignore_global dosyası oluşturup içerisine global olmasını istediğiniz dosyaları ekledikten sonra git bash terminalinizi açarak aşağıdakı komut ile konfigürasyon sağlayabilirsiniz.
```bash
$ git config --global core.excludesfile "%USERPROFILE%\.gitignore"
```

Dosyanızın doğru çalıştığını kontrol etmek için ise aşağıdaki komutu çalıştırarak aşağıdaki çıktıyı aldığınızda sorunsuz çalıştırabilmişsinizdir. (Aşağıdaki kodu kopyala yapıştır yapmadan önce kullanıcı adını değiştirin.)
```bash
$ git config --global core.excludesfile
> C:/Users/user-name/.gitignore_global  
```

Son olarak hangi .gitignore dosyalarını eklemeliyim derseniz [buradan](https://github.com/github/gitignore) hangi dil, framework vs kullanıyorsanız ona ait .gitignore dosyalarını bulabilirsiniz. Global olarak düzenlemek istediğiniz .gitignore dosyalarına da [buradan](https://github.com/github/gitignore/tree/main/Global) erişebilirsin

## GIT - Proje İçindeki Birden Fazla Dosyanın Versiyon Kontrol Sistemine Eklenebilmesi

Projelerimizde bulunan birden fazla dosyanın versiyon kontrol sistemine gönderilmesi ve nasıl kontrol edebileceğimiz ile ilgili komutlar:

**git add**

Bu komut belirttiğimiz dosyaları veya tüm proje dosyalarını versiyon kontrol sistemine göndermemize yardımcı olur. Aşağıdaki kullanım index.js dosyamızı versiyon kontrol sistemine göndermiş oluruz.
```bash
git add index.js
```

git add komutumuzun sonuna . ifadesini kullanarak versiyon kontrol sistemine tüm dosyalarımızı göndermiş oluruz.
```bash
git add . 
```


**git commit**

```bash
git commit -m "ilk commit" 
``` 
komutunu çalıştırdığımızda “ilk commit” başlığıyla o anki çalışma dizinindeki dosyaları .gitklasörü içindeki özel bir bölüme(head) ekler.
![gitcommit](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/git-proje-i%CC%87cindeki-birden-fazla-dosyanin-versiyon-kontrol-sistemine-eklenebilmesi/figures/ilk-kommit.png)

**git push**

Commit’lediğimiz dosyaları versiyon kontrol sistemimize gönderir.

![gitpush](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/git-proje-i%CC%87cindeki-birden-fazla-dosyanin-versiyon-kontrol-sistemine-eklenebilmesi/figures/git-push.png)

GitHub hesabımızı kontrol ettiğimizde tüm dosyaların ve commit işlemlerimizin ulaştığını görmüş oluruz.

![GitHubHesabıKontrol](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/git-proje-i%CC%87cindeki-birden-fazla-dosyanin-versiyon-kontrol-sistemine-eklenebilmesi/figures/github.png)


Ekstra:
https://education.github.com/git-cheat-sheet-education.pdf
https://medium.com/@alianilkocak/temel-git-terimleri-ve-komutlar%C4%B1-6bc62b802baf

---

## Markdown

Markdown, John Gruber ve Aaron Swartz tarafından geliştirilen ve 2004 yılından bu yana kullanılan metinden HTML'e (text-to-HTML) dönüşüm için kullanılan hafif bir işaretleme dilidir.

### Başlıklar

HTML'de `<h1>`, `<h2>`, `<h3>` etiketleri ile aç-kapat yaparak oluşturduğumuz başlıkları, Markdown ile sadece `#` karakteri kullanarak oluşturabiliyoruz. (Burada önemli olan nokta # karakterinden sonra boşluk bırakmaktır.)

`h1` ve `h2` başlıklar yazarken alternatif olarak bir yöntem daha mevcut. `h1` için `=` ve `h2` için `-` kullanabilirsiniz.

### Kalın, Eğik ve Üstü Çizili İfadeler

Yaygın kullanımda kalın yazmak için `**`, eğik yazmak için `*`, hem kalın hem eğik yazmak için `***` kullanılmaktadır.

### Tek ve Çok Satırlı Kod Blokları

Tek satır kod bloğu için kodun başına ve sonuna ` (backtick) karakteri eklenir.

  \`console.log("Hello, World!");\`

  Çıktı:
  `console.log("Hello, World!");`

  Çok satır kod bloğu için kodun başına ve sonuna 3 adet ` ``` ` backtick karakteri eklenir.


Çıktı:
```
function (){
console.log("Hello, World!);
}
```

Yazılım diline göre kod bloğundaki ifadelerin stillendirilmesini isterseniz, kod bloğunun başındaki 3 adet backtick ifadesinden sonra javascript, python, css gibi etiket ekleybilirsiniz.

Çıktı:

```javascript
function (){
console.log("Hello, World!);
}
```

### Yatay Çizgi

İçerikte bölümleme yapmak için ` --- ` kullanabilirsiniz. HTML'deki karşılığı `<hr>` olan bu ifade;

Çıktı:

---

### Listeler

HTML'de `<ul>` `</ul>` ve `<li>` `</li>` etiketleri ile oluşturulan listeler Markdown formatında `-` ve `*` ile oluşturulur.

```
- Liste Elemanı 1
- Liste Elemanı 2
- Liste Elemanı 3
```
Çıktı:
- Liste Elemanı 1
- Liste Elemanı 2
- Liste Elemanı 3

Sıralı liste elde etmek için tek yapmanız gereken liste elemanlarının başına sıra numarası ve . nokta eklemek.

```
1. Liste Elemanı
2. Liste Elemanı
3. Liste Elemanı
```
Çıktı:
1. Liste Elemanı
2. Liste Elemanı
3. Liste Elemanı

Buradaki önemli nokta şu: Siz farklı sıra numaraları vermek isteseniz de Markdown sıra numaralarını otomatik olarak biçimlendirmektedir. Aşağıdaki örnek üzerinden inceleyelim;

```
1. Liste Elemanı
8. Liste Elemanı
13. Liste Elemanı
```
Çıktı:
1. Liste Elemanı
8. Liste Elemanı
13. Liste Elemanı

Gördüldüğü üzere biz 1, 8 ve 13 olarak numaralandırdık fakat çıktı sıralı olarak üretildi.


Markdown ile iç içe listeler yapmak da oldukça kolay. Alt listelere tab ile girinti verdiğinizde otomatik olarak nested list yapısına dönüşmekte.

```
1. Liste Elemanı
    1. Alt Liste Elemanı
    2. Alt Liste Elemanı
2. Liste Elemanı
3. Liste Elemanı
```
Çıktı:
1. Liste Elemanı
    1. Alt Liste Elemanı
    2. Alt Liste Elemanı
2. Liste Elemanı
3. Liste Elemanı


### Tablolar

```
| Ürünlerin Numaraları| Ürün Açıklaması| Ürünlerin Fiyatı|
| :--- | :---: | ---: |
| 1 | Açıklama | Fiyatı |
```

Çıktı:
| Ürünlerin Numaraları| Ürün Açıklaması| Ürünlerin Fiyatı|
| :--- | :---: | ---: |
| 1 | Açıklama | Fiyatı |

### Bağlantı ve Resim Eklemek

HTML'den aşina olduğumuz `<a>` etiketi yerine Markdown'da `[]()` karakterleri ile;

```markdown
[Kodluyoruz Sayfamız](https://www.kodluyoruz.org/)
```
yapısı kullanılır. Köşeli parantez bağlantı açıklamasını, küme parantezi ise linki barındırır.

Çıktı ise şöyledir; [Kodluyoruz Sayfamız](https://www.kodluyoruz.org/)


Bağlantı resimleri de aynı şekilde eklenir. Sadece köşeli parantezden önce bir tane ! ünlem işareti eklenmelidir.

```markdown
![Kodluyoruz Logo](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/markdown-nedir-nasil-kullaniriz-/figures/kodluyoruz_logo.jpg)
```
Yapısı kullanılır. Köşeli parantezin için doldurmak zorunlu değildir. Boş da kalabilir. Çıktı aşağıdaki gibi olacaktır;

![Kodluyoruz Logo](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/markdown-nedir-nasil-kullaniriz-/figures/kodluyoruz_logo.jpg)


### Alıntı

Yazınız içinde alıntı kullanmak isterseniz yapmanız gereken, metinin başına `>` karakteri koymaktır.

```markdown
 > Alıntı yapılan metin.
 ```

 Elde ettiğimiz çıktı:

> Alıntı yapılan metin.



# ***HTML***

### HTML Nedir?

HTML (Hypertext Markup Language) yani Hiper Metin İşaretleme Dili, web sayfalarında gördüğümüz iskelet yapısını oluşturmak için kullanılan metin işaretleme dilidir. Bir programlama dili olarak tanımlanmayan HTML' e metin işaretleme dili denilmesinin sebebi, HTML kodlarıyla çalışan bir program yazamadığımızdan kaynaklıdır.

### HTML Ne Yapar?

- Web sayfasında gördüğümüz görseller, yazılar ve videoların konumlandırılmasını sağlamaktadır.
- Konumlandırılan web sayfalarının web tarayıcılar tarafından doğru bir şekilde görüntülenmesini gerekli kuralları belirler.  
  

HTML aslında bilgisayarda sürekli olarak kullandığımız web sitelerinin oluşmasında kullanılan bir dildir. Yazılan kodlar web tarayıcıları (browser) tarafından web sayfalarına dönüştürülmektedir. Tabi ki bu web sayfalarının sadece HTML kodlarıyla oluşmuyor. HTML kodlarının yanında CSS ve JavaScript dilleri de kullanılmakta. Ancak bu dillere şu an bakmanıza gerek yok. Öncelikle HTML dilinin mantığını, tarihini ve web tarayıcıları hakkındaki bilgilerle başlayalım.

### HMTL Tarihi

[HTML](https://tr.wikipedia.org/wiki/HTML), 1980'li yılların başlarında bir ihtiyaç neticesinde oluşturulmaya başlanmıştır. CERN' de çalışan Tim Berners-Lee, CERN araştırmacılarının bilgilerini ve dokümanlarını birbiriyle paylaşmak için bir sistem oluşturmuş ve bu sisteme ENQUIRE ismini vermiştir. Bu sürecin devamında Tim Berners-Lee, 1989 yılında internet tabanlı sistemin temellerini atmaya başlamıştır. Bu temellerin atılmasından 1 yıl sonra yani 1990 yılında HTML dili geliştirilmiştir. HTML dili ile birlikte hepimizin bildiği www (World Wide Web) sistemi de kurulmuştur. Artık hayatımızın bir parçası olan web dünyasının temeli HTML, günümüzün vazgeçilmez teknolojileri arasında yerini almıştır.

### Web Tarayıcısı

"HTML Nedir?" sorusunun cevabını iyi bir şekilde anlamak için [web tarayıcıları](https://tr.wikipedia.org/wiki/Web_taray%C4%B1c%C4%B1s%C4%B1) hakkında kısa da olsa bilgi sahibi olmak gereklidir. Aslında hepimizin sürekli halde kullandığı web tarayıcıları basit anlamıyla; www (World Wide Web) sisteminde bulunan bilgileri görüntülemeye yarayan teknolojiler olduğunu söyleyebiliriz. Bir web tarayıcısı internet dünyasındaki istediğiniz bir noktaya gitmenizi sağlayarak metin, resim ve videolar görmenize imkan verir.

### İlk Web Sayfamızı Oluşturalım

```html
<html>
  <head>
    <title>Kodluyoruz</title>
  </head>
  <body>
    <h1>Kodluyoruz "HTML Nedir?" Yazımıza Hoş Geldiniz</h1>
    <p>İlk Web Sayfamız</p>
  </body>
</html>
```

Yukarıdaki kodu çalıştırdığımız zaman aşağıdaki gibi bir çıktı görmüş olacağız. Aşağıda Google web tarayıcısını kullandık. Ancak sizin web tarayıcınız farklı bir tarayıcı olabilir. Burada elde ettiğimiz çıktı tarayıcıdan tarayıcıya değişen bir durum değildir.

![İlkWebSitesiÖrneği](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/html/html-nedir/figures/%C4%B0lk-Web-Sayfam%C4%B1z.png)

**Hemen aşağıda codepen ile deneyimleyebilirsin!**

<div class="cp_embed_wrapper"><iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/RworQRx?height=300&amp;theme-id=dark&amp;slug-hash=RworQRx&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_RworQRx"></iframe></div>

---

## En Çok Kullanılan HTML Etiketleri Nelerdir?

Yazıya başlamadan önce HTML dilinde bir etiket nasıl oluşturulur bunu göstermek istiyorum. Etiketler küçüktür ve büyüktür işaretlerinin arasına yazılarak başlar (örn. `<etiket>`) içeriği yazdıktan sonra etiketi kapatmanız gerekir. Etiketi kapatmak için küçüktür, slash, etiket, büyüktür şeklinde yazılmalı (örn. `</etiket>`) Bütün bir örnek yapmak gerekirse (örn. `<etiket>` İçerik Yazılacak Alan `</etiket>`)

Not: Bazı etiketler kapanmaya ihtiyaç duymazlar (örn. `<br>`, `<hr>`, `<meta>` vs.)

## HTML Etiketi

HTML etiketi, dosya içeriğinin HTML dilinde yazıldığını tarayıcımıza bildirir. Bu etiket, kendi altında mutlaka `<head>` ve `<body>` etiketlerini barındırmalıdır. Eğer bir HTML dökümanı oluşturmak isterseniz ilk yapacağınız iş bir `<html>` etiketi oluşturmaktır. Ardından HTML etiketi altına `<head>` ve `<body>` etiketlerini yazmalısınız.




```html
<html>
  <head></head> 
  <body></body>
</html>
 ```

 ## HEAD Etiketi

`<head>` etiketi, site ziyaretçileri tarafından görülmesi gerekmeyen kodları içerir. Bu etiket altına yazılan kodlar genellikle arama motorları ve örümcekler (Crawler veya Spider diye geçer) içindir. Head etiketi altında bütün etiketleri kullanabilmeniz mümkün değil. Kullanabileceğiniz etiketler;

- `<title>` (Bu etiketi kullanmak şarttır)
- `<meta>`
- `<style>`
- `<script>`
- `<noscript>`
- `<link>`
- `<base>`

```html
<html>
  <HEAD>
    <title> Sekmede Görülecek İsim </title>
    <meta name="Keywords" content="HTML,Kodluyoruz">
  </HEAD> 
  
  <BODY></BODY>
  
</html>
```

## BODY Etiketi

Web sayfamızda görmek istediğimiz bütün içerikleri <body> etiketi altına yazıyoruz. Anlatacağım diğer etiketleri <body> etiketi içerisine yazacağız.


```html
<html>
  <HEAD>
    <title> Sekmede Görülecek İsim </title>
    <meta name="Keywords" content="HTML,Kodluyoruz">
  </HEAD> 
  
  <BODY>
    Site İçeriği
  </BODY>
</html>
```
**Not:**
Şu ana kadar oluşturduğumuz yapıyı idelerde kısayollar ile hızlıca oluşturabiliyoruz. Ben Visual Studio Code (VSC) kullanıyorum. VSC üzerinde "! + Enter" yazarak aşağıdaki yapıyı hızlıca oluşturabilirsiniz.


`<!DOCTYPE html>` : Dökümanımızın HTML dilinde olduğunu tarayıcımıza bildiren talimattır. `<html lang="en">` : Site içeriğinin dilini belirten etiket, "en" yerine "tr" yazabilirsiniz.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

</body>
</html>
```

## H Etiketleri

**H** etiketleri başlık etiketleridir. Büyükten küçüğe sırasıyla
```html
<h1>
<h2>
<h3>
<h4>
<h5>
<h6>
```
şeklindedir.

**Not:** HTML otomatik olarak **Başlık** etiketlerinin öncesine ve sonrasına satır atlatır.

## P Etiketi

`<p>` etiketi paragraf etiketidir. Sayfa içerisinde oluşturacağımız metinleri `<p>` etiketi ile oluştururuz. Aşağıdaki örnekte hem başlık etiketi hem de paragrafa etiketini kullandım.

**Not:** HTML otomatik olarak **Paragraf** etiketinin öncesine ve sonrasına satır atlatır.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h2>Kodluyoruz</h2>
    <p>HTML Etiketleri</p>
</body>
</html>
```

## BR Etiketi

`<br>` etiketi satır atlatma etiketidir ve kapatmaya ihtiyaç duymayan etiketlerden biridir. Atlatmak istediğiniz satır sayısı kadar `<br>` etiketi kullanabilirsiniz. NOT: BR etiketinin farklı kullanımlarını görebilirsiniz. örn.(`<br>`,`<br/>`,`<br />`) Hepsi aynı işlevi yerine getirir.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h2>Kodluyoruz</h2> <br>
    <p>HTML <br> Etiketleri</p>
</body>
</html>
```

## A Etiketi

`<a>` etiketinin en önemli özelliği href özelliğidir. Bu etiket ile sayfaları linkleyebiliriz. Etiket içerisine yazılan içerik sayfa üzerinde gösterilecek içeriktir. href içine yazılan ise tıklandığında gideceği URL'dir.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <a href="https://www.kodluyoruz.org">Kodluyoruz</a>
</body>
</html>
```

## UL - OL - Li Etiketi

`<ul>` ve `<ol>` etiketleri liste oluşturma etiketleridir. Listeyi oluşturduktan sonra içeriğini oluşturmak için `<li>` etiketini kullanıyoruz.

`<ul>` = "unordered list" sırasız liste anlamına geliyor. `<ol>` = "ordered list" sıralı liste anlamına geliyor.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
   
    <ul>
        <li>HTML</li>
        <li>CSS</li>
        <li>JavaScript</li>
    </ul>
    
    <ol>
        <li>HTML</li>
        <li>CSS</li>
        <li>JavaScript</li>
    </ol>
    
</body>
</html>
## HR Etiketi

`<hr>` etiketi konusal bir geçişi temsil eder. Yazı yazarken yeni bir paragrafa başlamaya benzetebiliriz. Varsayılan olarak sayfaya yatay bir çizgi ekler ama bu özelliği değiştirilebilir. Bu etiket kapatılmaya ihtiyaç duymaz.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <p>
      HTML yani Hiper Metin İşaretleme Dili, web sayfalarında gördüğümüz iskelet
      yapısını oluşturmak için kullanılan metin işaretleme dilidir.
    </p>

    <hr>

    <p>
      CSS, HTML elementlerinin çeşitli medya araçlarında nasıl ekrana
      yansıtılacağını tanımlayan bir dildir. Tek seferde birden çok sayfa için
      kurallar belirtebilir.
    </p>

    <hr>

    <p>
      JavaScript, HTML ve web için bir programlama dilidir. Dinamik olarak HTML
      içeriğini ve özelliklerini, CSS'i değiştirebilme gibi işlemleri
      gerçekleştirebilir.
    </p>
  </body>
</html>
 ```

## STRONG ve B Etiketi

`<strong>` etiketi bir metinin arama motorlarına önemli olduğunu bildirmek için kullanılır. Kullanıldığı zaman metini kalın yapar. Eğer sadece metini kalınlaştırmak isterseniz `<b>` etiketini kullanabilirsiniz.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h2><strong> Kodluyoruz </strong></h2>
    <p><b> HTML </b> Etiketleri </p>
</body>
</html>
```

## Script Etiketi

`<script>` etiketi JavaScript kodlarını HTML içerisine yazabilmemizi sağlar.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <script>
        document.write("Kodluyoruz")
    </script>
</body>
</html>
 ```

## Button Etiketi

`<button>` etiketini buton oluşturmak için kullanırız. Buton üzerine yazmak istediğiniz içeriği etiketin içine yazmanız yeterlidir.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <button> Buton </button>
</body>
</html>
 ```

## img Etiketi

Resim eklemek için `<img>` etiketini kullanıyoruz. `<img src=”resim.jpg” alt=”açıklama yazısı” />` **src=""** kısmına eklemek istediğimiz görselin yolunu yani kaynağını yazmalıyız. Eğer görselimiz ve HTML dosyamız aynı klasörde ise görselin adını ve uzantısını yazmamız yeterlidir. **alt=""** kısmına görselin açıklamasını yazıyoruz fakat isterseniz boş bırakabilirsiniz. Bu etiket kapanmaya ihtiyaç duymaz.


## iframe Etiketi

Belge içinde belge gösterebilmemizi sağlayan etikettir. Genelde başka bir sitedeki belgeyi kendi sayfamızda göstermek için kullanırız. örn: Youtube'dan bir videoyu sayfamızda göstermek istersek `<iframe>` kodlarını sayfamıza eklememiz yeterli.(video üzerinde sağ tıklayıp yerleştirme kodunu kopyala diyerek iframe kodunu kopyalayabiliriz.)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <iframe width="1519" height="581" src="https://www.youtube.com/embed/BHPYQHnD_QA" frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen></iframe>
</body>
</html>
```

## Yorum Satırı

HTML dilinde yorum satırı `<!--` ile başlar `-->` ile biter.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <!-- Örnek Yorum Satırı -->
    
    <!-- 
        2. Örnek Yorum Satırı 
    -->   
</body>
</html>
```

Aşağıda hadi [bütün örneklerin olduğu](https://www.w3schools.com/tags/default.asp) codepen'i düzenlemekten değişiklikleri deneyimlemekten çekinme!

<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/poNgaao?height=300&amp;theme-id=dark&amp;slug-hash=poNgaao&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_poNgaao"></iframe>

---

## Başlık Etiketleri Kullanımı

Bu yazıda `<head></head>` etiketi arasına yazılan etiketlerden bahsedeceğiz.Başlık etiketlerimiz de benzer şekilde bize sayfamızla ilgili ipuçları verir ve sayfamız için ihtiyacımız olacak dış kaynakları yüklememize yardımcı olur. Hem sayfamızın düzgün ve verimli çalışması için hem de bu sayfanın tanınmasını bilinmesini hatta arama motorları tarafından fark edilmesini sağlamak için bu etiketlere ihtiyacımız var.

Öyleyse sırasıyla etiketlerimize başlayalım ve html sayfalarımızı nasıl daha bilinir ve gelişmiş hale getirebiliriz öğrenelim.

### Title Etiketi

Bu etiketimiz html dökümanlarında türkçe anlamı olan "başlık" görevini üstlenir. Bu başlık birkaç farklı yerde görülebilir. Bizim en sık karşılaştığımız şekli ise browser sekmelerinin isimleridir. Örnek olarak :
```html
<title> Kodluyoruzla Web Öğreniyorum </title>
```
Gibi bir başlık belirlediğimizde sekme isminde Kodluyoruzla Web Öğreniyorum yazdığını görürüz.

Bu etiket arasına yazdıklarımız aynı zamanda sayfayı favorilere eklerken de karşımıza çıkar.

Ayrıca arama motorları (Google, Yahoo, Bing ...) sayfamızın bu kısmına bakarak sitemizi listeler. Bu yüzden de oluşturduğumuz mükemmel web sayfalarının insanlara ulaşması için bu alanda yazdıklarımızın açıklayıcı, dikkat çekici ve 50-60 karakteri geçmeyecek şekilde ( Arama motorları genelde başlığın ilk 50-60 karakterini gösterir ) yazmamız gerekir.


### Style ve Script Etiketleri

Öncelikle style etiketinden başlayalım. `<style></style>` etiketleri arasında sayfamızı güzelleştiren, renklendiren belli özellikler tanımlayabiliyoruz. Bu kısımlarda, bir html dökümanında hangi alanın nerede ve nasıl görünmesi gerektiğini tasarlayabiliriz. Belli kuralları olan bu belirteçlere [CSS](https://www.w3schools.com/css/default.asp) diyoruz. Sayfa tasarımlarının bulunduğu bir ön döküman veya bir taslak gibi düşünebiliriz.

Burada dikkat etmemiz gereken bir konu var. HTML dökümanı işlenirken ve görüntülenirken sayfa sırayla işlendiği için her zaman sırasıyla en altta kalan stil belirlemeleri baskın gelecektir.

Bu etiketimizin global özelliklere(attribute) ek olarak alabildiği iki farklı özellik vardır. Bunlar media ve type. Çok yaygın olmadığı için kullanım detaylarına girmeyeceğim ama alabildikleri özelliklere [şuralardan](https://www.w3schools.com/tags/att_style_media.asp) bakabilirsiniz.


### Script Etiketleri

Geldik web dökümanlarının ön yüzlerini "sihirli" hale getiren etikete. Bu etiketle web sayfalarının, browser yardımıyla çalıştırabildiği kodlar yazabiliriz. Sayfamızı canlandırabilir, hareketlendirebilir her alanda değişiklik yapabiliriz. Sayfamız üzerinde hayal gücümüzle sınırlı her değişikliği yapabilmemizi sağlayan kodlar bu etiketler arasında bulunur.

`<script></script>` etiketleri ileride öğreneceğiniz sihirli bir dünyaya açılan kapıdır. Normalde HTML dökümanlarının bir programlama dili ile yazılmadığını biliyoruz. Çünkü HTML ve CSS bir programlama dili değildir. Ancak `<script></script>` tagları arasına girdiğimizde işler değişmeye başlıyor. Artık bir programlama dili olan JavaScript'in dünyasına girmiş oluyoruz. HTML dökümanlarının stilleri yerleşimleri hatta bütün dökümanın kendisini Javascript yardımıyla değiştirebilir, farklı işlemler yapabilir, farklı sayfalarla veya arka planda bir veri tabanıyla haberleşebilir oradan aldığımız bilgilerle dökümanımızı güncelleyebiliriz. Ayrıca HTML dökümanımıza yeni elemanlar ekleyip çıkartabiliriz. Dökümanlarımız üzerinde hareketli animasyonlar çalıştırabilir, her türlü değişikliği yapabiliriz.

Bu yüzden bu etiketlerin bizim gücümüzü artıran sihirli bir dünyaya açıldığını söyleyebiliriz. Şimdi bunun özelliklerine bakalım.


#### Script Tag Özellikleri

Öncelikle bu etiketlerin bize sayfa üzerinde büyük bir güç verdiğinden bahsetmiştik.Bu yüzden bu tagın özelliklerinden bahsederken sayfanın işlenişi, browser tarafında nasıl işlendiğini ve yanlış bir kullanımın nelere sebep olabileceğini iyi anlamamız gerekiyor. Eğer script etiketini kullanırken herhangi bir özellik eklemezsek browser sırası geldiğinde doğrudan işlenir. Ve bu kısım işlenmeden sayfa yüklenmeye devam etmez. Bu noktada da async özelliğimiz devreye giriyor. Eğer sayfanın yüklenmeye devam ederken eşzamanlı olarak bu etiketlerle belirlediğimiz scriptlerin de yüklenmesini ve hazırlanmasını istiyorsak, yani bu kısmın asenkron çalışmasını istiyorsak etiketimize bu özelliği ekliyoruz. Herhangi bir değer girmemize gerek yok şu şekilde kullanabiliriz :
```html
<script src="myJavascript.js" async></script>
```

Eğer bu etiketin sayfa yüklendikten sonra yüklenip çalıştırılmasını istiyorsak o zaman async özelliğinin yanına defer özelliğini de eklememiz gerekiyor. Ancak bu iki özellik de yalnızca sayfa harici kaynaktan yani bu HTML içinde yazmadığımız javascripti yüklerken kullanabileceğimiz özellikler. Buna da dikkat etmemiz gerekiyor.

Bu etiketin sihirli dünyasından bahsetmiştik. Ancak bahsetmediğimiz nokta her sihirli dünyada olduğu gibi burada da kötü büyücülerin, kötü insanların olduğudur. Bu yüzden sayfamız üzerinde bu kadar güce sahip bir alanın doğru şekilde korunması ve kullanılması hayati önem taşıyor. İşte bu amaçla da karşımıza iki özellik çıkıyor.

Bu özelliklerden birincisi crossorigin. Browserlar, istek sahteciliği gibi güvenlik sorunlarıyla aktif şekilde mücadele etmeye çalışıyor. Bu yüzden bir kaynaktaki dökümanın bir diğer kaynaktaki (farklı domain) dökümanlara erişmesinde biraz hassas davranıyorlar. Bu konuya cross origin resource sharing deniyor kısaca CORS diyebiliriz. İşte bu etiketimiz de farklı kaynaklardaki, farklı domainlerdeki scriptleri yüklememiz için bize yardımcı oluyor. Eğer bir kaynaktan(aynı domain dahil) bir şey yüklemek için belli bilgileri( Çerezlerimiz olabilir, HTTP basit giriş bilgileri olabilir) göndermemiz gerekiyorsa bu özelliğin değerini crossorigin = "use-credentials" olarak belirlemeliyiz. Eğer anonim şekilde erişmemiz gerekiyorsa yani herhangi bir bilgiye ihtiyaç yoksa crossorigin="anonymous" olarak kullanacağız.

Bir diğer özelliğimiz ise integrity özelliğidir. Integrity türkçeye bütünlük, doğruluk, dürüstlük şeklinde çevirilebilir. Webin gelişmesiyle birlikte bir HTML sayfasına yüklenen kaynaklar çoğaldı. Özellikle tekrar eden ihtiyaçlar için zaman geçtikçe en verimli çözümler üretilmeye ve kullanılmaya başlandı. Bu çözümlerin kullanılması yaygınlaştıkça belli riskler de ortaya çıkmaya başladı. Örnek olarak HTML sayfamıza ekleyeceğimiz bir dış script bir güvenlik açığıyla karşı karşıya kaldığında o scripti kullanan bütün sayfalar aynı anda etkilenmiş olacak. Bunun bir örneği yakın zamanda birçok firmayı etkileyen Gigya servisinde olmuştu. Bu servisi kullanan sitelerin sayfalarına ekledikleri harici bir gigya servisi bir saldırıya maruz kalmıştı ve o servisi kullanan binlerce sitede bu açıktan etkilenmişti. İşte CDN dediğimiz bu gibi hazır scriptleri eklediğimiz durumlarda bir doğrulama yöntemine ihtiyaç duyuyoruz. Yani browser bir şekilde, sayfamızı etkileyecek kodların bizim istediğimiz eklediğimiz kodlar olduğunu doğrulaması gerekiyor. Bu noktada da integrity özelliği devreye giriyor. Sayfamızda kullanacağımız hazır kodların bir imzasını bu özelliğe değer olarak ekliyoruz. Bu imza doğrudan kodun kendisinden oluşturulur ve belli bir karakter uzunluğundadır. Ayrıca kodda bir harf bile değişecek olsa imza tutmayacaktır. Bu sayede eğer kodda zararlı/zararsız herhangi bir değişiklik olursa browser imzalar uyuşmayacağı için kodları sayfamıza yüklemeyecektir.

**Örnek olarak şu şekilde kullanabiliriz :**

```html
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js" integrity="sha384-0mSbJDEHialfmuBBQP6A4Qrprq5OVfW37PRR3j5ELqxss1yVqOtnepnHVP9aJ7xS" crossorigin="anonymous"></script>
```

Bir diğer etiketimiz de refreferrerpolicy. Bu etiket de scripti yükleyeceğimiz zaman, alacağımız kaynağa atacağımız verileri eklemek için kullınılır. Detaylı kullanımına buradan [bakabilirsiniz :](https://www.w3schools.com/tags/att_script_referrepolicy.asp) Bu da crossorigin gibi kaynak paylaşımı maksadıyla kullanılan özelliklerdendir.


HTML sayfamızı oluştururken sayfa içerisindeki kod ne kadar uzun olursa okunması, yazılması ve incelenmesi o kadar zor olur. Bu yüzden kodları farklı sayfalara bölüp kullanmak hem daha kullanışlı hem de daha verimli olur. İşte bu amaçla farklı sayfalardaki scriptleri yükleyebilmek için de script etiketini kullanabiliriz. Bu amaçla script etiketinin src özelliğini kullanırız. Bu özellikle hem kendi dosya sistemimizde hem de internet üzerinde herhangi bir adreste bulunan kodları kendi sayfamıza ekleyebiliriz.

Örnek olarak kendi dosya sistemimizde, html dökümanımızla aynı dizinde bulunan bir script dosyasını çağırmak için:

```html
<script src="myJavascript.js"></script>
```

Veya bir web sayfasındaki başka bir scripti çağırmak için :

```html
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js" integrity="sha384-0mSbJDEHialfmuBBQP6A4Qrprq5OVfW37PRR3j5ELqxss1yVqOtnepnHVP9aJ7xS" crossorigin="anonymous"></script>
```

Son olarak da bu etiketle kullanabileceğimiz type özelliğimiz, yüklenecek dosyanın içeriğinin, browser tarafından nasıl yorumlanması gerektiğini belirtir. Örnek olarak javascript dosyası yüklemek için yüklenecek kodların javascript kodunu belirtmek için şöyle yazabiliriz :

```html
<script type="application/javascript">
document.getElementById("someTestDiv").innerHTML = "This code runs as js";
</script>
```

*Ya da Ecmascript için :*

```html
<script type="application/ecmascript">
document.getElementById("someTestDiv").innerHTML = "This code runs as js";
</script>
```

### Link Etiketi

Script etiketini anlatırken bir HTML dökümanında yüklenecek kodların bölünmesinin bir çok kolaylık sağlayacağından bahsetmiştik. İşte `<link></link>` etiketi de script etiketinin src özelliği ile kullanılması gibi link etiketini de farklı kaynaklardan farklı dosyaları HTML dökümanımıza dahil etmek için kullanabiliriz. Bu etiket dökümanımızda bulunmayan dış kaynaklarla dökümanımız arasındaki ilişki kurmak için kullanılır.

Bu etikette de crossorigin özelliği mevcuttur.

Bu etikette ilişki kurmak istediğimiz dış kaynağı href özelliği ile veriyoruz. Bu özelliğin açılımı Hypertext REFerence şeklindedir. Örnek olarak bir CSS sayfasını HTML dökümanımız ile ilişkilendirmek için şu kodu kullanabiliriz :

```html
<link rel="stylesheet" href="styles.css">
```

Bu etiketin önemli özelliklerinden birisi de rel özelliğidir. Bu özellik dış kaynaktaki dosyayı kendi HTML dökümanımıza ne şekilde ilişkilendirmek istediğimizi belirttiğimiz kısımdır. En çok kullanılan değerleri "stylesheet" ve "icon" dur. Stylesheet eklemek istediğimiz dosyanın bir stil dosyası olduğunu söyler. Böylece browser oradaki komutları HTML'imizi şekillendirmede ve değiştirmede kullanır.

Yukarıda HTML dökümanımızın stil ve script dosyalarını ayrı ayrı yazmanın faydalarından bahsetmiştik. Script etiketi ile bu javascript dosyalarını ekleyebiliyorduk ancak CSS yani stil dosyalarını eklemenin yöntemini öğrenmemiştik. İşte bu link etiketi ve rel özelliği yardımıyla istediğimiz stil dosyasını da `<head></head>` etiketlerinin arasında ekleyerek web sayfamızı daha renkli ve eğlenceli hale getirebiliriz.

`<title></title>` etiketi yardımıyla sekmelerde görünecek, HTML dökümanımızın başlık ismini belirlemiştik. Ancak şu an bu yazının olduğu sekmeye bakarsanız başlığın yanında bir de küçük bir logo/ikon göreceksiniz. İşte bu ikonlar eklemek için de rel = "icon" kullanıyoruz. Bulunduğumuz dizinde **.ico** uzantılı bir **favicon.ico** dosyamız varsa bu dosyayı sekmelerde ismin yanında ikon olarak göstermek üzere şöyle bir kod kullanabiliriz :

```html
<link rel="icon" href="/favicon.ico" type="image/x-icon">

```

Son olarak link etiketi de type özelliği kullanır. Bu özellikle de ilişkilendirdiğimiz dosyanın tipini vermiş oluyoruz. Yaygın kullanılan değerleri stil dosyaları için `type = "text/css"` şeklinde, ikonlar için de `type="image/x-icon"` şeklindedir.

Link etiketi global özellikleri de destekler. Diğer detaylı özellikleri için de [buraya](https://www.w3schools.com/tags/tag_link.asp) bakabilirsiniz.


### Meta Etiketi

Tanıtacağımız son etiket ise meta etiketi. Meta veriler bilgisayar bilimleri dünyasında genellikle verinin verisi anlamında kullanılır. Yani bir veriyle ilgili bilgiler meta bilgiler olarak tanımlanır. İşte HTML dökümanımızla ilgili verilerin olduğu etiketler de meta etiketleridir. Burada vereceğimiz bilgiler sitemizi arama motorlarına, sosyal medyaya ve diğer sitelere tanıtmak ve dökümanımızla ilgili bilgiler vermek için kullanılacak veriler olacak.

Sadece 4 farklı özelliği olan `<meta></meta>` etiketi dökümanımızla ilgili birçok bilgiyi barındıran farklı kullanım şekillerine sahip. Bu kullanımlar sayfamızla ilgili önemli bilgiler içerdiği için ayrı ayrı inceleyeceğiz.

Dünyada farklı farklı diller ve farklı alfabeler mevcut. Örnek olarak latin alfabesi, arap alfabesi, çin alfabesi, elf alfabesi vs vs. Ancak hepsinde farklı karakterler olduğu için browserin bu karakterli görüntüleyebilmek için doğru şekilde çözümlemesi gerekir. İşte HTML dökümanımızdaki bu karakterlerin çözümlenme biçimlerini belirttiğimiz `<meta>` etiketi özelliğimiz charset özelliğidir. Bizim latin alfabesi için verilen charset kodu UTF-8 dir.

```html
<meta charset="UTF-8">
```
Bir diğer önemli özelliğimiz ise http-equiv'dir. Browserlar farklı sunuculara istek atarlarken belli bilgileri karşı tarafa gönderirler. İşte bu isteklerin arasında isteğin detaylarıyla ve yöntemiyle ilgili bilgilerin olduğu header'lar bulunur. Biz de dökümanımızda o dökümana ulaşan birisinin browser'inde header alanında bir bilgi tutmak istiyorsak bu meta etiketi özelliğini kullanabiliriz. Örnek olarak charset ile belirttiğimiz özellik HTML5 ile gelmiştir. Daha önceki versiyonlarda ise şu şekilde bir kullanım vardır :

```html
<meta http-equiv="Content-type" content="text/html" charset="UTF-8">
```

Ayrıca refresh başlığını(header) bu meta yardımıyla belirleyerek sayfamızın belli sürede bir yenilenmesini veya belli bir süre sonra başka bir sayfaya yönlendirilmesini sağlayabiliriz.

```html
<meta http-equiv="refresh" content="10;URL=kodluyoruz.html">
```

Yukarıdaki kodda sayfa yüklendikten 10 saniye sonra URL ile verdiğimiz değer olan kodluyoruz.html'ye yönlendirilecek.

Burada kullandığımız diğer etiket de content etiketidir. Bu da meta olarak verdiğimiz bilgilerin içeriğini tanımlamamızı sağlar.

Son özelliğimiz de name özelliğimizdir. Bu da meta bilgi olarak vereceğimiz bilginin tanımlayıcısıdır diyebiliriz. Örnek olarak sayfamızda en çok geçen harfin ne olduğunu belirteceğimiz bir meta bilgisi yazmak isteyelim:

```html
<meta name="enCokGecenHarf" content="a">
```

Bu şekilde istediğimiz meta bilgiyi sayfamızın başlık etiketleri arasında kullanabiliriz.

Buraya kadar meta etiketini öğrendik peki sosyal medyalar ve arama motorları sitemizle ilgili bilgileri nasıl bu meta verilerden alıyor? Bu sorunun cevabı da yaygın kullanılan meta etiketleri kalıplarında bulunuyor. Örnek olarak github'da sağ tıklayıp sayfa kaynağını görüntüle dediğimizde karşımıza bir çok meta etiketi çıkıyor :

```html
<meta property="og:url" content="https://github.com">
<meta property="og:site_name" content="GitHub">
<meta property="og:title" content="Build software better, together">
<meta property="og:description" content="GitHub is where people build software. More than 50 million people use GitHub to discover, fork, and contribute to over 100 million projects.">
<meta property="og:image" content="https://github.githubassets.com/images/modules/open_graph/github-logo.png">
<meta property="og:image:type" content="image/png">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="1200">
<meta property="og:image" content="https://github.githubassets.com/images/modules/open_graph/github-mark.png">
<meta property="og:image:type" content="image/png">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="620">
<meta property="og:image" content="https://github.githubassets.com/images/modules/open_graph/github-octocat.png">
<meta property="og:image:type" content="image/png">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="620">

<meta property="twitter:site" content="github">
<meta property="twitter:creator" content="github">
<meta property="twitter:card" content="summary_large_image">
<meta property="twitter:title" content="GitHub">
<meta property="twitter:description" content="GitHub is where people build software. More than 50 million people use GitHub to discover, fork, and contribute to over 100 million projects.">
<meta property="twitter:image:src" content="https://github.githubassets.com/images/modules/open_graph/github-logo.png">
<meta property="twitter:image:width" content="1200">
<meta property="twitter:image:height" content="1200">
```

İşte burada kullanılan meta taglar, facebook ve twitter paylaşımlarımızda bir url paylaşmak istediğimizde karşımıza çıkıyor. Sosyal medyada bir url paylaşmak istediğimizde url'yi kopyaladıktan sonra bir kart görürüz. Bu kartta bir başlık bir resim ve kısa bir açıklama bulunur. İşte o bilgiler bu meta verilerden alınır.

Arama motorları bizi meta verilerinde verilen "keywords" lere göre sıralamaya alır :

```html
<meta name="keywords" content="Kodluyoruz,programlama,web">
```

Ayrıca arama motorlarında sayfa başlığının altındaki açıklamalarda da yine bu meta verilerine öncelik verilir :

```html
<meta name="description" content="Kodluyoruzla web öğrenmeye hazır mısınız?">
```

Bazı arama sonuçlarında yazar adı görürsünüz. Bu kısım da yine meta etiketinin marifetidir:

```html
<meta name="author" content="Kodluyoruz">
```

Meta etiketiyle söyleyeceğimiz son şey de viewport konusu. Akıllı telefonlarla birlikte geliştiriciler artık farklı cihazlara, farklı cihaz ekranlarında düzgün görünen kodlar yazmaya çalışıyor. Her ekranın genişliği boyutları farklı olduğu için tek bir ekran türüne göre tasarım ve kodlama yapmak da bu sorunu çözmüyor. Bu yüzden farklı cihazlarda da iyi görünen siteler yapmak için temel görünen alanı, bu alanın genişliğini vs tanımlamamız gerekiyor. İşte viewport burada yardımımıza koşuyor.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Burada genişliğin cihaz genişliğinde olduğunu ve zoom oranının 1.0 olacağını tarayıcıya belirmiş oluyoruz. Böylece mobilde masaüstü görünümü gibi bir görünüm değil olması gerektiği gibi düzgün bir görüntü elde ediyoruz. Detaylı bilgi için [şurayı](https://fatihhayrioglu.com/meta-viewport-etiketi/) inceleyebilirsiniz.


Şimdiye kadar başlık etiketlerini, başlık etiketlerinin özelliklerini ve genel kullanım alanlarını öğrenmiş olduk.

**Şimdi sıra kısa bir alıştırma yapalım. Lütfen soruları cavaplarken kendinize biraz zaman tanıyın ve yukarıdaki bilgilere göre hareket edin.**

**Bu bilgiler :**

→ Web sitesinde en çok kullanılan baskın renk nedir? (dominantColor) → Sayfanın başlığı nedir? (title) → Sayfanın açıklaması/konusu ne üzerinedir? (description)

Bu verilerin sayfadan kolayca alınabilmesi için hangi etiketler hangi özelliklerle nasıl kullanılmalı?

**Cevaplar :**

1. CDN (Content Delivery Network) yardımıyla bootstrap stil ve js dosyalarını sayfamıza eklemek istiyoruz. Bunun için google'da bootstrap cdn diye arattığımızda karşımıza yukarı öğrendiğimiz link ve script etiketleriyle bootstrapi nasıl ekleyebileceğimiz çıkıyor. link etiketimizde integrity özelliğimizle imza kontrolü yaptığımıza crossorigin özelliğimizi kullandığımıza ve ilişkilendirme(rel/relation) türünün stylesheet olduğuna dikkat edin. Script etiketimizde de aynı özellikler bulunmakta :

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" crossorigin="anonymous">
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js" integrity="sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV" crossorigin="anonymous"></script>
```







2. Bu tip sayfayla ilgili veriler için `<meta>` etiketini kullandığımızdan bahsetmiştik. Ayrıca başlık için de `<title>` etiketini kullandığımızı söylemiştik. Şimdi bu etiketlerin doğru kullanımlarına bakalım :

```html
<title>Kodluyoruz HTML</title>
<meta name="dominantColor" content="red">
<meta name="description" content="Kodluyoruz ile webe giris">
```

####Kaynaklar

- https://clutch.co/seo-firms/resources/meta-tags-that-improve-seo
- https://www.geeksforgeeks.org/most-commonly-used-tags-in-html/
- https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML
- https://www.w3schools.com/tags/tag_script.asp
- https://www.w3schools.com/tags/tag_head.asp
- https://www.w3docs.com/learn-html-html-head-tag.html
- https://help.ahrefs.com/en/articles/2433739-what-is-meta-refresh-redirect-and-why-is-it-considered-a-critical-issue
- https://en.wikipedia.org/wiki/Meta_refresh
- http://www.yunusbassahan.com/blog/genel/arama-motorlari-ve-sosyal-medya-servisleri-icin-meta-tag-ler.html
- https://stackoverflow.com/questions/6535405/what-is-the-attribute-property-ogtitle-inside-meta-tag
- https://www.w3schools.com/tags/tag_meta.asp
- https://gist.github.com/lancejpollard/1978404
- https://www.w3schools.com/tags/tag_link.asp
- https://www.w3schools.com/tags/att_link_rel.asp
- https://www.w3schools.com/tags/att_link_type.asp
- https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link
- https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types
- https://www.w3schools.com/tags/att_meta_charset.asp
- https://www.w3schools.com/tags/att_meta_name.asp
- https://stackoverflow.com/questions/2359866/html-set-image-on-browser-tab
- https://stackoverflow.com/questions/34429024/what-is-the-purpose-of-the-integrity-attribute-in-html
- https://www.w3schools.com/tags/att_meta_http_equiv.asp


## VS Code ile Çalışmak ve İlk HTML Sayfasının Web Tarayıcıda Gösterilmesi

Doğru olarak yazdığımız index.html dosyamızda ilk html etiketimizi oluşturalım. Başlık etiketi için kullanılan h1 etiketi ile alıştırmamızı yapalım.

<h1> Buraya İstediğimiz Başlığı Yazabiliriz </h1>
h1 etiketleri arasına istediğimiz bir başlığı yazabiliriz. Aşağıda verilen örnekte h1 etiketlerimiz arasına "Kodluyoruz" yazılmıştır.

![KodluyoruzH1](https://github.com/Kodluyoruz/taskforce/raw/main/html/vs-code-ile-calismak-ve-i%CC%87lk-html-sayfasinin-web-tarayicida-gosterilmesi/figures/vscode-kodluyoruz.JPG)

Oluşturduğumuz dosyamızı çalıştırmadan önce kaydetmemiz gerekmektedir. Eğer bir değişiklik yapmış ve dosyamızı kaydetmemişsek yazdığımız dosyanın üzerinde bir nokta ve en solda Explorer'da kaç dosyanın kayıtlı olmadığı gösteren bir ikon göreceğiz.

Oluşturduğumuz index dosyamızı File > Save ile veya CTRL+S ile kaydettikten sonra ilk html etiketimizi web browserda görüntüleyebilmek için ana klasörümüzün altında oluşturduğumuz index dosyamızı açıyoruz.

ve ilk HTML sayfamız tarayıcımızda gözüküyor!

![İlkHTMLWebSayfamız](https://github.com/Kodluyoruz/taskforce/raw/main/html/vs-code-ile-calismak-ve-i%CC%87lk-html-sayfasinin-web-tarayicida-gosterilmesi/figures/vscode-ilk-html.JPG)


## Açıklama Satırları Oluşturmak


#### Açıklama satırı eklemeli miyim?
Evet, eklemelisin. Çünkü açıklama satırlarını kodunuzu 2 ay sonra tekrar gözden geçirmek için açtığınızda neyin nerede olduğunu anlamanız açısından fayda sağlayacaktır. Sadece kendimiz ile de bitmiyor. Projeyi farklı bir kişiye devrettiğinizde veya paylaştığımızda yazdığınız yorum satırlarının başka biri tarafından okunması karşı taraf için de fayda sağlayacaktır.

#### Açıklama satırı nasıl oluşturulur?


Açıklama satırını HTML kodumuzda `<!–` ile başlatıp `–>` ile bitecek şekilde yazabiliyoruz. "ile başlatıp" yazan alana yorumlarımızı ekleyebiliyoruz.

**Ekstra:**
- Hızlı yorum satırı (Ctrl+Shift+A)
- Cümleyi yorum satırına çevirme (Ctrl+K+C)

#### Açıklama satırı web sayfasında görünür mü?

Hayır, kullanıcılar web sayfanızda açıklama satırlarını görmezler. Ayrıca açıklama satırları web tarayıcıları tarafından herhangi bir işleme tabi tutulmazlar. Fakat kullanıcı sayfanızda sağ tıklayıp kaynağı görüntüle dediğinde açıklama satırlarınızı görebilir.


##### Hadi örneklendirelim!
Aşağıdaki örnekte birden fazla HTML elementlerini tanımlayıp aralara açıklama satırları ekliyoruz. Böylelikle HTML kodumuz daha okunabilir bir hal alabiliyor. Hangi elementin nerede kapatıldığını veya açıklama satırına yazacağımız o kodun işlevi ile daha açıklayıcı bir hale getiriyoruz. Aşağıdaki örnekte index.html dosyasının body elementi içerisine yazacağımız kodları paylaşıyorum.


```html
<!--nav element başlangıç-->
<nav>
    <ul>
        <li>Anasayfa</li>
        <li>Kurumsal</li>
        <li>İletişim</li>
    </ul>
</nav>
<!--nav element bitiş-->
 
<!--section element başlangıç-->
<section>
    <p>Lorem Ipsum, dizgi ve baskı endüstrisinde kullanılan mıgır metinlerdir.</p>
</section>
<!--section element bitiş-->
 
<!--footer element başlangıç-->
<footer>
    Copyright © 2021
</footer>
<!--footer element bitiş-->
```

**Aşağıda codepen kullanarak pratik yapabilirsin!**

<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/rNWxJbj?height=300&amp;theme-id=dark&amp;slug-hash=rNWxJbj&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_rNWxJbj"></iframe>

---


## Başlıklar ve Paragraflarla Çalışmak

### HTML Paragrafları
HTML'de enter işlevi yoktur. Bu yüzden eğer farklı farklı paragraflar oluşturmak istiyorsak <p> etiketini kullanırız. Bir paragraf her zaman yeni bir satırda başlar ve tarayıcılar bir paragrafın önüne ve arkasına otomatik olarak biraz beyaz boşluk (kenar boşluğu) ekler.

```html
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

### HTML Başlıklar

HTML’de en önemli kısım başlıklardır. `<h1>` Etiketi yazıların başlık şeklinde yazılması için kullanılır. Altı tane başlık çeşidi vardır. Bu başlık özellikleri `<h1>` den `<h6>` ya kadar kodlanmıştır. `<h1>` Etiketi en büyük fontu ve en çok önemi bildirirken `<h6>` ya doğru azalma göstermektedir.

```html
<h1>H1 Başlık</h1>
<h2>H2 Başlık</h2>
<h3>H3 Başlık</h3>
<h4>H4 Başlık</h4>
<h5>H5 Başlık</h5>
<h6>H6 Başlık</h6>
```

### HTML Görünümü
![H1-H6HTMLGÖRÜNÜMÜ](https://user-images.githubusercontent.com/74019386/103456246-57e91380-4d05-11eb-8bc3-0c6566057f58.PNG)

Başlıklar [HTML](https://html.com/paragraphs/) Dökümanlar’da büyük önem arz eder. Arama motorları, web sayfalarınızın yapısını ve içeriğini indekslemek için başlıkları kullanır. Kullanıcılar genellikle başlıkları ile bir sayfayı gözden kaçırırlar. Belge yapısını göstermek için başlıkları kullanmak önemlidir. `<h1>` Başlıklar ana başlıklar için kullanılmalı, ardından başlıklar takip edilmeli `<h3>`, biraz daha az önemli `<h4>` vb.

<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/poNgLYW?height=300&amp;theme-id=dark&amp;slug-hash=poNgLYW&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_poNgLYW"></iframe>

---

# Ödev 1

## İlk Web Sayfamızı Oluşturmak

Sizlerden istediğimiz çok basit bir şekilde öğrendiklerinizle bir web sayfası tasarlamanız.

- Siteyi açtığımızda adınız ve soyadınızı başlık şeklinde göstermeniz gerekiyor.
- Ad-Soyadın altında alt başlık olarak Hakkımda yazmalıdır.
- Altına paragraf içerisinde neler yaptığınızı ve nelerden hoşlandığınızı yazabilirsiniz.
- Web sitenizi kaydederken dosya adı olarak 'index.html' seçmeniz gerekmektedir.
- Yazdığınız kodları açıklayan yorum satırları eklemeyi unutmayın.

![Ödev1HTML](https://github.com/Kodluyoruz/taskforce/raw/main/html/odev1/figures/firstwebpage.png)

---

## [Listeler](https://www.geeksforgeeks.org/html-li-tag/) ve Diğer Özellikler

### Listelerle Çalışmak

#### Listeleme Etiketleri

Listeleri iki ana başlık altında listeleyebiliriz;

1. Sıralı Listeler
2. Sırasız Listeler

##### Sıralı Listeler

Sıralı listeler ardışık liste numaraları vermek için kullanılır. Sıralı listelerden yararlanmak için `<ol>` etiketi kullanılır.

```html
 <p> Gerçek <b>tereyağı</b> nasıl anlaşılır ?</p>
    <ol>
        <li>Oda sıcaklığında tamamen erimez</li>
        <li>Suyun içinde tek parça halinde çözünür</li>
        <li>Tereyağı rengi sarı yada beyaz olabilir</li>
    </ol>
```

**Ekran çıktısı:**
![olEkranÇıktısı](https://github.com/Kodluyoruz/taskforce/raw/main/html/listelerle-calismak/figures/s%C4%B1ra.PNG)

şeklinde olur.

Liste başındaki sıralandırmayı rakamdan başka roma rakamı veya alfabetik şeklinde de yapabiliriz. Bunun için type özelliğini kullanmamız gerekir.

```html
<ol type="I">
  <li>Javascript</li>
  <li>C#</li>
  <li>Php</li>
</ol>
```
**Ekran çıktısı:**

![olTypeEkranÇıktısı](https://github.com/Kodluyoruz/taskforce/raw/main/html/listelerle-calismak/figures/siralama.png)

```html
<ol type="A">
  <li>Javascript</li>
  <li>C#</li>
  <li>Php</li>
</ol>
```
**Ekran çıktısı:**
![olType2EkranÇıktısı](https://github.com/Kodluyoruz/taskforce/raw/main/html/listelerle-calismak/figures/alfabetik.PNG)

#### Sırasız Listeler

**Sırasız listeler** numaralandırma olmadan oluşturduğumuz listeleredir. Her bir liste elemanı bir satırı kaplayacak şekilde yani blok etiket şeklinde oluşturulur

```html
<ul>
  <li>Çay</li>
  <li>Türk Kahvesi</li>
  <li>Süt</li>
</ul> 
```
**Ekran çıktısı:**
- Çay
- Türk Kahvesi
- Süt

şeklinde olur. Liste elemanlarının başındaki içi dolu daireyi değiştirebilir veya silebiliriz.

** Silmek İçin: **
```html
<ul style="list-style-type:none">
  <li>Çay</li>
  <li>Türk Kahvesi</li>
  <li>Süt</li>
</ul>
```
**Ekran çıktısı:**
Çay
Türk Kahvesi
Süt

şeklinde olur. Liste başındaki içi dolu daireyi değiştirmek için ise disc, square, circle değerlerini kullanabiliriz.

```html
<ul style="list-style-type:square">
  <li>Telefon</li>
  <li>Bilgisayar</li>
  <li>Yazıcı</li>
</ul>
```

**Ekran çıktısı:**
![ListeBaşıElemanınıKareYapmak](https://github.com/Kodluyoruz/taskforce/raw/main/html/listelerle-calismak/figures/kare.PNG)


<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/ExNPLPr?height=300&amp;theme-id=dark&amp;slug-hash=ExNPLPr&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_ExNPLPr"></iframe>

---


### Emmet ile Daha Hızlı HTML Yapıları Oluşturmak
Emmet web geliştiricilerinin sıklıkla zamandan tasarruf etmek ve daha hızlı kod yazmak için kullandığı bir eklentidir. Emmet’in temel mantığı, yazılımcıya kodlama yaparken zaman kazandırmasıdır. Örneğin hepimiz bir html dosyasının iskeletini biliriz:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
</body>
</html>
```

Emmet sayesinde çok daha hızlı bir biçimde `!` + `Tab` kullanarak bu yapıyı oluşturabilirsiniz. Bunu tek tek yazmaktansa iki tuşa basarak yapmak çok güzel değil mi?

![EasyHTMLw/Emmet](https://camo.githubusercontent.com/2b6b8cc6da640800e1cb752bce4fbb8ec4d96ec3988d09ac9a7c5a736f35b49e/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f3836352f302a74494c593447596a427670466f355a782e676966)

Anlayacağınız üzere Emmet bazı kısa yollarla basit bir biçimde HTML ve CSS kodu yazmamıza yardımcı olur. Aynı kodu tekrar tekrar yazmanızı engellerken üretkenliğinizi de arttırmış olur. Emmet neredeyse tüm text editörlerinde mevcuttur, bu yüzden onu yüklemenize gerek yoktur. Ama herhangi bir nedenden IDE’nizde mevcut değilse [bu sayfadan](https://emmet.io/download/) yükleyebilirsiniz.


### [Emmet](https://docs.emmet.io/cheat-sheet/)’deki Kısa Yollara Gelecek Olursak...

Emmette kullandığımız bazı kısa yollar var, şimdi bunları örnekleriyle tek tek inceleyelim.

1 -) `>` ifadesini kullanarak kardeş element oluşturuyoruz.

Örneğin şekildeki, gibi `ul` tagı içerisinde `li` tagı oluşturmak istiyorsunuz. Bunun için yapmanız gereken tek şey `ul>li` yazarak Tab’a basmak.
```html
<ul>
  <li></li> 
</ul>
```
Bu işlemi yaptıktan sonra ul tagına eklemek istediğimiz bir kardeş eleman kalmayınca ise ^ ifadesini kullanarak ul tagı dışına çıkıp yeni taglar oluşturabiliriz.

Örneğin `ul` tagı içinde `li` tagı oluşturduktan sonra `ul` tagı dışında bir `p` tagı eklemek istiyorum. Bunun için `ul>li^p` yazarak taba basabilirim.
```html
<ul>
    <li></li> 
</ul>
<p><p/>
```

2 -) Peki ya bu ul tagı içerisine birden fazla li oluşturmak istiyorsam, ne yapmalıyım?

Bunun için * ifadesini kullanırız. ul>li*3 yaparak ul tagı içerisinde üç adet li tagı oluşturabilirsiniz.
```html
<ul>
  <li></li> 
  <li></li> 
  <li></li> 
</ul>
```

3 -) Bunu yerine benzer biçimde kardeş eleman-tag eklemek için `+` ifadesi de kullanılabilirdi: `ul>li+li+li`

4 -) Tag eklerken onlara class özelliği vermek için de `.` ifadesini kullanırız.

Örneğin `ul.class1>li.class2` yazılarak tab tuşuna basıldığında:
```html
<ul class="class1">
    <li class="class2"></li>
</ul>
```
Bu şekilde bir kod oluşur. Aynı şekilde `ul.class1>li.class2*3` denerek bir yerine üç adet class2 sınıfından `li` tagı oluşturulabilirdi.

5 -) Bir id özelliği eklemek için ise `#` ifadesini kullanırız. Yeni bir örnekle id özelliği eklemeyi görelim. `ul#id1>li#id2` diyerek aşağıda gördüğünüz kodu oluşturabiliriz.

```html
<ul id="id1">
    <li id="id2"></li>
</ul>
```
6 -) Burada `+` ve `*` ifadesinin farkını da daha kolay anlayabiliriz.

Örneğin `ul` tagının içine aynı id’ye sahip 3 adet `li` eklemek istiyorsam * ifadesi kullanılabilir.

Fakat amacım farklı `id`’lere sahip üç adet `li` tagı oluşturmaksa `ul>li#id1+li#id2+li#id3` yapılır.

7 -) Peki otomatik artış sağlayan değerleri tek tek yazmak amacımız zaman tasarrufu iken ne kadar mantıklı?

Emmet bunun için de bir kısa yola sahip :`$` ifadesi. Yani yukarda görmüş olduğunuz `ul>li#id1+li#id2+li#id3` şeklinde yazdığımız kod bloğunu çok daha basit bir biçimde `ul>li#idNo$*3` diyerek yazabiliriz.

Böylece otomatik olarak `idNo1`, `idNo2` ve `idNo3` idlerine sahip üç adet `li` tagımız olur.
```html
<ul>
  <li id="idNo1"></li>
  <li id="idNo2"></li>
  <li id="idNo3"></li>
</ul>
```

8 -) Sırada oluşturulan tagların içine text yazılması var:

Textlerimizi `{}` ifadesinin içine yazmamız yeterli: `p{Emmet ile tag içine text yazma}`
```html
<p>Emmet ile tag içine text yazma</p>
```

9 -) Bir diğer emmet kısa yolunu ise kodumuzda içerik olmadığı zamanlarda kullandığımız anlamsız yazıları yani **“lorem ipsum”ları** oluşturmak için kullanıyoruz.

Örneğin bir paragraf oluşturacaksınız ve bu paragrafın henüz bi içeriği yok fakat boş durmasındansa oraya metin geleceğini belirtmek istiyorsunuz veya metin geldiğinde nasıl görüneceğini görmek istiyorsunuz. Anlamsız harfler veya zaman gerektiren rastgele cümleler oluşturmak yerine bu kısayolu kullanabilirsiniz : `p>lorem` Taba bastığınızda aşağıdaki gibi bir çıktı alacaksınız.

```html
<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit.Facere dolore sint ea? Molestiae ratione ullam, illo commodi ipsum soluta mollitia itaque,maiores maxime natus reiciendis architecto. Quaerat culpa beatae dicta.</p>
```

10 -) Bu kadar uzun bir lorem yazısı istemiyorsanız yapmanız gereken tek şey `lorem` yazdıktan sonra yanına kaç kelimeli bir lorem oluşturmak istediğinizi eklemek.

**Örneğin 5 kelimeli bir lorem yazısı istiyorsunuz.** Bunun için `p>lorem5` yazmanız yeterli.
```html
<p>Lorem ipsum dolor sit amet.</p>
```

11 -) Son olarak Emmet’in bir özelliğinden bahsedeceğim. `li.className` yazıp Tab’a bastığımızda ne oluşmasını bekleriz? **Evet** `className` class’ına ait bir `li` tagı oluşmasını. peki herhangi bir tag koymaksızın sadece `.className` yazdıktan sonra Tab’a basarsak ne olur?

Cevap:
```html
<div class="className"></div>
```
Gördüğünüz gibi bir `div` oluşturdu. Emmet’e bir tag vermeksizin `.` veya `#` ifadelerini kullandığımızda bunun `div` tagı olduğunu biliyor.



Ama biz bunu ul tagı içinde denersek tepkisi ne olur? **Hadi deneyelim!:**
```html
<ul>
  <li class="className"></li>
</ul>
```
Gördüğünüz gibi `ul>.className` yazıp Tab’a bastığımızda ise bunun `li` elementi olduğunu algılıyor.

[Emmet](https://medium.com/doctolib/why-i-love-pressing-tab-featuring-emmet-578aa4e77858)’in kendi sitesindeki cheat sheete [buradan](https://docs.emmet.io/cheat-sheet/) ulaşabilirsiniz. Bu konuda bol bol egzersiz yapmayı unutmayın lütfen, emin olun başta eliniz alışana kadar çok zorlansanız da emmet kullanımı çalışma hızınızı arttıracak ve sizi gereksiz çabadan kurtaracaktır.


## Görsellerle Çalışmak
Bu yazıda HTML belgesine resim ekleme, bu resimlerle çalışma konusunu inceleyeceğiz. Öncelikle HTML sayfasına resim eklemek için `<img>` tagi kullanılır.

### `src=""` Kullanımı
Kod bloğundaki `src=""` özelliğine görselin URL ya da dosya adresi belirtilerek resim HTML sayfasına çağırılır. (Resmi webden çağırmak için resmin URL'ini src=”…” parametesine eklemek yeterlidir.)
```html
<img src="ornek.jpg"/>
```
Yukarıdaki örnekte resim HTML dosyasıyla aynı dizinde(klasörde) olduğu için direkt adını ve uzantısını yazmak yeterlidir. Burada img uzantısına dikkat etmek önemli, HTML dosyaları nasıl .**html** ile bitiyorsa tüm resim dosyalarının sonu da **.xbm, .gif, .png veya .jpg** ile veya başka bir resim formatıyla bitmelidir.

### Yaygın Image Formatları

Diyelim ki projenin içerisinde bir dizin oluşturdunuz (images) ve resminizi bu dizine eklediniz. Bu defa çağırmak için öncelikle images dizinine gitmek gerekiyor.
```html
<img src="images/ornek.jpg"/> 
```
Ya da resim bir üst dizinde kalıyor olabilir. Bu durumda bir üst dizine çıkıp images dizinini bulup resmi çağırmak gerekiyor. **(Üst dizine çıkmak için ../ kullanırız.)**
```html
<img src="../images/ornek.jpg"/>
```

Bu şekilde istediğiniz kadar üst dizine çıkabilirsiniz.
```html
<img src="../../images/ornek.jpg"/>
```

### `alt=""` Kullanımı
Alt textlerin temel amacı, görüntüleri göremeyen kullanıcılar için metinler sunmaktır. Kullanıcı görseli görüntüleyemez ise (Yavaş bağlantı, src özelliğinde hata vb.) alt özelliği görüntü için alternatif bilgilendirici bir metin içerir.
```html
<img src="../images/kedi.jpg" alt="Yavru Kedi"/>
```

### `title=""` Kullanımı
Title özelliği kullanıcıyı bilgilendirme amacı taşır. `Cursor`(mouse imleci) ile görselin üzerine gelince bu özelliğe verilen text mesajı görünür. Ek açıklama gerektirecek resimlerde kullanabiliriz. Bilgilendirme amacı taşır.
```html
<img src="../images/kedi.jpg" title="image"/>	
```
**NOT:** Title ve Alt parametreleri *SEO* açısından önem taşımaktadır.

### `width` ve `height` Kullanımı
Görsele istenen ölçüleri vermek için `width` ve `height` özellikleri kullanılır.

**Width yatay genişlik, Height ise dikey uzunluk**için kullanılır.

Width ve Height özellikleri tanımlanmadığı zaman görsel sayfada gerçek ölçüleri ile görünür. Bu ölçülerden yalnızca birine değer verildiğinde görsel oranları korunarak belirlenen ölçüde görünür. Her iki özelliğe de değer verildiğinde resim oranları yeni verilen ölçülerde olduğu gibi görünür. Bu kullanım resim ölçüleri ile uyumlu olmadığı zaman resimde oransal bozukluklar oluşur.
```html
<img src="resim.jpg" width="300" />
<img src="resim.jpg" height="400" />
<img src="resim.jpg" width="300" height="600" />
<img src="resim.jpg" height="100%" />
```
[Buradan](https://jsfiddle.net/detfj6w9/4/) örneği inceleyebilirsiniz.

### `border` Kullanımı
Görseli belirtilen kalınlıkta çerçeve içine alır. Daha gelişmiş **CSS Border** özelliği bunun yerine kullanılabilir.

Aşağıda `border` örneği: Görsele **3 pixel** kalınlıkta border verir.
```html
<img src="resim.jpg" border="3" />
```

### `align` Kullanımı
Web sayfasında resmin gözükeceği pozisyonu belirlemede align özelliği kullanılır. Bu özelliğe verilebilecek değerler şunlardır: `left`, `right`. Görselin sağa veya sola yaslı çıkmasını sağlar.

```html
<img src="resim.jpg" align="right" />
```

### Görsele Link Vermek
Görsele link vermek için `img` tag'i `a` taginin içerisinde kullanılır. Yönlendirilmek istenen yerin URL'i `a` taginin `href` özelliğine yazılır. Görsel ise `a` taginin açıklama kısmına eklenir.
```html
<a href="default.asp">
  <img src="smiley.gif" alt="HTML tutorial" style="width:42px;height:42px;">
</a>
```
[Buradan](https://jsfiddle.net/qcpfsev7/2/) örneği inceleyebilirsiniz.

### `map` ve `area`
Görselleriniz hyperlink atamanız durumunda görselin tüm alanı link alanı haline dönüşecektir. Görselin herhangi bir yerine tıklanılması durumunda görsel sizi tanımlanan bağlantıya gönderecektir. `<img>` etiketleri için kullanılan `<map>` ve `<area>` etiketleri ile resmin içindeki koordinatlarla belirlediğimiz bir alanı sadece link haline getirebiliriz. Eklediğimiz `<area>` etiketi kadar belirlenen alanı bir resim üzerinden birçok bağlantıya link verebiliriz.

**Örneğin** Instagram'da bazı satıcılarda gördüğünüz bir insan fotoğraf üzerinde pantolon ve ayakkabının ürün linklerini ayrı ayrı vermek isterseniz kullanabilirsiniz.
```html
<html>
<body>
<img src="workplace.jpg" alt="Workplace" usemap="#workmap" width="400" height="379">

<map name="workmap">
 <area shape="rect" coords="34,44,270,350" alt="Computer" href="computer.htm">
 <area shape="rect" coords="290,172,333,250" alt="Phone" href="phone.htm">
 <area shape="circle" coords="337,300,44" alt="Cup of coffee" href="coffee.htm">
</map>
</body>
</html>
```

[Buradan](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_images_map2) inceleyebilirsiniz.


### `onload` Event'i Kullanımı
Bu olay görsel yüklenmesi tamamlandığında çalışacak fonksiyonu belirler. Herhangi bir nedenle görsel yüklenemezse ya da belirtilen adreste resim yoksa fonksiyon çalışmaz.

Aşağıdaki örnekte görsel yüklenmesi tamamlandığında `resimYuklendi()` fonksiyonu çalışacak ve ekrana **Resim Yüklendi.** uyarısı JavaScript tarafından bastırılacak. Bu konuyu ileride çok daha detaylı göreceğiz.
```html
<html>
    <body>
        <img src="resim.jpg" onload="resimYuklendi()" />
    </body>
    
    <script>
        function resimYuklendi(){
            alert("Resim yüklendi.");
        }
    </script>
</html>
```
### `picture` Elementi ile Kullanım
HTML5 ile gelen `picture` elementi web sayfamızda responsive image'ler kullanmamız konusunda büyük kolaylıklar sağlıyor. Bir tane `img` ve birden fazla source içerebilir. `picture` tagi ekran boyutlarına göre birden çok source kulllanmamızı sağlar bu sayede ekran boyutu değiştikçe farklı image'leri kullanabilirsiniz.

**Örnek:** Burada ekran genişliğinin 800 pikselden küçük olduğu durumlarda başka diğer koşullarda ise başka bir görsel kullanılacak.
```html
<picture>
    <source srcset="https://cdn.sanity.io/images/9kdepi1d/production/65c832d202a503b15d99e628f4313782f3ef50db-300x62.png" media="(min-width: 800px)">
    
    <img src="/media/cc0-images/painted-hand-298-332.jpg" alt="" />
</picture>
```

Tarayıcı, her bir source öğesini inceleyip eşleşme sağlar. Eşleşme bulunamazsa veya tarayıcı `<picture>` öğesini desteklemiyorsa, `<img>` öğesinin `src` URL'si seçilir. Seçilen görüntü daha sonra `<img>` öğesinin kapladığı alanda sunulur.

[Buradan](https://jsfiddle.net/a2dvm503/4/) ekran boyutunuzu değiştirerek inceleyebilirsiniz.

Aşağıda codepen kullanarak deneyimle!

<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/zYorjKe?height=300&amp;theme-id=dark&amp;slug-hash=zYorjKe&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_zYorjKe"></iframe>
---


## Linklerle Çalışmak

Bir HTML dosyası içerisinde herhangi bir sayfaya, sayfa içine, bir websitesine, e-mail, telefon adreslerine ya da dosya yolu belirtilen herhangi bir dosyaya (resim, video, zip vb.) erişmek için kullanılan HTML etiketidir. Genel yapısı `<a></a>` şeklindedir.

```html
<a href="gitmek istenilen yer">Gidilecek yer için isim tanımlaması</a>
```
![](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/html/linklerle-calismak/figures/a-tagi.png)


### HTML sayfaları içinde kullanımı:
### Sayfalar arası kullanımı:
HTML sayfalar arası geçiş yapmak için linklerden şu şekilde faydalanırız. Şu an üzerinde çalıştığımız klasörün içerisinde bir linksayfasi.html adında dosya oluşturduk ve içerisine bir şeyler yazdık. Şimdi HTML'de sayfalar arası linkleme ile yeni oluşturduğumuz sayfaya gitmek için link oluşturacağız:
```html
<a href="linksayfasi.html">İkinci sayfaya git</a>
```
Bunu oluşturduğumuzda tarayıcı ekranımızda **Diğer sayfaya geç** diye bir link oluşacak (üzerine gelindiğinde mouse'un el işaretine dönmesinden anlaşılabilir)

**Örneği görelim:**

![DiğerSayfayaGeç](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/html/linklerle-calismak/figures/sayfalar-arasi-link.gif)

### Sayfa içerisinde kullanımı:
Sayfa içerisinde herhangi bir başlığa ya da bölüme gitmek için linkler kullanılabilir. Aynı sayfada işlem yapacağımız için birden fazla satır ekleyeceğim ve en aşağıya scroll ile kaydırmak yerine link yardımı ile gideceğim. Bunun için de gidilecek bölüm için `a` tagine `name` özelliği verilmelidir:
```html

<a href="#sonbolum">Aşağı Git</a>
<a name="sonbolum"></a>
```
![AşağıGit](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/html/linklerle-calismak/figures/sayfaici-link.gif)

### Website Yönlendirmesinde Kullanımı:
`a` etiketinde `href` özelliğine verilen herhangi bir websitesi adresine kolayca gidilebilir. Burada `target` özelliğini göreceğiz. Bu özellik, gitmek istediğimiz bağlantının geçerli pencerede mi yoksa yeni bir pencerede mi açılması için kullanılır. `_self` özelliği geçerli pencerede açılması içindir. Varsayılan olarak böyledir. `_blank` özelliği ise yeni bir pencerede açılması içindir. Kodluyoruz'un internet sitesine gidelim:
![WebsiteyeGit](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/html/linklerle-calismak/figures/website-link.gif)


### Mail ve Telefon Yönlendirmesinde Kullanımı:

`a` etiketinin `href` özelliğine verilen `mailto:` ve `tel:` özellikleri sayesinde direkt olarak herhangi bir e-mail adresine posta gönderilebilir ya da geçerli bir telefon numarası aranabilir. Kodluyoruz'un e-mailine gidelim ve rastgele bir numaraya gidelim.
```html
<a href="mailto:info@kodluyoruz.org">Kodluyoruz'a mail atınız.</a>
```

**Yukarıda öğrendiklerinizi aşağıda deneyebilirsin!**

<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/xxRZzgE?height=300&amp;theme-id=dark&amp;slug-hash=xxRZzgE&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_xxRZzgE"></iframe>


## [Blok Elementler ve Inline Elementler](https://htmlreference.io/)le Çalışmak

Bulunduğu yerin tamamını kaplayan [elementler](http://www.99lime.com/_bak/topics/you-only-need-10-tags/); **Blok Elementler**

Sadece bulunduğu (yazdığımız text kadar) yeri kaplayan elementler; **Inline Elementler** (Bkz; `a`, `strong`, `em`, `span`,...)

```html
<h1>HTML</h1>
<h2>Blok Elements</h2>

<p>
  Lorem ipsum dolor <strong>sit amet consectetur adipisicing</strong> elit.
  <em>Tempore,</em> odio. <a href="">consectetur adipisicing</a>
</p>

<p>
  Lorem ipsum, dolor sit <strong>amet consectetur adipisicing</strong> elit.
  <span style="color: rgb(253, 17, 0)">
    Assumenda ipsam id amet ratione quam natus.</span
  >
</p>

<p>
  div: Lorem ipsum dolor
  <br />
  sit amet consectetur adipisicing elit. Laboriosam, non.
</p>

<p>
  <strong>
    <em>Lorem ipsum dolor sit</em>
  </strong>
  amet consectetur adipisicing elit. Deserunt, tempore?
</p>
<p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Autem, vel.</p>

<hr />

<h2><a href=""></a>Block Element</h2>
```

`<div>`: Elementleri bir blocka almak için kullanılır. Yeni bir block haline getirdikten sonra alt satıra geçer.
`<span>`: Kendi başına bir işe yaramayan inline bir ayırıcı oluşturarak çeşitli ayar opsiyonları sağlar. Sadece belli bir yerde bir özellik verirken diğer yerdeki özelliklerin değişmesini istemediğimizde kullanırız.

Bunları genellikle bloklarımızın içinde css özellikleri oluştururken kullanıyoruz.

Ek:

`<br>`: Bir alt satıra geçirir!
`<hr>`: Çizgi ile ayırır!

---

 HTML elementleri, iki şekilde kategorize edilmiştir; block-level element ve inline element. Bu sınıflandırma da tabiiki stil verirken göz önüne alınması gereken önemli bir noktadır.

 Block-level (blok seviyeli) elementler her zaman yeni satırdan başlar ve soldan sağa var olan alanı kaplar. Yani açılış ve kapanış etiketi arasında belirlenen  alanı kaplar. Inline (satır içi) elementler ise adından anlaşılacağı üzere aynı satırda başlayıp içerik kadar alan kaplar.

 Bu farkı anlamak için çok sık kullandığımız iki önemli etiket vardır.

 - Block-level elementler için `<div>` etiketi.
 - Inline elementler için `<span>` etiketi.

Şimdi bu elementleri anlamak için bir örnek yazalım. Bu örnekte bütün etiketlerin arkaplan rengini farklı yapıyoruz ki kapladıkları alanları ve nereden başladıklarını anlamak kolay olsun.
```html
  <style>
       body{
           background: forestgreen;
           font-size: 30px;
       }
       div{
           background: wheat;
       }
       span{
           background: palevioletred;
       }
       label{
           background: blueviolet;
       }
       h6{
           background: orange;
       }
    </style>
    <div><u>Block-level element</u></div>
    <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Aliquam, eveniet.</div>
    <h6>Başlık etiketleri block etiketlerdir.</h6>
    <hr>
    <span><u>Inline element</u></span>
    <span>Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium voluptatem eaque id quae 
      tempore nostrum perspiciatis et culpa tenetur nobis.</span>
    <label>Lorem ipsum dolor sit amet.</label>
```
Çıktısı:

![Block-level--Inline-Element--Çıktısı](https://www.mobilhanem.com/wp-content/uploads/2019/10/block-inline-1024x523.png)

Bu örnekte **block-level element** olarak `<div>`, `<h6>` ve `<hr>` etiketlerini kullandık. Inline elementlere örnek olarak ise `<span>` ve `<label>` etiketlerini kullandık. Verdiğimiz background(arka plan) rengi sayesinde ***block-level*** elementlerin satırı olduğu gibi kapladıklarını ve ***inline*** elementlerin ise sadece içerik kadar yer kapladığını gördük.

Örneğin linkine de [buraya](https://codepen.io/emineimran/pen/eYYYQom) tıklayarak ulaşabilirsiniz.

Şimdi bir liste halinde tüm elementleri bu iki özelliğe göre sınıflandıralım ve ne amaçla kullanıldıklarını öğrenelim.

### Block-Level Elementler
- `<address>` : İletişim bilgileri tanımlanır.
- `<article>` : Makale tanımlar.
- `<aside>` : İçeriği sayfa içeriğinden ayırır.
- `<blockquote>` : Başka bir kaynaktan alıntılanan bir bölüm için kullanılır.
- `<canvas>` : Grafik çizmek için kullanılır.
- `<dd>`: Tanımlama listelerinde bir terimin tanımı için kullanılır.
- `<div>` : Bir bölümü tanımlar.
- `<dl>` : Tanımlama listelerini tanımlar.
- `<dt>` : Tanımlama listelerinde bir terimi tanımlar.
- `<fieldset>` : Bir formdaki ilgili elemanları gruplandırır.
- `<figcaption>` : `<figure>` etiketi için altyazı tanımlar.
- `<figure>` : Medya içeriği ve altyazısını gruplar.
- `<footer>` : Altbilgi bölümü.
- `<form>` : Kullanıcı girişi için bir HTML formu tanımlar.
- `<h1>` - `<h6>` : HTML başlıklarıdır.
- `<header>` : Başlık bölümü.
- `<hr>` : İçerikteki tematik değişimi tanımlar.
- `<li>` : Listenin özelliğini tanımlar.
- `<main>` : Bir belgenin ana içeriğini için kullanılır.
- `<nav>` : Navigasyon linklerinin tanımlar.
- `<noscript>` : İstemci tarafı komut dosyalarını desteklemeyen kullanıcılar için alternatif bir içerik tanımlar.
- `<ol>` : Sıralı listeyi tanımlar.
- `<p>` : Bir paragraf için kullanılır.
- `<pre>` : Önceden biçimlendirilmiş metni tanımlar.
- `<section>` : Belgedeki bir bölüm.
- `<table>` : Tabloyu tanımlar.
- `<tfoot>` : Tablodaki footer içeriğini gruplandırır.
- `<ul>`  : Sırasız listeyi tanımlar.
- `<video>` : Video veya film tanımlar.

### Inline Elementler
- `<a>` : Link tanımlar.
- `<abbr>` : Kısaltma tanımlar.
- `<acronym>` : Bir kısaltma tanımlar. HTML5’te desteklenmiyor ve bunun için `<abbr>` kullanılıyor.
- `<b>` : Kalın metni tanımlar.
- `<bdo>` : Geçerli metin yönünü geçersiz kılar.
- `<big>` : Büyük metni tanımlar.
- `<br>` : Tek satır sonu tanımlar
- `<button>` : Tıklanabilir buton oluşturmak için kullanılır.
- `<cite>` : Bir çalışmanın başlığı için kullanılır.
- `<code>` : Bir bilgisayar kodu tanımlar.
- `<dfn>` : Bir terimin tanımlayıcı örneğini temsil eder.
- `<em>` : Metni vurgulamak için kullanılır.
- `<i>` : İtalik yazı.
- `<img>` : Resim tanımlar.
- `<input>` : Giriş kontrolü için kullanılır.
- `<kbd>` :  Klavye metni tanımlar.
- `<label>` : `<input>` etiketi için bir etiket tanımlar.
- `<map>` : İstemci tarafı görüntü haritasını tanımlar.
- `<object>` : Gömülü bir nesneyi tanımlar.
- `<output>` : Bir hesaplamanın sonucu için kullanılır.
- `<q>` : Küçük bir alıntı tanımlar.
- `<samp>` : Bir bilgisayar programından örnek çıktıyı tanımlar.
- `<script>` : Komut dosyasını tanımlar.
- `<select>` : Drop-down liste için kullanılır.
- `<small>` : Yazı boyutunu kçüçültmek için kullanılır.
- `<span>` : Dökümanda bir bölüm.
- `<strong>` : Yazı kalınlığını artırır.
- `<sub>` : Abone olunan metin.
- `<sup>` : Üst yazı için kullanılır.
- `<textarea>` : Birden fazla input tanımlar.
- `<time>` :  Zaman için kullanılır.
- `<tt>` : Teletip metnini tanımlar.
- `<var>` : Bir değişken tanımlar.

# Ödev 2
## Kişisel Sayfamızı Detaylandırmaya Devam Etmek

- Sayfanıza bir adet resim ekleyin ve bu resime bir açıklama yazın.
- Sevdiğiniz film, dizi ve kitapları bunlar başlıklar olacak şekilde sıralayınız. (Film, dizi, kitap sıralı liste, içerikleri bullet liste olacak şekilde)
- Bunları sıralarken film ve dizilerin en az bir tanesine IMDb linki, kitapların bir tanesine de** Goodreads linkini** yazınız.
- Kurduğunuz yapılarda block, inline gibi elementler kullanmaya çalışın.

![Ödev2](https://github.com/Kodluyoruz/taskforce/raw/main/html/odev2/figures/secondwebpage.png)

---

## HTML Etiketlerine Ekstra Özellikler Eklemek
1. Tüm HTML elementleri [nitelik](https://www.algoritmaornekleri.com/web/html/html-oznitelik-kullanimi-html-attributes/) alabilirler.
2. Her zaman başlangıç elemanının içine yazılır.
```html
<a href = ""></a>
```
1. Bu nitelikler, etiketler konusunda ekstra özellik bilgisi sağlar.
2. Kelimeler arasında tire işareti koyarak(html-etiketi) veya camel case(htmlEtiketi) şeklinde kullanılabilir. HTML'de genellikle - (tire) kullanılır.
3. `class` veya `id` gibi özniteliklerin ismi belirlerken Türkçe karakter tercih edilmemelidir. (ş,ç,ö,ü,ğ,büyük İ ve küçük ı)
Kullanabilmek için özniteliği yazdıktan sonra `=""` kullanılıp istediğimiz özelliği tırnakların içine yazılmalıdır..

İngilizce bir kaynakta aramak istiyorsanız ***["HTML attributes"](https://www.w3schools.com/html/html_attributes.asp)*** diye aratmak gerekir.

## *Özet:*
```html
<img src ="" alt = "">
```

HTML dosyasına bir resim eklemek istersek `img` etiketini kullanırız. `img`, İngilizcedeki image(resim) kelimesinin kısaltmasıdır. Bu etiketin yanında ise `src` ve `alt` özniteliklerini ekleyebiliriz. `src` (source = kaynak) ekleyeceğimiz resmi nereden alacağını belirttiğimiz yerdir.

`alt` (alernative = alternatif) ise eğer bir nedenden resim görüntülenemez ise resme alternatif olarak ne yazması gerektiğidir.
```html
<a href =""></a>
```
Eğer bir bağlantının URL sini vermek istiyorsak `<a>` (anchor) etiketini kullanırız. href teki iki tırnağın arası URL'yi girdiğimiz yerdir.


### *Her etikete `id` ve `class` özniteliklerini ekleyebiliriz.*
```html
<img src ="" alt = "" id ="">

<img src ="" alt = "" class ="" id ="">

<a href ="" id="" class ="" data-id ="" ></a>
```

### id (identity = kimlik)
`id` kullanılan etiketin kimliğini belirtir. **Biriciktir**(unique) yani dökümanın içindeki bir etikete yalnızca bir kez o `id` ismi verilebilir.

**Not:** `id` biricik olduğu için istisna olarak `id = facebook-URL` şeklinde yazarak tırnak işareti kullanmayabiliriz.


### `class` (sınıf)
`class`, HTML etiketinin hangi sınıfta olduğunu belirmemizi sağlar. Aynı sınıf adını **birden fazla** HTML etiketine **verebiliriz.**
```html
<img src ="" class ="documents">
<a href ="" class ="documents" ></a>
```
Burada görüldüğü gibi iki HTML etiketi de(`img` ve `a`) documents sınıfında bulunmaktadır. Daha sonrasında aynı sınıfta bulunan bu iki etikete CSS ile aynı anda değişiklik yapılabilir.

## [HTML İskeletinin](https://www.informit.com/articles/article.aspx?p=2472081) Genel Yapısını Anlamak
#### HTML sayfalarının en temel bileşenleri nelerdir? Bir HTML iskeleti nasıl oluşturulur ?

Web tasarım konusunda araştırma yapan hemen herkesin karşına çıkan temel kavram HTML'dir. Web sayfalarını oluşturma aşamasında kullanılan standart bir metin işaret dili olan **HTML açılımı “Hyper Text Markup Language”** olarak bilinir. Genel bilinen yanlış kanının aksine **HTML** bir programlama dili değildir.

Daha açık anlatmak gerekirse, Chrome, Firefox, Yandex gibi tarayıcıların okuyup anlamlandırdığı dil **HTML** dilidir.

Bir html sayfası oluşturmadan önce mutlaka **HTML 5 standartlarına uygun bir html iskeleti** oluşturmalıyız. Web sayfalarımızı **HTML 5** standardına uygun hazırlamamız büyük önem taşımaktadır çünkü arama motorları tarafından önemsenmektedir.

#### [HTML İskelet](https://www.w3schools.com/w3css/w3css_web_html.asp) Örneği
 ```html
 <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Page Title</title>
<meta name="viewport" content="width=device-width,initial-scale=1">
<link rel="stylesheet" href="">
<style>
</style>
<script src=""></script>
</head>
<body>

<img src="img_la.jpg" alt="LA" style="width:100%">

<div class="">
 <h1>Bu bir h1 boyutunda başlık.</h1>
 <p>Bu bir paragraf.</p>
 <p>Bu başka bir paragraf.</p>
</div>

</body>
</html>
 ```

#### HTML'inizi Yapılandırma
**HTML** yapısında sayfanın genel yapısını tanımlamak ve bazı basit başlık bilgilerini sağlamak için 3 farklı etiket bulunur. Bu üç etiket `<html>` , `<head>` ve `<body>` her web sayfasının temel iskeletini oluşturur.

Ayrıca, her şeyi yüklemeden önce sayfa hakkında basit bilgiler *(başlığı veya yazarı gibi)* sağlarlar. Sayfa yapısı etiketleri, sayfanın görüntülendiğinde nasıl görüneceğini etkilemez; sadece tarayıcılara yardımcı olmak için bulunurlar.


#### `DOCTYPE` Tanıtıcı
Bir sayfa yapısı etiketi olmasa da, XHTML 1.0 ve HTML 5 standartları web sayfalarınıza ek bir gereklilik getirir. Her sayfanın ilk satırı, sayfanızın uygun olduğu HTML sürümünü tanımlayan bir DOCTYPE tanımlayıcısı ve bazı durumlarda, spesifikasyonu tanımlayan Belge Türü Tanımını (DTD) içermelidir . Bunu `<html>` , `<head>` ve `<body>` etiketleri takip eder. HTML 5 belge türü, sayfa yapısı etiketlerinden önce görünür.


#### `<html>` Etiketi
Her HTML sayfasındaki ilk sayfa yapısı etiketi `<html>` etiketidir. Bu dosyanın içeriğinin HTML dilinde olduğunu gösterir. `<html>` etiketi `DOCTYPE` tanımlamasından hemen sonra kullanılmalıdır. Web sayfanızdaki tüm metin ve HTML öğeleri HTML etiketlerinin başlangıcına ve bitişine yerleştirilmelidir.

`<html>` etiketi sayfasını oluşturan etiketlerin tümünün bir kabı olarak hizmet vermektedir. Bunu dışarıda bırakırsanız, ki bunu yapmamalısınız çünkü bu, sayfanızı geçersiz kılar, tarayıcı sizin için bir `<html>` etiketi oluşturur, böylece sayfa HTML işlemcisi için anlamlı olur.


#### `<head>` Etiketi
`<head>` etiketi sayfayla ilgili bilgiler içeren etiketler için bir kapsayıcıdır. Genellikle sayfanın `<head>` bölümünde yalnızca birkaç etiket kullanılır. Sayfanızın hiçbir metnini başlığa ( `<head>` etiketleri arasına ) koymamalısınız. Yine `<head>` etiketinin arasında bulunan `lang` anahtar kelimesinin amacı sayfa içeriğinin hangi dilde oluştuğudur. Bunu belirtmemizin sebebi arama motorlarında bize bu sayfayı tarayıcımızın diliyle zıt düştüğü durumda çevirme tavsiyesi verip vermemesini sağlamaktır.


#### `<head>` Etiketi Arasında Bulunan Diğer Anahtar Kelimelerin Görevleri
- `<meta>` : Sayfamızı tanımlayan açıklamaların bulunduğu kısımdır. Sayfa açıklaması, sayfa başlığı, kullanılan karakter seti tanımlaması gibi işlemler burada tanımlanıyor.
- `<title>`: Tarayıcı penceresinin sekmesindeki başlığı buradan belirtiyoruz.
- `<style>`: Sayfada kullanılan stil işlemlerinin tanımlaması yapılır. Örneğin arka plan rengi yazı rengi ya da nesnelerin hizalanması gibi işlemler.


#### `<body>` Etiketi

HTML sayfanızın içeriği `<body>` etiketi içinde bulunur . Bu, tüm metni ve diğer içeriği (bağlantılar, resimler vb.) içerir.

Aşağıdaki örnekte etiketlerin iç içe olduğunu göreceksiniz. Yani hem `<body>` ve `</body>` hem de `<head>` ve `</head>` etiketlerini `<html>` etiketlerinin kapsadığını göreceksiniz. Tüm HTML etiketleri bu şekilde çalışır ve metnin tek tek iç içe bölümlerini oluşturur.

Örnek:
```html
<! DOCTYPE html> 
<html> 
<head> 
<title> Bu bir başlıktır.</title> 
</head> 
<body> 
... sayfanız ... 
</body> 
</html>
```
Etiketleri asla çakıştırmamaya dikkat etmelisiniz. Yani, asla aşağıdaki gibi bir şey yapmayın:
```html
<! DOCTYPE html> 
<html> 
<head> 
<body> 
</head> 
</body> 
</html>
```
Bir HTML etiketini her kapatışınızda, en son kapatılmamış etiketi kapattığınızdan emin olun.

---

## Semantic(Anlamlandırılmış) HTML Etiketleri Kullanımı
![SemanticScheme1](https://pbs.twimg.com/media/Et4mZDMUcAAcrEG.jpg)

Semantik, anlam veya anlamlandırma anlamı ifadesi taşımaktadır. O halde semantik elementler herhangi bir anlamı olan etiketler ifadesi taşımaktadır. Semantik olarak anlamlandırılmış bir element hem tarayıcıya hem geliştiriciye ne anlama geldiğini açık bir şekilde belirtir. `<div>` ve `<span>` gibi elementler semantik olmayan elementlerdir ve mevcut içeriğin hakkında bilgi vermezler. `<form>`, `<table>` ve `<img>` gibi elementler semantik elementlerdir ve içeriği açıkça belirtirler.


#### `header` Elementi
`header` elementi bir doküman veya bir `<section>` için bir başlık olduğunu belirtir. İçinde barındırdığı içeriği **kapsayıcı** olmalıdır. Bir dokümanda birden fazla kullanılabilir.

Aşağıdaki örnek, bir `<article>` için bir başlık içermektedir.

```html
<header> 
    <h1>Kodluyoruz Akademi Nedir?</h1>
</header>
<p>Her bireyin, özellikle kadınların, yükselen teknoloji sektöründe başarılı olması için eşit haklara sahip olması gerektiğine inanıyoruz.
Bu yüzden, Kodluyoruz Akademi gençlere dünya çapında kaliteli ve ücretsiz içerik, kaynak ve bootcamp sağlıyor!</p> 
```


#### `nav` Elementi
`nav` elementi navigasyon bağlantıları büyük sayfalar için ortaya çıkarılmıştır. Fakat, sayfadaki tüm linkler bu element içinde olmak zorunda **değildir.**
```html
<nav> Bootcamp CS50X Kodluyoruz Jr. Şirketler Hakkımızda </nav>
```


#### `<section>` Elementi
Section elementi bir doküman içinde olan sadece bir kısmı belirtir.
```html
<section>
<h1>CS50xKodluyoruz Challenge Başlıyor!</h1>
<p>CS50xKodluyoruz ödevlerine devam etmekte zorlanıyor musun? Bitirmek istediğin halde nasıl ilerleyeceğini bilmiyor musun?
O zaman CS50xKodluyoruz Challenge tam sana göre! Challenge ekibiyle hedefimiz: 4. haftaya kadar bütün ödevleri tamamlamak olacak!</p>
</section>
<section>
<h1>CS50x Nedir?</h1>
<p>CS50x (Computer Science 50), Harvard Üniversitesi Profesörü David J. Malan tarafından verilen efsanevi bilgisayar bilimlerine giriş kursu.
Her yıl milyonlarca kişi tarafından alınan bu kursu Türkçe’ye çevirsek ve Türkiye’nin her yerinden gençlere ulaştırsak nasıl olur?
Üstelik online ve ücretsiz olarak? Üstelik çalışma gruplarında her yaştan gencin beraber öğrenmesini destekleyerek?</p>
</section>
```


#### `figure` Elementi
İçeriğinde resim, gösterim, diyagram, kod listeleri vs. gibi nesnelerin olduğunu belirtir. Ana akış ile ilgili olsa da, konumu ana akıştan tamamen bağımsızdır. Çıkarılırsa dokümanın akışını **engellemez.**
```html
<p>CS50x Kodluyoruz için hemen kayıt ol, dersleri anında almaya başla. Dersler tamamen online ve ücretsiz! Üstelik CS50x Kodluyoruz herkese göre.
İster hiç bilgisayar dersi almamış olun, ister kendinizi ilerletmek isteyin: Bu ders, sağlam bir algoritma temeli isteyen herkes için!</p>

<figure>
	<img src="https://cdn.sanity.io/images/9kdepi1d/production/1a22b9fada2411b7369592fd852613637834e866-5520x3680.jpg?auto=format" />
</figure>
```


#### `figcaption` Elementi
`<figcaption>` etiketi, `<figure>` elementinin belirttiği resme başlık koymaya yarar.
```html
<figcaption>
	<p>A duck.</p>
	<p><small>Photograph courtesy of News.</small></p>
</figcaption>
```


#### `aside` Elementi
`<aside>` elementi içerdiğinden farklı olarak daha başka bazı içerikleri tanımlar. İçeriği, üst içerik hakkında olmalıdır.


#### `article` Elementi
`<article>` elementi bir makale elementidir. Bir makale web sayfasının geri kalanından bağımsız olarak dağıtılabilmelidir.

Genelde bu elementin kullanabildiği yerler forum mesajları, blog gönderileri, haber metinleri, yorumlar gibi makale içeren metinlerdir.


#### `footer` Elementi
`<footer>` elementi bir doküman ya da kısım için alt bilgilerini belirtir. Bir `<footer>` genelde dokümanın yazarını, telif haklarını, kullanım gizliği, iletisim vs. gibi bilgileri içerir ve bir dokümanda bir kereden fazla kullanılabilir.


<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/VwmedMr?height=300&amp;theme-id=dark&amp;slug-hash=VwmedMr&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_VwmedMr"></iframe>

---

## Diğer HTML Etiketleri Hakkında
HTML öğrenirken sıkça sorulan bir soru tüm etiketlerin öğrenilmesi gerekip gerekmediğidir. HTML güncel olarak 100’den fazla etiket içerir ancak bunların hepsini öğrenmek mümkün değildir. Günümüzde birçok HTML sayfası semantik elementler ve 10-12 adet semantik olmayan etiket ile oluşturulabilir.

- `h1` - Başlık
- `p` - Paragraf
- `i` / `em` - Eğik / Vurgulu Yazı
- `b` / `strong` - Kalın / Koyu Yazı
- `a` - Link
- `ul` & `li`  - Sırasız liste ve liste elemanı
- `blockquote` - Alıntı
- `hr` - Yatay çizgi ekleme
- `img` - Görsel
- `div` - Bölme 

Yukarıda yaygın kullanılan semantik olmayan etiketler ve görevleri verilmiştir. Bunlar dışında bir etikete ihtiyaç duyulduğunda istenen fonksiyona dair yapılacak araştırmayla ilgili etikete ulaşılabilir.


### Emmet
HTML ve CSS etiketlerinde kullanım kolaylığı sağlaması açısından [Emmet](https://emmet.io/) oldukça faydalı bir eklentidir. Kısaltılmış kod yapıları yardımıyla uzun kod blokları oluşturmayı sağlar.

**Asıl koda dönüşmeden önceki Emmet yapısı:**
```html
<!doctype html>
<html lang ="en">
<head>
  <title>Demo</title>
</head>
<body>
  ul#nav>li.item$*4>a{Item $}
</body>
</html>
```

**Emmet sonrası kodun tam formu:**
```html
<!doctype html>
<html lang ="en">
<head>
  <title>Demo</title>
</head>
<body>
  <ul id="nav>
    <li class="item1"><a href="">Item 1</a></li>
    <li class="item2"><a href="">Item 2</a></li>
    <li class="item3"><a href="">Item 3</a></li>
    <li class="item4"><a href="">Item 4</a></li>
	</ul>
</body>
</html>
```
---

## Bölüm Sonu Çalışması

3 adet HTML sayfasının birbirine linklenmesi ve **"HTML5 Semantik Yapısı"** nı da barındıran şuana kadar işlediklerimizin özeti niteliğinde bir projeyi hep beraber yapalım.

#### Ders Videoları:
[Bölüm Sonu Çalışması Part 1](https://app.patika.dev/courses/html/bolum-sonu1)
[Bölüm Sonu Çalışması Part 2](https://app.patika.dev/courses/html/bolum-sonu2)

#### Proje Önizlemesi:
![Bölüm Sonu Çalışması Proje Önizleme](https://github.com/cantuncr/front-end/raw/main/Patika.dev/frontend101/frontend101-odevler-kodluyoruz-patika.dev/odev-4-html-bolum-sonu-calismasi/img/screencapture-odev-4-html-bolum-sonu-calismasi.png?raw=true)
#### Kodlar:
**index.html:**
```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ana Sayfa</title>
</head>
<body>
    <!-- Navbar - Start -->
    <header>
        <nav>
            <ul>
                <li>
                    <a href="index.html">Ana Sayfa</a>
                </li>
                <li>
                    <a href="about-us.html">Hakkımızda</a>
                </li>
                <li>
                    <a href="contact.html">İletişim</a>
                </li>
            </ul>
        </nav>
        
    </header>
    <!-- Navbar - Start -->

    <!-- Content - Start -->
    <section>
        <!-- Articles - Start -->
        <article>
            <h2>Birinci Yazı</h2>
            <img height="300" src="img/laptop.jpg" alt="laptop">
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Reiciendis, incidunt!</p>
            <p>Lorem ipsum dolor sit amet.</p>
            <p>Eveniet facilis delectus voluptas provident!</p>
            <p>Porro numquam enim error optio!</p>
            <ol>
                <li>Lorem, ipsum dolor.</li>
                <li>Soluta, omnis eius.</li>
                <li>Cum, sit officiis!</li>
                <li>Beatae, nulla delectus?</li>
            </ol>
            <hr>
        </article>    
        <article>
            <h2>İkinci Yazı</h2>
            <img src="https://picsum.photos/id/27/200/300" alt="Yazi 1">
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Reiciendis, incidunt!</p>
            <p>Lorem ipsum dolor sit amet.</p>
            <p>Eveniet facilis delectus voluptas provident!</p>
            <p>Porro numquam enim error optio!</p>
            <ul>
                <li>Lorem, ipsum dolor.</li>
                <li>Soluta, omnis eius.</li>
                <li>Cum, sit officiis!</li>
                <li>Beatae, nulla delectus?</li>
            </ul>
            <hr>
        </article>  
        <article>
            <h2>Üçüncü Yazı</h2>
            <img src="https://picsum.photos/id/217/200/300" alt="Yazi 1">
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Reiciendis, incidunt!</p>
            <p>Lorem ipsum dolor sit amet.</p>
            <p>Eveniet facilis delectus voluptas provident!</p>
            <p>Porro numquam enim error optio!</p>
            <hr>
        </article>  
        <!-- Articles - End -->
    <!-- Content - Start -->
    </section>
    <!-- Footer - Start -->
    <footer>
        <nav>
            <ul>
                <li>
                    <a href="index.html">Ana Sayfa</a>
                </li>
                <li>
                    <a href="about-us.html">Hakkımızda</a>
                </li>
                <li>
                    <a href="contact.html">İletişim</a>
                </li>
            </ul>
        </nav>
    </footer>
    <!-- Footer - Start -->
    
</body>
</html>
```   



**about-us.html:**
```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hakkımızda</title>
</head>
<body>
    <!-- Navbar - Start -->
    <header>
        <nav>
            <ul>
                <li>
                    <a href="index.html">Ana Sayfa</a>
                </li>
                <li>
                    <a href="about-us.html">Hakkımızda</a>
                </li>
                <li>
                    <a href="contact.html">İletişim</a>
                </li>
            </ul>
        </nav>
        
    </header>
    <!-- Navbar - Start -->

    <!-- Content - Start -->
    <section>
        <!-- Articles - Start -->
        <article>
            <h2>Hakkımızda</h2>
            <img src="https://picsum.photos/id/77/200/300" alt="Yazi 1">
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Reiciendis, incidunt!</p>
            <p>Lorem ipsum dolor sit amet.</p>
            <p>Eveniet facilis delectus voluptas provident!</p>
            <p>Porro numquam enim error optio!</p>
            <ol>
                <li>Lorem, ipsum dolor.</li>
                <li>Soluta, omnis eius.</li>
                <li>Cum, sit officiis!</li>
                <li>Beatae, nulla delectus?</li>
            </ol>
            <hr>
        </article>     
        <!-- Articles - End -->
    <!-- Content - Start -->
    </section>
    <!-- Footer - Start -->
    <footer>
        <nav>
            <ul>
                <li>
                    <a href="index.html">Ana Sayfa</a>
                </li>
                <li>
                    <a href="about-us.html">Hakkımızda</a>
                </li>
                <li>
                    <a href="contact.html">İletişim</a>
                </li>
            </ul>
        </nav>
    </footer>
    <!-- Footer - Start -->
    
</body>
</html>
```



**contact.html:**
```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>İletişim</title>
</head>
<body>
    <!-- Navbar - Start -->
    <header>
        <nav>
            <ul>
                <li>
                    <a href="index.html">Ana Sayfa</a>
                </li>
                <li>
                    <a href="about-us.html">Hakkımızda</a>
                </li>
                <li>
                    <a href="contact.html">İletişim</a>
                </li>
            </ul>
        </nav>
        
    </header>
    <!-- Navbar - Start -->

    <!-- Content - Start -->
    <section>
        <!-- Articles - Start -->
        <article>
            <h2>İletişim</h2>
            <img src="https://picsum.photos/id/7/200/300" alt="Yazi 1">
            <p>
                Adres:
            </p>
            <address>
                Çankaya <br>
                Ankara
            </address>
            <ul>
                <li><a href="tel:03123123123">03123123123</a></li>
                <li><a href="mailto:cantuncr@gmail.com">cantuncr@gmail.com</a></li>
            </ul>
            <hr>
        </article>     
        <!-- Articles - End -->
    <!-- Content - Start -->
    </section>
    <!-- Footer - Start -->
    <footer>
        <nav>
            <ul>
                <li>
                    <a href="index.html">Ana Sayfa</a>
                </li>
                <li>
                    <a href="about-us.html">Hakkımızda</a>
                </li>
                <li>
                    <a href="contact.html">İletişim</a>
                </li>
            </ul>
        </nav>
    </footer>
    <!-- Footer - Start -->
    
</body>
</html>
```

---

## Ödev 3: Çikolatalı Küp Tarifi
Bu ödevimizde sevdiğimiz bir yemek ya da tatlının tarifini öğrendiğimiz bir web sitesini, HTML etiketlerini kullanarak yazmaya çalışacağız. Aşağıdaki resim size yol gösterebilir.

![Tatlı Tarifi Ödev Önizleme](https://github.com/Kodluyoruz/taskforce/blob/main/html/html-odev3/figures/%C3%A7ikolatak%C3%BCpleri.PNG?raw=true)

Kodlar:
```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CanCan Pâtissière</title> <!-- Sekme Adı -->
</head>
<body style="background-color: #E0C9A9;"> <!-- Arkaplan rengi belirlendi -->
    
        <h1 style="color: #5E2610;"><em>...Hurma Topları...</em></h1> <!-- Ana Başlık -->
        <em><b><p>Basit, pratik, tatlı krizinde hızır gibi yetişen şip-şak bir tarif. Çocuklarınızın da bayılacağı katkı malzemesiz, sağlıklı bir tarif...</p></b></em> <br> <!-- Minik bir info -->
        <br><b><p>Tarif:</b> Can TUNÇER</p> <br>

             <br>

    <article style="padding-left: 30em;"> <!-- Rasyonellikten ırak ve eksperimental olarak yapılan hizalama -->
           
            <li style="list-style-type:none;">                       
                <u><b><span style="color:#B0550B;">Kaç Kişilik:</span></b> 4 Kişilik</u> <!-- span ile spesifik alan boyaması -->
                <u><b><span style="color:#B0550B;">Hazırlama Süresi:</span></b> 30(10+20) dk.</u>
                <u><b><span style="color:#B0550B;">Dinlendirme Süresi:</span></b> 20 dk.</u>                     
             </li>

             <br>            
       
            <span style="background-color: brown; color: white;"><b>Tarif İçin Malzemeler:</b></span>
            <ul> 
                <li>1 Kase <b>Hurma</b></li>
                <li>3 Yemek Kaşığı <b>Fındık</b></li>
                <li>2 Yemek Kaşığı <b>Kakao</b></li>
                <li>6 Adet <b>Kuru Erik</b></li>
                <li>1 Kase <b>Hindistan Cevizi</b></li>
            </ul>
        

            <span style="background-color:brown; color: white;"><b>Nasıl Hazırlanır?</b></span>        
            <ol> <!-- Sıralı bir liste açalım -->
                <li>Hurmaların ve kuru eriklerin çekirdeklerini çıkartalım. </li>
                <li>Fındıkları dövün ve iyice toz haline gelmesini sağlayın.</li>
                <li>Bir robota hurmaları ve erikleri ilave edin. Üzerine fındık <br> ve kakaoyu da ekleyin ve robotu çekin. Karışımı kıvamlı <br> bir hamur haline getirene dek işleme devam edin.</li>
                <li>Yanınızda bir kase su bulundurun. Elinizi ıslatın, hamurdan <br> ceviz büyüklüğünde parçalar alın ve iyice yuvarlayın.</li>
                <li>Hindistan cevizi dolu kasede enfes vegan topları harmanlayın. <br> Ardından sunum kasesine alın.</li>
                <li>Hazırladığınız hurma toplarını buz dolabında bir süre bekletin. <br> Bir saat sonra çıkarın ve dilediğiniz gibi servis edin. Vegan tatlınız hazır.</li>
            </ol>       

            <p style="padding-left: 10em; font: 2em sans-serif;">Afiyet Bal Şeker</p>            

    </article>
    
</body>
</html>
```
---
## Coderbyte Challange
HTML eğitiminin sonuna yaklaştın! Şimdi sırada algoritma çözme yeteneğini pekiştiren hem de bootcamplere hazırlayan bir challenge var. Bu soruları çözmek için süren kısıtlı. Internet bağlantısına güvendiğin bir yerde girdiğinden emin ol. Kolay gelsin :smile:

Challenge linki [burada.](https://coderbyte.com/sl-candidate?promo=kodluyoruz-cmlzb:html-assessment-6ep83zbx45)

![Coderbyte-Multiple-Choices](https://lh3.googleusercontent.com/pw/AL9nZEXPaaut58RGZOSL4ONeAJHPn_vCzTsV3LETabPAZrhi7151qG520O-I2CRSjhtesW9W2RuaSdUtklCzyuzz__6nIuBnQ7FOtaVREw6OS7cR_2LTbjYLDrME_vLFOJ78PqvhU_xTaC2lQx7-VoSjSA9LnA=w826-h391-no)
![CoderByte-Case1](https://lh3.googleusercontent.com/pw/AL9nZEXN3z1mOyZcVDlQk5BuAwnTB8_AhrvK13W5a9zgooTJgjc3w0EucQPpqIhrCr63KxHvWnKt9J3SZPiKid1_SGo5xhrS5cHsbiy-hEZQN4Kf-F102NzATwoQp9ajYNpTMmaPLV5OOea-z6bofHJBVP3W4Q=w1513-h860-no)
![CoderByte-Case2](https://lh3.googleusercontent.com/pw/AL9nZEVY5a9OIWx1apjmfNu83IymZsSe6b7VSYBeoLM_Dh_AyMii0BAwWv8Ssf4GFlYiiLm_AULanr-_NjSg5eCcPpAZhpCesd2V7B7TFznPt3vJKv_WIujolvBs5Zx6MX3ev8ydXgYQIhEgwN7DFO3D67Z8uA=w1221-h860-no)

---

# CSS

## CSS Nedir?
CSS'de arka plan renklerini değiştirmekten ve nesnelerin neden olması gerektiği gibi hizalanmadığını merak etmekten daha fazlası vardır. Ancak JavaScript framework'leri ve kütüphaneleri gibi diğer araçlara zaman ayırdığımız için, CSS genellikle gözden kaçan ve arka planda kalan görsel bir iletişim aracıdır. Genellikle temel çalışma yeterliliğine sahip CSS'i alırız ve acil hedeflerimize ulaşır ulaşmaz daha derine inmeden bırakırız. Sonuç olarak uygulama genelinde yapı, mimari ve uyum gibi şeyleri göz ardı etme eğilimindeyiz. Biz bu yazımızda CSS hakkında bilmemiz gerekenleri ele alacağız ve şimdi en baştan başlayalım.


**CSS (Basamaklanmış Stil Katmanları)**, web sayfasını şekillendirmek için kullanılan bir kodlama türüdür. CSS kullanarak web sayfasının görünümünü ve düzenini değiştirebiliriz. Bir web sitesinin görünümünün masaüstü bilgisayarlar, tabletler ve mobil cihazlar gibi farklı ekranlarda nasıl değiştiğini de tanımlayabiliriz. CSS, C++ veya JavaScript gibi bir programlama dili değildir. Bunun nedeni, CSS'in amacının web tarayıcıları için biçimlendirmeye(HTML'e) stil vermek olmasıdır. HTML yalnızca içeriği "işaretleyen" bir dildir - yani, belgeye belirli bir görsel ve yapısal biçimlendirme verir.


Hem HTML hem de CSS doğaları gereği bildirimseldir. Bu, yalnızca bir şeyleri açıkladığı ve herhangi bir işlem yapmadığı anlamına gelir. Tarayıcılar CSS'i görüntüleme için yorumlarken, bunu doğrusal bir şekilde yapar. Bunun nedeni, CSS'in dosyayı yukarıdan aşağıya okuyan tarayıcıya talimatlar vermesidir. Bir kural belirlendiğinde ve daha sonra dizin aşağıya doğru değiştirildiğinde, tarayıcı ekranda görüntülenecek nihai sonuç olarak en son değerlendirmeyi alır. CSS'deki C'nin ifade ettiği şey budur. CSS'in cascade(kaskad)etkisi, tarayıcıyı, kuralın fiziksel olarak ne zaman gerçekleştiğine bağlı olarak, kuralları art arda ve geçersiz kılacak şekilde görüntüleyecek şekilde ayarlar. Cascade(kaskad), öğe için birden çok CSS bildirimi ve birden çok stil sayfasının bir kombinasyonu olduğunda, belirli bir öğe için uygulanan stiller arasındaki çakışmayı çözme anlamına gelir. Sonuç olarak, CSS göründüğü kadar kolay değildir. Anlamadan kullanmaya çalışırsanız web geliştirmede zorluk yaşarsınız. Bu nedenle, CSS öğrenmek bir programlama dili öğrenmek kadar önemlidir.


## CSS Syntax
İlk CSS kodumuzu yazalım. Örneğin, `h1` etiketinin rengini değiştirmek istiyorum.
```html
<h1>I'm a Header</h1>
```
![I'm a Header(without CSS)](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/css-nedir/figures/header.png)

Öncelikle, CSS'e HTML öğesini nasıl bulacağını söylememiz gerekir. Bunu selector denen bir özellik ile yapabiliriz. CSS'de bir selector, HTML öğelerini etiket adı, sınıf adı, kimliği ve çok daha fazlasına göre bulmak için kullanılır.

O zaman şimdi HTML öğesi için bir `selector` tanımlayalım ve ardından selector parantezleri arasında her biri noktalı virgülle biten CSS kurallarını bildirelim.
```css
h1 { color: red;  }
```
![I'm a Header(with CSS)](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/css-nedir/figures/header-color.png)

Böylelikle, tanımlı selector'e (`h1`) bağlı olarak, CSS artık yeni kuralların nereye uygulanacağını anlayabilir.

Bunların yanı sıra CSS kodlarımızı .css uzantılı bir dosya içerisinde tutar ve bu dosyayı HTML sayfası içerisine basit bir kodla çağırabiliriz. Örneğin CSS dosyamızın adı "hello.css" olsun ve bu dosyayı Html sayfaya eklemek için HTML içine yazmamız gereken kod şu şekildedir.
```html
<head> <link rel=”stylesheet” type=”text/css” href=”hello.css” /> </head>
```
Bir CSS selector tanımlamanın birçok farklı yolu vardır, aşağıda selector türlerinin bazı örneklerini görebilirsiniz:

- **Class Selector:** HTML öğelerini sınıf özelliklerine göre bulur.
- **ID Selector:** Öğeleri belirli kimliğine göre bulur.
- **Element Selector:** Öğeleri etiket adlarına göre bulur.

CSS teknik olarak kolaydır. Anlaşılması gereken sınırlı sayıda kural vardır. Bununla birlikte, CSS'i zorlaştıran potansiyel kural kombinasyonudur. Görsel gereksinimler daha karmaşık hale geldikçe, CSS kurallarınızın sürdürülebilirliğini kontrol altında tutmak için yaratıcı ancak yapılandırılmış çözümlere ihtiyaç vardır.

Tasarım yönleri pazarlamaya ve UX tasarımcısına bırakılabilirken, front-end geliştiricilerin tasarımın nasıl çalıştığını anlamaları da iyidir. Tasarımcıların tümü geliştirici değildir ve bazen tarayıcıların ve piksel rehberliğinin daha ince gereksinimlerini anlamayanlarla karşılaşıyoruz. Dijital tasarımcıların stil sayfalarının inceliklerini ve potansiyel karmaşıklığını öğrenmesi gerektiği kadar, tasarım dilinde de konuşabilmelisiniz.

### Kaynaklar


- https://levelup.gitconnected.com/what-is-css-specificity-and-how-it-works-833bb0b3d3a
- https://blog.isimtescil.net/css-nedir/
- https://medium.com/swlh/css-for-beginners-what-is-css-and-how-to-use-it-in-web-development-5985afe53096
- https://medium.com/madhash/what-exactly-is-css-d21d17f1031f
- https://www.vargonen.com/blog/css-nedir-css-kodlari-nelerdir/
- https://weebakademi.com/-html-sayfaya-css-ekleme.aspx

**Yukarıda anlatılanları aşağıda Codepen içerisinde deneyimleyebilirsiniz!**
<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/yLVeqNa?height=300&amp;theme-id=dark&amp;slug-hash=yLVeqNa&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_yLVeqNa"></iframe>

---

## Inline CSS Nasıl Kullanılır?

Özet: Elementin ilk tag'inin içine özellik belirt. Tanımlanacak özelliği yaz ve iki nokta koyarak değer ver. Ekstra tanımlamaları birbirinden ayırmak için de aralara `;` koy!

```html
<h1 style="color:crimson; font-size:30px;">css deneme</h1>
<p style="font-size: 20px; color:blueviolet">Lorem ipsum dolor sit amet.</p>
<p style="font-size: 20px; color:deeppink">Lorem ipsum dolor sit amet.</p>
```

![CSS Syntax](https://www.w3schools.com/css/img_selector.gif)

### Biraz daha derine inmek için:

https://tr.wikipedia.org/wiki/CSS
https://www.w3schools.com/css/css_syntax.asp
https://www.w3schools.com/css/css_colors.asp

---

## Inline(Etikete Özel), Internal(Aynı Dosyada) ve External(CSS Dosyasında) CSS Kullanımı

CSS, web sitenizin ekranda nasıl görüneceğini belirleyen belirli stil kurallarına sahip dosyalardır. CSS kuralları, web sitenizin HTML dosyalarına çeşitli şekillerde ve yerlerde uygulanabilir. External yani harici bir stil sayfası, Internal yani dahili bir stil sayfası veya Inline yani satır içi stil kullanabilirsiniz. Her yöntemin belirli kullanımlara uygun avantajları vardır.

External stil sayfası, bir web sayfasından bağlanan bağımsız bir `.css` dosyasıdır. External stil sayfasının avantajı, bir kez oluşturulabilmesi ve birden çok web sayfasına uygulanabilmesidir. Site tasarımınızda geniş çaplı değişiklikler yapmanız gerekirse eğer, stil sayfasında tek bir değişiklik yapabilirsiniz ve bu değişiklik tüm bağlantılı sayfalara uygulanarak zamandan ve emekten tasarruf sağlar.

![Internal Style Page](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/inlineetikete-ozel%2C-internalayni-dosyada-ve-externalcss-dosyasinda-css-kullanimi/figures/css-yapisi.jpg)

Internal stil sayfası, HTML dosyasının `<head>` bölümünde sayfa için CSS kural kodlarını barındırır. Kural kodları yalnızca o sayfa için geçerlidir, ancak sayfa kodunda birden çok öğeye stil uygulamak için kullanılabilecek class ve id’leri yapılandırabilirsiniz. Yine, CSS kodunda yapılacak tek bir değişiklik, sayfadaki tüm etiketlenmiş öğelere uygulanacaktır.

Inline stili, belirli bir sayfa öğesine stil vermek için, belirli bir HTML etiketi içinde kullanılır. Hızlı ve kalıcı değişiklikler için kullanışlıdırlar, ancak bir tasarım değişikliği yapmaya karar vermeniz durumunda, oluşturduğunuz her Inline stilin ayrı ayrı düzenlenmesi gerektiğinden, External ve Internal stil sayfalarından daha kullanışlı değildir ve diğerlerine göre çok fazla tercih edilmez.

### External CSS Kullanımı

Yukarıda bahsettiğimiz gibi External CSS, normal HTML dosyanızdan bağımsız bir dosyadır ve `.css` uzantılıdır. CSS dosyanızı oluşturduktan sonra mutlaka HTML dosyanıza linklemeniz gerekir. Yoksa CSS dosyanız işlevsiz kalacak ve HTML sayfanızda yaptığınız değişiklikleri göremeyeceksiniz. Hadi gelin bir de örnek üzerinde görelim.

`.css` uzantılı dosyamızı oluşturduktan sonra içine kodlarımızı bu şekilde yazıyoruz:

```css
body {
  background-color: #f7cac9;
}

.firstDiv, .secondDiv, .thirdDiv {
  border: 7px outset gold;
  background-color: lightblue;
  text-align: center;
}
```

Daha sonra HTML sayfamıza geri dönüyoruz ve yazdığımız bu External CSS kodunu `<head>` bölümüne aşağıdaki gibi linkliyoruz. İşte bu kadar. 

```css
<link rel="stylesheet" href="style.css">
```

### Internal CSS Kullanımı

Internal CSS, stil kodlarının direk HTML dosyasının içinde `<head>` bölümünde kullanıldığı bir yöntemdir. `<head>` bölümünün içinde bir `<style>` etiketi açtıktan sonra içine gerekli CSS kodlarını yazabilirsiniz.

**Örnek vermek gerekirse; kodunuz şu şekilde görünecektir:**

```html
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: #f7cac9;
}

.firstDiv {
  border: 7px outset gold;
  background-color: lightblue;
  text-align: center;
}
</style>
</head>
<body>
<div class="firstDiv">
  <h2>Lorem ipsum</h2>
  <p>Lorem ipsum dolor sit amet consectetuer</p>
</div>
</body>
</html>
```

### Inline CSS Kullanımı
Inline yani satır içi stiller, doğrudan HTML kodunuzdaki herhangi bir öğeye uygulanır. Stil niteliği ve ardından normal CSS özellikleri bir HTML etiketi içinde belirtilir. Kullanımı aşağıdaki örnekte gösterildiği gibidir:

```html
<!DOCTYPE html>
<html>
<head>
</head>
<body>
<div style="border-width:7px; border-style:outset; border-color:gold; background-color:lightblue; text-align:center;">
  <h2>Lorem ipsum</h2>
  <p>Lorem ipsum dolor sit amet consectetuer</p>
</div>
</body>
</html>
```

#### Ekstra Alıştırmalar:
- [Alıştırma 1](https://www.w3schools.com/css/exercise.asp?filename=exercise_howto2)
- [Alıştırma 2](https://www.w3schools.com/css/exercise.asp?filename=exercise_howto3)
- [Alıştırma 3](https://www.w3schools.com/css/exercise.asp?filename=exercise_howto4)


### Internal CSS Example
<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/LYbGBZr?height=300&amp;theme-id=dark&amp;slug-hash=LYbGBZr&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_LYbGBZr"></iframe>


### Inline CSS Example
<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_2" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/gOLPjwN?height=300&amp;theme-id=dark&amp;slug-hash=gOLPjwN&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_2" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_gOLPjwN"></iframe>


#### Kaynaklar
- https://www.w3schools.com/css/exercise.asp?filename=exercise_howto2
- https://www.w3schools.com/css/exercise.asp?filename=exercise_howto3
- https://www.w3schools.com/css/exercise.asp?filename=exercise_howto4
- http://zinzinzibidi.com/web_tasarim/css3/css_in_yapisi
- https://varvy.com/inline-small-css.html

---

## Açıklama Satırları ile Çalışmak ve Genel Font Özellikleri

### Açıklama Satırları
Açıklama satırları CSS kodu yazarken aralara kendimiz ve diğer yazılımcılar için notlar bırakmamızı sağlar. Açıklama satırlarının önemi kodda güncelleme yapılacığı vakit anlaşılmaktadır. Örnek olarak 5000 satır css kodunuz olduğu düşünün, kodu yazdıktan 1 yıl sonra değişiklik yapmak istediğimizde nerede ne yazdığınızı hatırlamamız çok zordur. Bunun için açıklama satırlarını okuruz ve bulmak istediğimiz yerleri daha kolay buluruz. Açıklama satırları tarayıcılar tarafından görünmemektedir.

CSS'de açıklama satırı bu şekilde başlar `/*` ve bu şekilde biter `*/`

**Örneğin:**
```css
     /* Tekli yorum satırı */
    p {
       color: red;
      }
```

Kodda istediğiniz yere yorum satırı ekleyebilirsiniz:
```css
p {
     color: red;  /* Metin rengini kırmızı yap*/
     }
```

Yorumları birden çok satıra da yazabilirsiniz:
```css
 /* Çoklu yorum
     satırı bu 
     şekilde */
    p {
      color: red;
    }
```

### Genel Font Özellikleri
CSS'de beş genel yazı tipi ailesi vardır:

1. **Serif** yazı tiplerinin her harfin kenarlarında küçük bir kontur vardır. Bir formalite ve zarafet duygusu yaratırlar.
2. **Sans-serif** yazı tiplerinin temiz satırları vardır (küçük konturlar eklenmez). Modern ve minimalist bir görünüm yaratırlar.
3. **Monospace** yazı tipleri burada tüm harfler aynı sabit genişliğe sahiptir. Mekanik bir görünüm yaratırlar.
4. **Cursive** yazı insan el yazısı taklidi gibidir.
5. **Fantasy** yazı tipleri dekoratif, eğlenceli yazı tipleridir.
Tüm farklı yazı tipi adları, genel yazı tipi ailelerinden birine aittir.

**Not:** Bilgisayar ekranlarında, sans-serif yazı tiplerinin serif yazı tiplerinden daha kolay okunabileceği kabul edilir.


#### CSS'de, `font-family` özelliğini bir metnin yazı tipini belirtmek için kullanırız.

**Not:** Yazı tipi adı birden fazla kelime ise, "Times New Roman" gibi tırnak içinde olmalıdır.
```css
    .p1 {
     font-family: "Times New Roman";
    }

    .p2 {
     font-family: Arial;
    }

    .p3 {
     font-family: monospace;
    }
```

**`font-style` çoğunlukla italik metnini belirtmek için kullanılır.**

- *normal*: Metin normal şekilde gösterilir.
- *italic*: Metin italik olarak gösterilir.
- *oblique*: Metin eğimli gösterilir ama çok desteklenmiyor.

**CSS'de `font-size` metnin boyutunu ayarlar.**
Metin boyutunu yönetebilmek web tasarımında önemlidir. Bununla birlikte, paragrafların başlık gibi veya başlıkların paragraflara benzemesi için yazı tipi boyutunu ayarlamalısınız. Bunun içinde `font-size` kullanılır.

**Not:** Bir yazı tipi boyutu belirtmezseniz, paragraflar gibi normal metin için varsayılan boyut 16 pikseldir (16px = 1em).
```css
     h1 {
      font-size: 40px;
     }
    
     h2 {
      font-size: 30px;
     }

     p {
      font-size: 14px;
     }
```
#### Em ile Yazı Tipi Boyutunu Ayarla
Kullanıcıların metni yeniden boyutlandırmasına izin vermek için (tarayıcı menüsünde), birçok geliştirici piksel yerine em kullanır.

1em, mevcut yazı tipi boyutuna eşittir. Tarayıcılarda varsayılan metin boyutu 16 pikseldir. Yani, 1em'in varsayılan boyutu 16 pikseldir.
```css
     h1 {
      font-size: 2.5em; /* 40px/16=2.5em */
     }

     h2 {
      font-size: 1.875em; /* 30px/16=1.875em */
     }  

     p {
      font-size: 0.875em; /* 14px/16=0.875em */
     }
```
Yukarıdaki örnekte, em içindeki metin boyutu, piksel cinsinden önceki örnekle aynıdır. Ancak em boyutu ile tüm tarayıcılarda metin boyutunu ayarlamak mümkündür.


#### Kaynaklar
- [Yorum Satırı](https://www.w3schools.com/css/css_comments.asp)
- [Font-Family](https://www.w3schools.com/css/css_font.asp)


---

## Class ve ID Kullanımı
Web sayfamızı oluştururken HTML elementlerimize bazı stil özellikleri eklemek isteriz. Bazı yazıların renkli, bazı resimlerin küçük veya bazı butonların farklı şekilde olması gerekebilir ve biz de bunun için CSS kullanırız.

Aşağıda html elementlerine nasıl stil özellikleri eklediğimize bakalım.

``` 
<p>Bugün kodluyoruz</p>
<p>Yarın da kodluyoruz<p>
p {
	color: red;
}
```
**Sonuç:**
![Çıktı](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/css-ile-class-ve-id-kullanimi/assets/Screenshot_1.jpg)

Yukarıda görüldüğü üzere iki farklı `<p></p>` elementimize kırmızı renk özelliği eklemiş olduk. Fakat sadece belirli `<p></p>` elementine istediğimiz herhangi bir özelliği eklemek istersek ne yapacağız? Bu durumda `class` veya `id` seçicilerini kullanmamız gerekiyor.

### `class` Kullanımı
Class seçicisi, HTML üzerinde aynı class’a sahip elemana ulaşmamızı sağlar.

Class seçicisi CSS’de `.` ile belirtilir.
```
.class{
     özellikler
}
<h4>Birinci Başlık</h4>
<h4>İkinci Başlık</h4>
<h4>Üçüncü başlık</h4>
```
Yukarıda 3 adet `<h4></h4>` elementimiz bulunuyor. Bunlardan sadece ikincisine kırmızı renk özelliği eklemek istersek class seçicisini kullanabiliriz.
```
<h4>Birinci Başlık</h4>
<h4 class="text-red">İkinci Başlık</h4>
<h4>Üçüncü Başlık</h4>
```
Daha sonra bunu istediğimiz özelliği ekleyelim.
```css
.text-red{
   color:red;
}
```
**Sonuç:**
![Çıktı](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/css-ile-class-ve-id-kullanimi/assets/Screenshot_2.jpg)

Bir class’ı birden fazla HTML elementi için kullanabiliriz.

```
<h4>Birinci Başlık</h4>
<h4 class="h-green">İkinci Başlık</h4>
<h4 class="h-green">Üçüncü Başlık</h4>

.h-green {
   color:green;
}
```
**Sonuç:**
![Çıktı](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/css-ile-class-ve-id-kullanimi/assets/Screenshot_3.jpg)

Eğer bir HTML elementinin birden fazla class özelliğine sahip olmasını istiyorsak aynı anda iki farklı class’ı kullanabiliriz. Bunun için sadece iki class arasına boşluk bırakmak yeterli olacaktır.

```
<h4>Birinci Başlık</h4>
<h4 class="h-blue">İkinci Başlık</h4>
<h4 class="h-blue thick">Üçüncü Başlık</h4>

.h-blue{
    color:blue;
}
.thick{
       font-style: italic;
}
```
**Sonuç:**
![Çıktı](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/css-ile-class-ve-id-kullanimi/assets/Screenshot_4.jpg)

Bir HTML elementi kendini kapsayan elementin (parent elementi) stil özelliklerine sahip olur.

```
<div class="intro"><p>Birinci Paragraf</p><p>İkinci Paragraf</p>

</div>
.intro{
    color:pink;
 }
```
**Sonuç:**
![Çıktı](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/css-ile-class-ve-id-kullanimi/assets/Screenshot_5.jpg)

Yukarıda `<div></div>` elementine CSS özelliği ekledik fakat altındaki elementler (child elementleri) de bu özelliğe sahip oldu.


### `id` Kullanımı
ID seçicisi, HTML üzerinde aynı id’ye sahip elemana ulaşmamızı sağlar.

ID seçicisi CSS’de `#` ile belirtilir.

ID seçicisinin kullanım amacı olarak class seçicisinden bir farkı yok diyebiliriz. İkisi de belirli HTML elementlerine CSS özellikleri eklemeye yöneliktir. Fakat id seçicisinin class seçicisinden bazı farkları vardır.
```css
#id {
     özellikler
}
```
Bir id’yi sadece bir HTML elementi üzerinde kullanabiliriz.

**Sonuç:**
![Çıktı](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/css-ile-class-ve-id-kullanimi/assets/Screenshot_6.jpg)

Aşağıdaki **yanlış** bir kullanımdır!
```
<p id="title">Birinci paragraf</p>
<p id="title">İkinci paragraf</p>
```
Bir html elementinin sadece bir tane id’si olabilir.

Aşağıdakiler **yanlış** kullanımlardır.
```
<p id="title" id="text-green">Birinci paragraf</p>
<p id="title text-blue">İkinci paragraf</p>
```
Böyle kullanımlar **geçerli değildir.**

#### Kaynaklar
- [W3Schools](https://www.w3schools.com/)
- [What is CSS Specificity and How Does it Work?](https://levelup.gitconnected.com/what-is-css-specificity-and-how-it-works-833bb0b3d3a)

---

## CSS Ödev 1
![CSS Ödev 1](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/odev1/figures/htmlcssjs.png)

Herkese merhaba arkadaşlar kanalımıza hoş geldiniz, bugün HTML sayfamıza hafif bir makyaj yapacağız. Komik gelse de aslında tam olarak böyle yapacağız. Bir HTML sayfası oluşturup buna CSS ile tasarımsal açıdan güzellikler katacağız, HTML sayfamıza güzelliği getireceğiz.

- HTML sayfasını sıfırdan oluşturacaksınız. Eklemek istediğiniz ekstra özellikler tamamen size kalmış durumda.
- Sitemiz birkaç sayfadan oluşacak. Yani menü kısmında linkler vererek başka sayfaya geçilebilecek.
- Renkler tamamen sizin zevkinize kalmış durumda. Fakat renkler konusunda biraz yardım almak isterseniz Colorhunt renk paletleri konusunda muazzam bir site.
- Yazacağınız CSS etiketlerini Inline ve Internal yazabilirsiniz. External kullanmak tamamen sizin tercihinizdir.
- CSS yazarken noktalı virgülleri unutmayın. Biliyorum unutacaksınız, olur böyle şeyler...
- CSS ile ilgili yardımcı kaynak için w3schools.com'un CSS tutorialını, Türkçe kaynak için Fatih Hayrioğlu'nun web sitesini kullanabilirsiniz.
- Kendini tekrar eden yapılar kullanmamaya özen gösteriniz. Ya da kendini tekrar eden yapılarda kullandığımız özelliği kullanın. (İpucu: Inline(Etikete Özel), Internal(Aynı Dosyada) ve External(CSS Dosyasında) CSS Kullanımı)
- Sayfalarınızda kullandığınız fontlar için daha önce de videolarda bahsettiğimiz Google Fonts'u kullanabilirsiniz.
- Ana sayfada bulunan listelerin noktalarını ortalamak için `list-style-position: inside`'i kullanabilirsiniz.
![Örnek Önizleme](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/odev1/figures/webpage.gif)

Bu ödevde sizlerden istediğimiz hayal gücünüzü kullanarak öğrendiğiniz ve araştırarak bulduklarınızla birlikte güzel bir site oluşturmanız. Burada oluşturduğumuz sitenin tasarımı hoşunuza gitmese dahi burada önemli olan nokta CSS elemanlarını efektif bir şekilde kullanabiliyor muyuz onu görmek. Tasarımı ilerleyen ödevlerde daha güzelleştireceğiz.

Hepinize başarılar, kolay gelsin.

Benim yaptığım site:
![odev-6-sayfamiza-biraz-makyaj-yapalim](https://github.com/cantuncr/front-end/blob/main/Patika.dev/frontend101/frontend101-odevler-kodluyoruz-patika.dev/css/odev-6-sayfamiza-biraz-makyaj-yapalim/img/odev-6-sayfamiza-biraz-makyaj-yapalim-kendi-sitem-onizleme.jpg?raw=true)

## Kodlar:
**anasayfa.html:**
```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Müzik Dükkanım</title>
    <!-- Google Fonts'dan font linklendi! -->
    <link rel="stylesheet" href="../css/styles.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@100;400&display=swap" rel="stylesheet">
</head>
<body>
    <header>
        <h1>Müzik Dükkanım</h1>
        <nav>
            <div class="container">  <!-- div içine alınıp container class'ı atandı, nesnelerin ortalanması biraz terletti! -->
                  <ul > <!-- Sayfalar birbirine linklendi! -->
                      <li class="li"><a href="anasayfa.html">Ana Sayfa</a></li>
                      <li class="li"><a href="urunlerimiz.html">Ürünlerimiz</a></li>
                      <li class="li"><a href="hakkimizda.html">Hakkımızda</a></li>
                  </ul>
            </div>
        </nav>
    </header>
    <h1 class="header-yellow"> Ana Sayfa</h1>
    <section>
       <article> <!-- Semantic yapı -->
            <p style="text-align: center">Müzik dükkanım sitemize hoşgeldiniz! Bu sitede çeşitli müzik aletlerini bulabilirsiniz. Uygun fiyatlarımız ve kaliteli ürünlerimiz için <a href="urunlerimiz.html">Ürünlerimiz</a> sayfamızı ziyaret edebilirsiniz.</p>
        </article>
    <h3 style="text-align: center">Sitemizde Bulunan Müzik Aletleri</h3>
        <ul style="color:white">
            <li class="li2">Gitar</li>
            <li class="li2">Davul</li>
            <li class="li2">Piyano</li>
            <li class="li2">Keman</li>
        </ul>
    </section>

    <!-- Telifsiz bir müzik dükkanı vidosu, video tag'i ile linklendi! -->
    <video data-testid="video-asset" style="width:100%;height:auto" src="https://media.istockphoto.com/id/1361003187/tr/video/lot-of-multicolored-electric-guitars-hanging-in-a-music-store-guitar-shop.mp4?s=mp4-640x640-is&amp;k=20&amp;c=L3zIvvRgSYe4L_pcdy9o81JRMS1yWKIC6CtORjYKeOM=" alt="Lot of Multicolored Electric Guitars Hanging in a Music Store, Guitar Shop - Royalty-free Müzik Mağazası Stok Videolar" controls="" controlslist="nodownload" autoplay="" loop=""></video>
</body>
</html>
```

**hakkimizda.html:**
```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hakkımızda</title>
    <link rel="stylesheet" href="../css/styles.css">
</head>
<body>
    <header>
        <h1>Müzik Dükkanım</h1>
        <nav>
            <div class="container">
                  <ul >
                      <li class="li"><a href="anasayfa.html">Ana Sayfa</a></li>
                      <li class="li"><a href="urunlerimiz.html">Ürünlerimiz</a></li>
                      <li class="li"><a href="hakkimizda.html">Hakkımızda</a></li>
                  </ul>
            </div>
        </nav>
    </header>
        <h1 class="header-yellow">Hakkımızda</h1>
            <p>Müzik Dükkanım 2022 yılında Can TUNÇER tarafından kurulmuştur. Çeşitli müzik aletlerini uygun fiyatlarla müzikseverlerle buluşturmak için kurulmuştur</p>

        <h3>Vizyonumuz</h3>
            <p>İnsanlara kaliteli müzik aletleri sağlamak. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Totam vel maxime facilis, quisquam ex tempora ad incidunt omnis molestias temporibus aspernatur, aliquam obcaecati. Provident quos velit ad tenetur accusamus dicta.</p>

        <h3>Misyonumuz</h3>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa est vero aliquam a pariatur iure esse officia fugiat! Ipsum distinctio minima delectus nemo qui, tempore omnis soluta perspiciatis asperiores deserunt velit consectetur repudiandae expedita porro?</p>
    <hr>
    <footer>
        <h3>İletişim:<a style="color: white; font-size:15px;" href="mailto:cantuncr@gmail.com"> Buradan mail atabilirsiniz...</a></h3>
    </footer>
</body>
</html>
```

**urunlerimiz.html:**
```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ürünlerimiz</title>
    <link rel="stylesheet" href="../css/styles.css">
</head>
<body>
    <header>
        <h1>Müzik Dükkanım</h1>
        <nav>
            <div class="container">
                  <ul>
                      <li class="li"><a href="anasayfa.html">Ana Sayfa</a></li>
                      <li class="li"><a href="urunlerimiz.html">Ürünlerimiz</a></li>
                      <li class="li"><a href="hakkimizda.html">Hakkımızda</a></li>
                  </ul>
            </div>
        </nav>
    </header>
    <h1 class="header-yellow">Ürünlerimiz</h1>
    <section>
        <div style="background-color: white; border: 3px solid black" class="container">
            <ol class ="myUL">
                <li ><img class="resimboyut" src="https://www.do-re.com.tr/yamaha-c40-klasik-gitar-natural-23b60ccf40f89fc11bf8f20e198c59ba-ebbe3ff57b8a28bc62933319c6375809-max-pp.jpg" alt="Yamaha C40 Klasik Gitar"><br><span>Yamaha C40 Klasik Gitar<strong> 4000 TL</strong></span></li>
                <li><img style="height:250px; width:120px;" class="resimboyut" src="https://cdn.akakce.com/z/fender-squier/squier-mm-strat-sabit-kopru-siyah-elektro.jpg" alt="Fender Squier MM Strat"><br><span>Fender Squier MM Strat<strong> 3000 TL</strong></span></li>
                <li><img class="resimboyut" src="https://st3.myideasoft.com/idea/cl/86/myassets/products/803/ludwig-evolution-maple-lcem622xbl-trans-blue-shell-set-bateri-10-12-14-14-16-22-4133-1.jpg?revision=1529675534" alt="bateri"><br><span>Ludwig Evolution Maple LCEM622XBL Trans Blue Shell Set Bateri </span><strong> 30000 TL</strong></li>
                <li><img class="resimboyut" src="https://cdn.cimri.io/image/1000x1000/yamahadtxkdijitalelektronikdavulbateri_162654004.jpg" alt="bateri"><br><span>Yamaha DTX402K Dijital Elektronik Davul Bateri</span><strong> 15000 TL</strong></li>
                <li><img class="resimboyut" src="https://www.do-re.com.tr/yamaha-gb1-akustik-kuyruklu-piyano-parlak-siyah-cce51c1f066f575b7d9a21f9f985bb02-12622d3632fb8eb8cb92c2028a5434e8-max-pp.jpg" alt="piyano"><br><span>Yamaha GB1 Akustik Kuyruklu Piyano</span><strong> 350000 TL</strong></li>
                <li><img class="resimboyut" src="https://m.media-amazon.com/images/I/816kFYPDFcL._AC_SL1500_.jpg" alt="piyano"><br><span>RockJam 88 Tuşlu Dijital Piyano</span><strong> 4000 TL</strong></li>
                <li><img class="resimboyut" src="https://www.do-re.com.tr/yamaha-v5sa-keman-4-4-4e855e101cf8655b377fea1f7aad4a24-48dd2ed057df03decf6b780aac8f0524-large-pp.jpg" alt="keman"><br><span>Yamaha V5SA Keman</span><strong> 13000 TL</strong></li>
                <li><img class="resimboyut" src="https://m.media-amazon.com/images/I/61EY44rU7sL._AC_SL1500_.jpg" alt="keman"><br><span>Stentor 1018/F Standart Keman</span><strong> 2500 TL</strong></li>
            </ol>
        <br>       
            <a href="#" class="top">↑ Yukarı Dön ↑</a> <!-- Tek tıkla yukarı dönmek için tıkla! -->
        </div>
    </section>
</body>
</html>
```

**styles.css:**
```css
body {
    background-image: url("https://rstatic.stores.musicarts.com/locations/3450_gonzales_la.jpg");
    backdrop-filter: blur(10px);
    font-family: 'Roboto', sans-serif;
}
/* Spektrumal renk geçişi */
h1, h2 {
    background-image: linear-gradient(to left, violet, indigo, blue, green, yellow, orange, red);   -webkit-background-clip: text;
    color: transparent;  
    text-align: center;
    font-size: 45px;
}
h3 {
    color:rgb(167, 16, 159);
}
ul {
    text-align: center;
}
a {
    color: rgb(231, 19, 150);
    font-size: 25px;
}
p {
    color:white;
}

/* Ortalama */
div.container {
    text-align: center;
  }
ul.myUL {
    display: inline-block;
    text-align: left;

  }
.header-yellow {
    color: rgb(240, 236, 10);
}
.resimboyut {
    width: 300px;
    height: 240px;
}
.li {
    color: rgba(83, 16, 83, 0.842);
    padding-inline: 50px;
    padding-block: 10px;
    display: inline-block;
    list-style: none;
}
.li2{
    list-style-position:inside;
}
.top {
    text-decoration: none;
    padding: 10px;
    font-family: sans-serif;
    color: #fff;
    background: #000;
    border-radius: 100px;
  }
```

---

## CSS Seçiciler ile Çalışmak, İstediğimiz HTML Etiket Yapısına Özelliklik Ekleyebilmek
CSS seçiciler, HTML taglarına ulaşarak biçim atamaları yapmamızı sağlar. CSS işlemleri, HTML tagı içinde `style` attribute kullanarak yani inline, `<head>` arasında `<style>` tagı kullanarak yani internal ya da dosya uzantısı .css olan bir dosya oluşturup bu dosyayı `<head>` arasına ekleyerek yani external şekilde kullanabiliriz.

### Inline
`<h1 style="color:orange;">Turuncu renkli başlık</h1>`

### Internal
```html
<head>
  <style>
    h1{
    color: orange;
    }
  </style>
</head>
<body>

<h1>Turuncu renkli başlık</h1>

</body>
```

### External
```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
```
`styles.css` dosyası:
```css
h1{
  color:orange;
}
```
Kısaca CSS kodlarımızı nasıl yazabileceğimizi öğrendikten sonra şimdi CSS seçicileri kullanarak nasıl HTML taglarına erişebiliyoruz onlara bakalım.

## Seçiciler
<iframe width="550" height="300" src="https://www.youtube.com/embed/iScCq-8OWSE" title="CSS Seçiciler ile Çalışmak, İstediğimiz HTML Etiket Yapısına Özellik Ekleyebilmek #6" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Genel seçici `*`
Bu seçiciyi kullanarak tüm etiketlere CSS uygula demiş oluyoruz.
```css
*{
  margin:0;
  padding:0;
}
div *{
  color:orange;
}
```
İlk kullanımda tüm elementlerin margin ve padding değerlerini sıfırlamış olduk. İkinci kullanımda `div *` diyerek tüm div elementleri içindeki elementlerin yazı rengine erişmiş olduk.

### Element Seçiciler (Element Selectors)
Bu seçiciler ile doğrudan HTML etiket isimlerini kullanarak CSS uygulayabiliriz.
```css
div{
  background-color: orange;
}
```
Tüm div etiketleri etkilenir.

### Sınıf Seçiciler (Class Selectors)
Bu seçiciler ile sınıf atadığımız etiketlere CSS uygulayabiliriz. Sınıf ismine erişmek için sınıf isminin başına nokta `.` ekliyoruz.
``` css
.turuncu{
  background-color: #FFA500;
}
p.mavi{
  color:blue;
}
 <p class="turuncu">Arka plan rengim turuncu</p>
 <div class="turuncu">Arka plan rengim turuncu</div>
```
Burada ikinci kullanımda p.mavi sınıf ismi mavi olan p elementlerine erişmiş olduk.

### Id Seçiciler (Id Selectors)
Bu seçiciler ile id atadığımız elementlere CSS uygulayabiliriz. Id' ler tek bir elemente ait olmalıdırlar. Id özelliğine erişmek `id`' nin başına `#` ekliyoruz.
```css
#mavi{
  background-color: #0000FF;
}
#lila{
  color: #c8a2c8;
}
 <p id="mavi">Arka plan rengim turuncu</p>
 <div id="lila">yazı rengim lila</div>
 ```

 ### Özellik Seçiciler (Attribute Selectors)
Bu seçiciler ile özelliğini belirttiğimiz elementlere CSS uygulayabiliriz. Özelliğin içi boş olsada element bundan etkilenecektir. Özelliklere erişmek için yapmamız gereken tek şey köşeli parantezler içinde özelliğin ismini `[attribute]` şeklinde yazıyoruz.
 ```
[name]{
  color: orange;
}
<button name="">gönder</button>
<ul>
      <li name="html">HTML</li>
      <li name="css">CSS</li>
</ul>
```
Bu şekilde name attribute alan tüm elementler etkilenir.

```
.btn[disabled] {
  color: orchid;
}
<button class="btn" disabled="disabled">Submit</button>
```
Burada sınıfı `.btn` ve niteliği(attribute) `[disabled]` olan butona CSS uyguladık.
```html
div[title="deneme"] {
  background-color: orange;
}
<div title="Deneme">Lorem, ipsum dolor.</div>
<div title="deneme">Lorem, ipsum dolor.</div>
<div name="denemefalan">Lorem, ipsum.</div>
```
Burada tam eşleşen özelliğe CSS uyguladık. Büyük-küçük harf duyarlılığı vardır.

```html
div[title~="isim"] {
  color: orange;
}
<div title="isim">Lorem, ipsum dolor.</div>
<div title="isimler">Lorem, ipsum dolor.</div>
<div title="isim ve şehirler">Lorem, ipsum dolor.</div>
```
Burada `~=` ifadesi ile `title` özelliği "isim" içeren divlere eriştik.

```html
a[href ^= "https"] {
  color: palegreen;
}
<a href="https://www.google.com/">google</a>
<a href="https://github.com/">github</a>
<a href="http://github.com/">github</a>
```
Burada `^=` ifadesi ile `href` özelliği "https" ile başlayan a etiketlerine eriştik.

```html
a[href *= "http"] {
  color: palegreen;
}
<a href="https://www.google.com/">google</a>
<a href="https://github.com/">github</a>
<a href="http://github.com/">github</a>
```
Burada `*=` ifadesi ile `href` özelliği "http" içeren a etiketlerine eriştik.

```html
div[class$="test"] {
  background: yellow;
}
<div class="bir_test">Lorem, ipsum dolor.</div>
<div class="iki-test">Lorem, ipsum dolor.</div>
<div class="uc test">Lorem, ipsum dolor.</div>
<div class="dorttest">Lorem, ipsum dolor.</div>
```
Burada `$=` ifadesi ile `class` özelliği sonunda "test" içeren divlere eriştik.

```html
a[href*="https"][href$="com"] {
        color: orange;
}
<a href="https://www.google.com/"> Google</a>
<a href="https://reactjs.org/">React.js</a>
<a href="https://css-tricks.com/">Css Tricks</a>
```
Burada `https` ile başlayan ve sonunda `com` olan `a` etiketlerine eriştik.

Artık ana hatlarıyla öğrendiğimiz CSS seçicilere daha yakından bakabiliriz.

## Grup Seçiciler (Group Selectors)
Çoğunlukla etiketlere verilen CSS özellikleri benzer veya ortak olabilir. Bu gibi durumlarda seçicileri gruplayarak daha temiz CSS dosyaları oluşturabiliriz.
```css
h1,h2,h3{
  color:orange;
}
```
Tüm `h1`, `h2`, `h3` etiketlerine erişmiş olduk.

```css
p.turuncu{
  color:orange;
}
<p class="turuncu">turuncu yazı</p>
<p>normal yazı</p>
```
Burada sınıf ismi `.turuncu` olan `p` etiketlerine ulaştık.

## Çocuk seçiciler (Child Selectors)
Artık etiketleri birbiriyle olan hiyerarşik durumuna göre seçerek CSS özelliklerini belirleyeceğiz. Child selector, kendisi ve kendisini sarmalayan bir üst etiketle olan ilişkiyi gösterir ve `>` işareti ile ifade edilir.
```css
p > span{
  color:orange;
}
p > span >b{
  color:blue;
}
div > ul >li#first{
  color:red;
}
<p>
  <span>child element</span>
</p>
```
Parent etiketi yani bir üst kapsayıcısı `p` olan `span` etiketine ulaştık.
```html
<p>
  <span>Burası turuncu renkte <b>mavi renkte yazılacak</b></span>
</p>
<p>
  <span>Burası turuncu renkte <b>mavi renkte yazılacak</b></span>
</p>
<div>
  <ul>
    <li id="first">bir</li>
    <li>iki</li>
  </ul>
</div>
```

## Torun-Soy Seçiciler (Descentad Selectors)
Bir kapsayıcı yani parent element altındaki tüm etiketlere ulaşmak için kullanılır. Her ulaşılacak etiket arasına boşluk konulur.
 ```css
div p{
  background-color:blue;
}
```
Burada div içinde olan tüm p etiketlerine ulaşırız.

```html
<div>
  <p>Bu p etiketi arka planı mavi renk</p>
  <ul>
    <li>
      <p>Bu p etiketi arka planı mavi renk</p>
    </li>
  </ul>
  <p>Bu p etiketi arka planı mavi renk</p>
</div>
```

## Genel Kardeş Seçiciler (General Sibling Selectors)
Aynı parent etikete sahip olan ve birbiri ardına gelen etiketleri seçmek için kullanılır. `AltGr+ü` Kambinasyonuyla oluşan `~` işareti ile gösterilir.
```html
ul ~ p{
  color:orange;
}
<div>
  <p>Lorem, ipsum.</p>
  <ul>
    <li>
      <p>Lorem, ipsum dolor.</p>
    </li>
  </ul>
  <h3>Lorem, ipsum dolor.</h3>
  <p>Bu p etiketi turuncu renkte</p>
</div>
```
Burada dikkat edilmesi gereken iki nokta var. Birincisi `<p>` etiketi `<ul>` etiketinden sonra gelmeli (arada başka etiketler olabilir) ve ikiside aynı düzeyde yani aynı parent etiketine sahip olmalılar.


## Bitişik Kardeş Seçiciler (Adjacent Sibling Selector)
Genel kardeş seçiciden tek farkı belirtilen etiketler bitişik arka arkaya gelmeliler. `+` işareti ile gösterilir.
```html
ul + p{
  color:green;
}
<div>
  <p>Lorem, ipsum.</p>
  <ul>
    <li>
      <p>Lorem, ipsum.</p>
    </li>
  </ul>
  <p>Bu p etiketinin yazı rengi yeşil</p>
</div>
```

## Sahte Sınıf Seçiciler (Pseudo classes)
Sahte sınıflar kullanarak HTML etiketlerine CSS uygulayabiliriz. Kullanımları `selector:pseudo class{}`şeklindedir.

## `:link`
Daha önce tarayıcıda açılmamış linke CSS uygular. Not: Etkisini görmek için tarayıcıya geçmişi temizlemek gerekebilir.
```css
a#google:link {
  color: red;
}
<a id="google" href="https://www.google.com/">Google</a>
```

## `:hover`
Seçici ile işaretlenen etiketin üzerine mouse ile gelindiğinde CSS uygalanır ve mouse üzerinde değilken etki kaybolur.
```css
a.test:hover {
  color: red;
}
<a class="test" href="https://www.github.com/">Github</a>
```

## `:active`
Mouse ile tıklandığında CSS uygulanır. Tıklama kaldırıldığında etki kaybolur.
```css
a:active {
  position: relative;
  top: 5px;
}
<a href="#">Submit</a>
```

## `:first-child`
İlk child etikete CSS uygulanır.
```html
ul > li:first-child {
  color: orange;
}
<ul>
<li>lorem</li>
  <li>lorem</li>
  <li>lorem</li>
  <li>lorem</li>
</ul>
```

## `:last-child`
Son child etikete CSS uygular.


## `::first-letter`
Blok seviyesinde bir etiketteki ilk harfe CSS uygular. `<span>` blok seviyesinde bir etiket olmadığından bu pseudo class uygulanamaz.
```css
p::first-letter {
  font-size: 20px;
  color: orange;
}
<p>Lorem ipsum dolor sit.</p>
```

## `::first-line`
Blok seviyesinde bir etiketin ilk satırına CSS uygular.


## `::before`
Belirtilen etiketin önüne CSS uygular.
```css
p::before {
  content: "selam";
  color: orange;
}
<p>Lorem ipsum dolor sit.</p>
 
```

## `::after`
Belirtilen etiketin sonuna CSS uygular. Kullanımı `::before` ile aynıdır.



#### Bölüm Sonu Minik Notlar
 ```
.color-coral.fw-normal {
    color: coral;
    font-weight: normal;
} /* Bu iki class'a aynı anda sahip olunca işler! */
--------------------------------------------------------------
<h2 class="color-coral fw-normal">Lorem, ipsum dolor.</h2>

```

 ```
.color-coral .fw-normal {
    color: coral;
    font-weight: normal;
} /* Arada boşluk olunca ise ilk class'a sahip elementin içinde, ikinci class'a sahip bir element içeren yapı olması halinde işler! */
-------------------------------------------------------------------
<h1 class="color-coral">Lorem.<span class="fw-normal">Lorem.</span></h1>
 ```

 ```
 ul > li:first-child {
    color:green;
} /* İlk nesneye işler! */

ul > li:last-child {
    color:green;
} /* Son nesneye işler! */
-------------------------------------------------------------------
    <ul>
        <li>Lorem.</li>
        <li>Sed.</li>
        <li>Atque.</li>
        <li>Ratione.</li>
        <li>Eligendi.</li>
        <li>Fuga.</li>
        <li>Aliquid?</li>
    </ul>
 ```

 ```
 li:nth-child(2) {
    color: blueviolet;
} /* Barındırdığı elemanlardan 2.'sini mor yap! */

li:nth-child(odd) {
    color: blueviolet;
} /* Tekleri mor yap! */

li:nth-child(even) {
    color: yellow;
} /* Çiftleri sarı yap! */

li:nth-child(3n) {
    color: aqua;
} /* n=0,1,2,3,.. için aqua yap! (2n+1 / 5n-3 / ...) */
-------------------------------------------------------------------
    <ul>
        <li>Lorem.</li>
        <li>Sed.</li>
        <li>Atque.</li>
        <li>Ratione.</li>
        <li>Eligendi.</li>
        <li>Fuga.</li>
        <li>Aliquid?</li>
    </ul>
 ```

#### Kaynaklar
- https://www.w3schools.com/cssref/css_selectors.asp
- https://css-tricks.com/almanac/selectors/

---

## CSS Kutu Özellikleri(Margin, Padding, Width, Height) Kullanımı

### CSS Kutu Modeli
![CSS Kutu Modeli](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/css-kutu-ozelliklerimargin%2C-padding%2C-width%2C-height-kullanimi/figures/box.png)

Resimde [Kodluyoruz'un anasayfasını](https://kodluyoruz.org/) görüyoruz. İşaretlediğim alanlar birer HTML elementleri ve bir yapıyı oluşturan lego parçalarından sadece birkaçı. Kutu denmesinin sebebi de bir bütünü oluşturan lego parçaları veya kutu gibi olması. Bu kutuların aralarında mesafelerin ve içeriklerinin de kendi aralarında bir düzen olduğunu görmekteyiz. Bunun sebebi "kutu özelliklerinin" kullanılıyor olması. Özellikle yeşil kutuların içindeki yazıların belli bir mesafede olmasından ve çizdiğim yeşil hatlara değmemesinden anlayabiliriz.

**Burada kutu modelini şema halinde göstereceğim:**
![Kutu Modeli](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/css-kutu-ozelliklerimargin%2C-padding%2C-width%2C-height-kullanimi/figures/boxmodel_.png)

**Kutu modeli margin,padding,border ve içerikten oluşur.**

- **İçerik(Content)**: Elementin içinde olan resim, ses ya da yazıdır.
- **Padding**: İçerik ile border arasında olan boşluk.
- **Border**: Padding ile margin'i ayıran sınırdır.
- **Margin**: Kutunun diğer kutularla arasındaki mesafeyi ayarlayan boşluk.

Yukarıda saydığım kavramların dışında kutunun boy ve uzunluğunu belirleyen width ve height kavramları vardır.

### `width` ve `height`
`width` ve `height` özellikleri ile elementin, yani lego parçamızın boy ve genişliğini ayarlayabiliriz. Bu özellikleri biz yazmadığımız takdirde tarayıcı kendisi ayarlar ve yapacağımız web uygulamasında istenmeyen sonuçlara neden olur :)Bu özellikleri `px`, `em` veya `%` ile kullanabiliriz. `%` ile kullandığımız zaman elementimiz hangi elementin içindeyse ona göre oranlanır. Yani `800px` boyunda bir `<div>` tag'inin içinde bulunan bir elementin boyunu `50%` olarak ayarlarsanız elementin boyu `400px` olur.

`Max-width` özelliği ise bir elementin genişliğini sınırlamak istediğimizde kullanırız. Diyelim ki bir element tarayıcı ekranından fazla geniş veya uzun. Bu durumda scrollbar(kaydırma çubuğu) çıkar.

### Alıştırma-1: Width ve Height Kullanımı
``` css
<style>
   p{
   width: 0;
   height: 0;
   }
<style>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</p>
```

Bu kodda `width` ve `height`'i `0` yaptım. Paragraf tuhaf bir şekilde görünecektir. Bu alıştırmada yapmanız gereken şey paragrafın düzgün görünmesi açısından `width` ve `height`'i istediğiniz şekilde kullanın. Burada `width` ve `heigth`'i görmeniz için `%` ve `px` in ikisini de kullanmanızı tavsiye ediyoruz..

## `margin` ve `padding`
### `margin`
Margin özelliği ile elementin dışında boşluk oluşturmada kullanıldığını öğrenmiştik. Şimdi nasıl kullanıldığını açıklamaya çalışacağız.

`margin` özelliğini `50px` yaptığınızda elementin dört yanında `50px` boşluk oluşturulur. Element sağa doğru kayar. `Negatif` değerler de kullanılabilir. `margin` değerine `-50px` yazdığınız takdirde element sola doğru kayacaktır.
Dört yanında değil de sadece bir yönde boşluk oluşturmak isteyebilirsiniz. Bunun için de özellikler vardır.

- `margin-left`: Soldan boşluk bırakır.
- `margin-top`: Yukarıdan boşluk bırakır.
- `margin-bottom`: Aşağıdan boşluk bırakır.
- `margin-right`: Sağdan boşluk bırakır.
- 
Bu değerleri tek bir satırda ayarlamanız mümkündür.
```css
margin: 100px 150px 60px 50px;
```

Bir elementi ortalamak için `margin:auto` değeri vermelisiniz. Bunun düzgün çalışması için de width özelliğinin de kullanılmasını öneririm. Böylelikle sağdan ve soldan eşit olarak ortalanmış olur. Aksi halde boyutu belli olmayan bir kutuyu ortalamayabilir.


### `padding`
Şimdi gelelim padding özelliğine. Elementin içindeki yazıların çerçeve(border) ile mesafesini `padding` ile ayarlarız. `margin` özelliğinde olduğu gibi `padding:50px` yaptığımızda içeriğin her tarafı için `50px` boşluk bırakıyoruz. Belirli bir tarafta `padding` bırakmak için;

- `padding-top`: içeriğin yukarısında boşluk bırakır.
- `padding-bottom`: içeriğin aşağısında boşluk bırakır.
- `padding-left`: içeriğin solunda boşluk bırakır.
- `padding-right`: içeriğin sağında boşluk bırakır.
- 
Bunları tek tek tanımlamak yerine tek bir satırda belirlemek mümkündür.
```css
padding: 10px 20px 30px 40px;
/* Burada üst boşluk 10px,sağ boşluk 20px,alt boşluk 30px ve sol boşluk 40px dir.*/
padding: 10px 20px 30px;
/* Üst boşluk 10px,sağ ve sol boşluk 20px,alt boşluk 30px dir. */
padding: 10px 20px;
/* üst ve alt boşluk 10px,sağ ve sol boşluk 20px */
```

#### Alıştırma 2-Kutu Özelliklerinin Kullanımı
Alıştırmaya aşağıdaki Codepen'den ulaşabilirsiniz.

Alt alta sıralayalım!

<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/RworBBX?height=300&amp;theme-id=dark&amp;slug-hash=RworBBX&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_RworBBX"></iframe>


Biraz da kutular ile uğraşalım:

<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_2" scrolling="no" src="https://codepen.io/Kodluyoruz/embed/preview/JjbGedp?height=300&amp;theme-id=dark&amp;slug-hash=JjbGedp&amp;default-tab=css%2Cresult&amp;user=Kodluyoruz&amp;embed-version=2&amp;preview=true&amp;editable=true&amp;name=cp_embed_2" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_JjbGedp"></iframe>

### Ekstra: (Ders Kodları)
***html:***
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="left-bar">
            <h1>left bar</h1>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit.
        </div>
        <div class="content">
            <div class="card">
                <h2>Lorem, ipsum dolor.</h2>
                <p>Lorem ipsum dolor sit amet.</p>
                <a href="" class="gradient btn">Başvur..</a>
            </div>
            <div class="card">
                <h2>Libero, fuga molestiae?</h2>
                <p>Cum odio amet sint nesciunt?</p>
            </div>
            <div class="card">
                <h2>Voluptatibus, deserunt temporibus!</h2>
                <p>Inventore nesciunt similique alias ad.</p>
            </div>
        </div>
    </div>
</body>
</html>
```

***css:***
```css
body {
    margin: 0;
    padding: 0;
}
.gradient {
    background: linear-gradient(135deg,rgba(112,73,186,0.6785938262939453),rgba(233,80,149,0.3910938262939453))!important;
}
.btn {
    padding: 10px 20px;
    border-radius: 35px;
    color: white;
    text-decoration: none;
    box-shadow: 10px 10px 5px -3px rgba(0,0,0,0.52);
    -webkit-box-shadow: 10px 10px 5px -3px rgba(0,0,0,0.52);
    -moz-box-shadow: 10px 10px 5px -3px rgba(0,0,0,0.52);
}
.container {
    width: 1000px;
    /* margin-left: auto;
    margin-right: auto; */
    /* margin: 0 auto 0 auto; yukarı aşağı sağ sol */
    margin: 50px auto 0; /* önce y ekseni sonra x ekseni */
    /* yukarıdan 50 sağdan-soldan oto- aşağıdan 0 */
}
.left-bar {
    width: 200px;
    float: left;
}
.content {
    width: 800px;
    float: left;
}
.card {
    width: 20%;
    float: left;
    padding: 5%;
    margin-right: 3%;
    background-color: aqua;
    border-radius: 10px;
}
.clear {
    clear: both;
}
.box {
    width: 300px;
    height: 300px;
    padding: 10px;
    /* margin: 10px; */
    /* margin-top: 10px; */
    /* margin-bottom: 10px; */
    margin-right: 10px;
    float: left;
}
.bg-red {
    background-color: red;
}
.bg-green {
    background-color: green;
}
.bg-yellow {
    background-color: yellow;
}
```
---

## CSS - Ödev 2
## Google Ana Sayfasını Tasarlamak
Hepimiz her gün Google kullanıyoruz ve çok işimize yarıyor değil mi? Her gün Google'da milyonlarca arama yapılıyor ve hatta siz de bu sayfaya gelmek için Google'ı kullanmış olabilirsiniz. Peki Google'ın geçmişten günümüze nasıl geliştiğini hiç merak ettiniz mi?

[Google](https://tr.wikipedia.org/wiki/Google) 1996 yılında kuruldu ve ilk versiyonunu 1998 yılında yayınladı. 1998, çok uzun bir süre önce değil mi? İlk versiyonu ile şu anki versiyonu arasında büyük fark var tabii ki. Peki size Google'ın ilk versiyonunu gösterebileceğimizi söylesek ne hissederdiniz?

İnternetteki gelmiş geçmiş bütün web sitelerini görebileceğiniz Wayback Machine adında bir web arşivi bulunmakta. [Google 1998](https://web.archive.org/web/19981202230410if_/http://www.google.com/) linkinden Google'ın ilk versiyonu nasılmış görebilirsiniz. Oldukça garip öyle değil mi? Garip olmasının yanında bu sizin HTML bölümündeki üçüncü ve son ödeviniz olacak. Bu sayfayı tasarlamanızı istiyoruz.

![Google-1998](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/cssodev3/figures/googlehomepage.png)

- Bu sayfada şu ana kadar öğrendiğiniz her şeyi kullanabilirsiniz. Bu sizin HTML becerilerinizi oldukça iyi bir şekilde geliştirmenizi sağlayacaktır.
- Butonların çalışmaması hiç sorun değil. Sadece tasarımsal olarak bu görüntüye benzesin ve aşağıdaki linkler çalışıyor olsun yeterli.
- Tasarladığınız bölümler ile alakalı kodunuzda açıklama satırlarına yer veriniz.
- Sayfa ile alakalı detaylara sayfanın üzerine sağ tıklayıp "İncele/Inspect" diyerek ulaşabilirsiniz.
- Bu [logo](https://web.archive.org/web/19990504112211im_/http://www.google.com/google.jpg)'yu kullanabilirsiniz.

İleride göreceğimiz CSS'den sonra Google'ın bugünkü halini de tasarlayacağız. Ama öncelikle bakalım Larry Page ve Sergey Brin başlangıçta nasıl yapmışlar!

### Kaynaklar
- https://tr.wikipedia.org/wiki/Google
- https://web.archive.org/

---

# CSS - Ödev 3
## Google Ana Sayfasını Tasarlamak
Bir zamanlar basit ama gururlu bir Google Ana Sayfası vardı, hatırladınız mı? Yıllaar yıllar geçti ve o ana sayfa gelişti, serpildi ve bugünkü halini aldı. HTML'in son ödevinde Google'ın ilk tasarımı üzerinde çalışmıştık ve CSS bölümünde günümüzdeki halini tasarlayacağımızı söylemiştik. Evet, o gün bugündür arkadaşlar. Bu ödevde Google'ın bugünkü ana sayfasını tasarlayacağız.

Sizler için HTML yapısını ve basit CSS'i hazırladık. Sizlerden istediğimiz orijinali inceleyip detayları işlemeniz.

![ÖdevProjeİlkHal](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/odev2/figures/googlehomepage.gif)

[Google Homepage Projesi](https://github.com/Kodluyoruz/taskforce/tree/main/css/odev2/google_homepage)'ne buradan erişebilirsiniz.

Projeyi indirdikten ya da cloneladıktan sonra Visual Studio Code programında LiveServer eklentisi ile açmanızı öneririz.

[Google Ana Sayfa](https://web.archive.org/web/20191130234759if_/https://www.google.com/) için arşiv linkini kullanabilirsiniz ya da  [Google](https://www.google.com/)'ın şimdiki ana sayfasını kullanabilirsiniz.

Bu ödevi yapabilmeniz için bolca "İncele/Inspect"'ten yararlanmanız gerekecektir. Sayfadayken sayfaya sağ tıklayıp "İncele/Inspect" demeniz yeterlidir.

Fark ettiyseniz logo eski bir Google logosu. Bu logoyu günümüzde logo ile değiştirmelisiniz. Kullanmanız gereken logo assets klasöründe bulunmakta.

Üstteki alanı sağ tarafa alın ve fotoğrafı kendi fotoğrafınız ile değiştirin ve fotoğrafın kenarlarını yarıçap özelliği ile düzenleyiniz.

Arama yapılacak alanın kenarlarını yarıçap özelliği ile düzenleyiniz.

Arama simgesi gibi sesle arama simgesini de siz ekleyin. (Nasıl yapıldığını görmek için Google Ana Sayfa'dan İncele ile yazılanları inceleyiniz.)

Arama alanında yazı yazılan yerin genişliği 480px olmalı ve kenarlığı olmamalı.

Buttonları ortaya alıp üstünden ve sağından boşluklar veriniz. Button kenarları 1px kalın #f2f2f2 renginde olmalı. Yazı tipi Arial, yazı rengi #5f6368, yazı boyutu 14px olmalı. Button yüksekliği 36px olmalı.

Buttonlara aynı arama alanında olduğu gibi gölge veriniz.

Footerda arkaplan rengini #f2f2f2 yapınız ve liste noktalarını ortadan kaldırın. (Bir önceki ödevde söylediğimiz [w3schools.com](https://www.w3schools.com/w3css/defaulT.asp)'un CSS tutorialını, Türkçe kaynak için [Fatih Hayrioğlu](https://fatihhayrioglu.com/)'un sitesini kullanabilirsiniz.)

CSS dosyasında kullanılan bütün elementleri araştırıp ne işe yaradıklarını öğrenin. Daha sonra bunları kullanabileceğiniz projelerinizde kullanmaya özen gösterin.

Tasarımı mümkün olduğunca benzetmeniz gerekmekte. Buttonların, arama kısmının çalışmaması önemli değil.

Kod yazarken yorum satırları kullanmaya özen gösteriniz. ödevin indirilebilir içeriklerine buradan ulaşabilirsiniz.

![ÖdevFinalGörüntü](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/css/odev2/figures/googlehomepage.png)

#### Benim Kodlarım:

***html:***
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="./css/style.css">
    <title>Google</title>
  </head>
  <body>



<!------------------------ ÜST KISIMDAKİ NAV BAR (GMAIL, IMAGES, APPS, PP) ------------------------>

    <div class="panel">
      <nav>
        <ul class="header">    
          <li style="margin: 8px" class="headerli">
            <a href="https://mail.google.com/mail/?tab=wm&authuser=0&ogbl"
              >Gmail</a
            >
          </li>
          <li style="margin: 8px; margin-left: -2px;" class="headerli">
            <a
              href="https://www.google.com.tr/imghp?hl=en&tab=wi&authuser=0&ogbl"
              >Images</a
            >
          </li>
          
          <li style="margin: 8px" class="headerli">
            <a href="https://www.google.com.tr/intl/en/about/products?tab=wh"
              ><img src="./assets/appsbutton.svg" alt="" style="width: 16px; height: 16px; margin-right: 3px;"></a
            >
          </li>
          <li class="pic headerli">
            <a href="https://github.com/cantuncr" target="_blank"
              ><img id="profilepic"
                src="./assets/profilepic-cantuncer.png"
                alt=""
                style="margin-right: 1px; width: 35px;"
            /></a>
          </li>
          
        </ul>
      </nav>

<!------------------------ NAV BAR BİTİŞ ------------------------>







<!------------------------- GOOGLE LOGO------------------------>
      <div class="container">
        <img
          src="./assets/logo.png"
          width="350px"
          alt=""
        />
      </div>
<!------------------------- GOOGLE LOGO SON ------------------------->


<!------------------------ SEARCH BAR BAŞLANGIÇ ------------------------->
      <div class="search-area"> 
        <div class="search">
          <div class="search-img">
            <span>
              <svg 
                focusable="false"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
              > <!-- Scalable Vector Graphics -->
                <path
                  d="M15.5 14h-.79l-.28-.27A6.471 6.471 0 0 0 16 9.5 6.5 6.5 0 1 0 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79l5 4.99L20.49 19l-4.99-5zm-6 0C7.01 14 5 11.99 5 9.5S7.01 5 9.5 5 14 7.01 14 9.5 11.99 14 9.5 14z"
                ></path> <!-- SVG Path -->
              </svg>
            </span>
          </div>
          <div class="input-enter">
            <div class="input-area">
              <input
                type="text"
                class="input"
                maxlength="2048"
                autofocus="true"
              />
            </div>
          </div>
          <div class="voice"> <!-- SESLİ ARAMA BUTONU EKLENDİ! -->
            <img class="voice-search" style="width: 35px;" src="/frontend101-odevler-kodluyoruz-patika.dev/css/odev-8-google-ana-sayfasini-tasarlamak/cloned/assets/voicelogo.png" alt="">
          </div>
        </div>
      </div>
<!----------------------- SEARCH BAR BİTİŞ ----------------------->



<!----------------------------- BUTONLAR ---------------------------->
      <div class="buttons">
        <a href=""
          ><button class="googlesearch">Google Search</button></a
        >
        <a href=""
          ><button class="feelinglucky">I'm Feeling Lucky</button></a
        >
      </div>
    </div>
<!----------------------------- BUTONLAR BİTİŞ -------------------->




<!--------------------- FOOTER BAŞLANGIÇ -------------------------->
    <nav>
      <ul class="footer">
        <li class="footerli">
          <a
            href="https://www.google.com/intl/en_tr/ads/?subid=ww-ww-et-g-awa-a-g_hpafoot1_1!o2&utm_source=google.com&utm_medium=referral&utm_campaign=google_hpafooter&fg=1"
            >Advertising</a
          >
        </li>
        <li class="footerli">
          <a
            href="https://www.google.com/services/?subid=ww-ww-et-g-awa-a-g_hpbfoot1_1!o2&utm_source=google.com&utm_medium=referral&utm_campaign=google_hpbfooter&fg=1"
            >Business</a
          >
        </li>
        <li class="footerli">
          <a
            href="https://about.google/?utm_source=google-TR&utm_medium=referral&utm_campaign=hp-footer&fg=1"
            >About</a
          >
        </li>
        <li class="footerli">
          <a href="https://google.com/search/howsearchworks/?fg=1"
            >How Search works</a
          >
        </li>

        <li class="footerli" style="float: right; margin-right: 35px">
          <a href="https://www.google.com/preferences?hl=en">Settings</a>
        </li>

        <li class="footerli" style="float: right">
          <a href="https://policies.google.com/terms?hl=en-TR&fg=1">Terms</a>
        </li>

        <li class="footerli" style="float: right">
          <a href="https://policies.google.com/privacy?hl=en-TR&fg=1">Privacy</a>
        </li>
      </ul>
    </nav>
<!--------------------- FOOTER BİTİŞ -------------------------->





  </body>
</html>
```

***css:***
```css
.header { /* NAVBAR EDIT! */
  list-style-type: none;
  margin: 10px;
  overflow: hidden;
  margin-right: 16px;
  font-family: arial,sans-serif;
  font-size: 13px;
}

.headerli a { /* LIST DOTS REMOVAL! */
  display: block;
  color: black;
  text-align: center;
  padding: 5px 5px;
  text-decoration: none;
}

.headerli a:hover {
  text-decoration: underline;
}

.container {
  text-align: center;
  margin: 100px;
}

.header {
  text-align: right;
}

.headerli {
  display: inline-block;
}

.buttons {
  text-align: center;
  }

.googlesearch ,.feelinglucky { /* BUTTONS EDIT! */
  font: Arial, Helvetica, sans-serif;
color:#5f6368;
font-size: 14px;
height: 36px;
border: 1px #f2f2f2;
margin-top: 25px;
}

.googlesearch:hover, .feelinglucky:hover { /* BUTTON ANIMATION! */
  box-shadow: 0 2px 3px 0 rgba(0,0,0,0.24), 0 2px 5px 0 rgba(0,0,0,0.19);
}


.search-area { /* arama kutusunu şenlendirme */
  background: #fff;
  display: flex;
  border-radius: 20px;
  border: 1px solid #dfe1e5;
  box-shadow: none;
  z-index: 3;
  height: 44px;
  margin: 0 auto;
  margin-top: -77px;
  width: 582px;
}

.search-area input { /* SEARCH-BAR BORDER REMOVAL! */
  border: 0px;
  width:475px;
}

.search-area:hover {
box-shadow: 0 2px 3px 0 rgba(0,0,0,0.24), 0 2px 5px 0 rgba(0,0,0,0.19);
}

.search {
  flex: 1;
  display: flex;
  padding: 5px 8px 0 16px;
  padding-left: 14px;
}

.search-img {
  display: flex;
  align-items: center;
  padding-right: 13px;
  margin-top: -5px;
}

.search-img span {
  color: #9aa0a6;
  height: 20px;
  width: 20px;
  margin-top: 0px;
  display: inline-block;
  fill: currentColor;
  line-height: 24px;
  position: relative;
}

.input-enter {
  display: flex;
  flex: 1;
  flex-wrap: wrap;
}

.input-area {
  color: transparent;
  flex: 100%;
  white-space: pre;
  font: 16px arial, sans-serif;
  line-height: 34px;
  height: 34px !important;
  display: block;
}

.input {
  margin: 0;
  padding: 0;
  color: rgba(0, 0, 0, 0.87);
  word-wrap: break-word;
  outline: none;
  display: flex;
  flex: 100%;
  margin-top: -68px;
  font: 16px arial, sans-serif;
  line-height: 34px;
  height: 34px !important;
  text-rendering: auto;
  letter-spacing: normal;
  word-spacing: normal;
  text-transform: none;
  text-indent: 0px;
  text-shadow: none;
  text-align: start;
  appearance: textfield;
  cursor: text;
}

.googlesearch {
  margin: 11px 4px;
  padding: 0 16px;
  line-height: 27px;
  min-width: 54px;
  text-align: center;
  cursor: pointer;
  user-select: none;
}

.feelinglucky {
  padding: 0 16px;
  line-height: 27px;
  min-width: 54px;
  text-align: center;
  cursor: pointer;
  user-select: none;
}

.footer {
  margin: 0;
  padding: 0;
  overflow: hidden;
  border: 1px solid #dfe1e5;
  border-top: 1px solid #dadce0;
  position: fixed;
  bottom: 0;
  width: 100%;
  margin-left: -8px;
  line-height: 10px;
  background-color: #f2f2f2;
}

.footerli {
  float: left;
}

.footerli a {
  display: block;
  color: #70757a;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-family: arial, sans-serif;
  font-size: 14px;
  margin-left: 14px;
  margin-right: -20px;
}

.footer li {
  list-style: none;
}

.footerli a:hover {
  text-decoration: underline;
}
```


Bu ödev ile birlikte CSS bölümünü tamamladınız, tebrik ederiz!

---

# Bootstrap

Bootstrap ile responsive web tasarımını hızla ve verimli bir biçimde oluşturulabilir. Bu eğitim sizin rehberiniz olacak.

Grid sistem, continer, row, col yapısı, responsive yapı, ui component


##Konular
5 bölüm ve 21 konu

## Bootstrap Nedir? - 7 konu
- Bootstrap Nedir?
- Bootstrap 4 Dökümanlarına Ulaşmak ve Bootstrap 5 Hakkında
- 12'lik Izgara(Grid) Sistemini Anlamak
- Bootstrap - Genel Tutucu(Container), Satır Blokları(Row) ve Kolon(Col) Yapısı
- Bootstrap - Ekran Çözünürlüğü / Cihaz Duyarlı(Responsive) Kolon Yapısı Kullanımları
- Bootstrap - Satır Blokları (Row) Kullanımı
- Ödev 1
## Bootstrap Devam Konuları - 5 konu
- Bootstrap Kullanarak Web Sitesi Nasıl Yapılır (Demo)
- Bootstrap Renk Strandartları, Tipografi, Margin ve Padding Kullanımı
- Display Özellikleri ile Responsive Yapıya Göre İstenilen Blokların Gösterilmesi / Gizlenmesi
- Bootstrap - Offset Kullanımı
- Bootstrap Sıralama Özellikleri Kullanarak Responsive Yapıya Göre Tepkilerin Düzenlenmesi
## Bootstrap Bileşenleri (UI Components) - 2 konu
- Bootstrap Bileşenlerine(UI Components) Genel Bakış
- Ödev 2
## Alıştırmalar & Ödevler - 5 konu
- Bootstrap ile Medium Klon Çalışması - Tek Video
- Bootstrap ile Medium Klon Çalışması - Bölüm 1
- Bootstrap ile Medium Klon Çalışması - Bölüm 2
- Bootstrap ile Medium Klon Çalışması - Bölüm 3
- Bootstrap ile Medium Klon Çalışması - Bölüm 4
## Bootstrap Harici CSS Kütüphaneleri - 2 konu
- Diğer CSS Kütüphanelerine Genel Bakış
- Ödev 3

---

## Bootstrap Nedir?

![Bootstrap](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-nedir/figures/Bootstrap.png)

Bootstrap dünyanın en popüler, açık kaynak kodlu, ücretsiz, farklı cihazlar için responsive tasarıma duyarlı bir CSS **Framework(kütüphane)**'üdür.

İçerisinde mevcut olan sayısız tablo, grafik, ikon, carousel, navigasyon gibi pek çok hazır tasarım sayesinde sitenizi kolayca tasarlayabilirsiniz.

Ayrıca Bootstrap‘in kullandığı Grid (Izgara) sistemi ile sitenizi istediğiniz bölümde konumlandırabilirsiniz. Bu özellik, ekranı dilediğiniz ölçüde bölüp, ayırdığınız bu kısımlara kolayca müdahale etmenizi sağlamaktadır.

**Basit bir hazır Bootstrap örneği:**
```bootstrap
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Bootstrap Example</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js"></script>
</head>
<body>

<div class="jumbotron text-center">
  <h1>My First Bootstrap Page</h1>
  <p>Resize this page to see the responsive effect!</p> 
</div>
  
<div class="container">
  <div class="row">
    <div class="col-sm-4">
      <h2>London</h2>
      <p>London is the most populous city in the United Kingdom,
      with a metropolitan area of over 13 million inhabitants.</p>
    </div>
    <div class="col-sm-4">
      <h2>Paris</h2>
      <p>The Paris area is one of the largest population centers in Europe,
      ith more than 12 million inhabitants.</p>
    </div>
    <div class="col-sm-4">
      <h2>Tokyo</h2>
      <p>Tokyo is the center of the Greater Tokyo Area,
      and the most populous metropolitan area in the world.</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Çıktı:**
![Çıktı](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-nedir/figures/website.png)

**Faydalı Linkler:**
- [Resmi Bootstrap Dökümantasyonu](https://getbootstrap.com/docs/5.0/getting-started/introduction/)
- [Bootstrap Bileşenleri 1](https://www.toptal.com/front-end/what-is-bootstrap-a-short-tutorial-on-the-what-why-and-how)
- [Bootstrap Bileşenleri 2](https://www.w3schools.com/whatis/whatis_bootstrap.asp)
- [Hazır Bootstrap Temaları](https://themes.getbootstrap.com/)

---

## Bootstrap 4 Dökümanlarına Ulaşmak ve Bootstrap 5 Hakkında
Bootstrap kütüphanesi 2011 yılının Ağustos ayından beri açık kaynaklı olarak geliştiriliyor aynı zamanda gelişen web teknolojileri ile birlikte yeni versiyonlar çıkartıp kütüphanenin kapsamını artırarak kütüphanenin gücünü artırıp, kullanımını kolaylaştırıyor. Fakat yeni versiyon ne kadar iyi bir özellik gibi gözükse de, yayınlandıkları zaman bazı eski versiyon özellikleri ve yazım şekilleri de terk ediliyor, buda bazı eski kodların yeni versiyonlarda çalışmasını imkansız hale getiriyor.

Bu seri çekilirken Bootstrap'in 5. Versiyonu henüz Beta test aşamasında olduğu için kurs sürecinde Bootstrap 4.5 sürümü kullanılmıştır. Size önerilen Bootstrap 4 ile Bootstrap 5 arasında pek de fark olmadığından kurs ile birlikte 4 versiyonunu öğrenip, 5. versiyondaki küçük değişiklikleri de stabil bir sürüm çıktığı zaman öğrenmeniz olacaktır.

Son çıkmış sürümü kullanmadığımızdan, [Bootstrap Sitesinin](https://getbootstrap.com/) Docs(Döküman) kısmına girdiğinizde sağ yukarıdan versiyon seçimini yapmanız gerekmektedir. Latest versiyon yerine V(4.5.X) seçmeniz gerekiyor. Tıkladığınız zaman [bu sayfaya](https://getbootstrap.com/docs/4.5/getting-started/introduction/) geleceksiniz.

## Versiyon 5'in Versiyon 4'e Göre Farkı
Bootstrap 5 in en çok sevilen özelliği kütüphanenin jquery kütüphanesinden tamamen bağımsız hale gelmesi. Önceki versiyonlarda jquery kullanmadan Bootstrap kullanılamıyordu fakat artık jquery kullanmadan da Bootstrap'in özelliklerinden yararlanabiliyorsunuz. Tabi hala jquery kullanmak isterseniz de entegre edebiliyorsunuz.

Bootstrap 5 ile gelen ana özelliklerden diğeri de, Arapça gibi **sağdan sola okunan** diller için destek. Bootstrap 4 versiyonunda **Left (sol)** ve **Right (sağ)** sistemleri **start (başlangıç)** ve **end(bitiş)** sistemine dönüştü. Aksini belirtmediğiniz zamanlar left yazacağınıza start, right yazacağınıza da end yazmanız gerekecek.

Bootstrap'in bu sistemi getirmesindeki amacı sizin dinamik olarak sağdan sola dillerde start'ı right, end'i left olarak deklere edip her dil için okunaklı bir site yapabilmenizi sağlamak. Bazı değişten syntax örnekleri...


Versiyon farklarının geri kalanlarını [bu linkten](https://getbootstrap.com/docs/5.0/migration/) görebilirsiniz.


## Dökümanlar Nasıl Kullanılır?
Döküman okuyabilmek ve dokümanlar arasından aradığınız şeyleri bulabilmek, mühendislerin ve kod yazarlarının sahip olabileceği en faydalı özelliklerden biridir. Bilgisayar dünyasında sorularınızın cevapları çoğunlukla **Stackoverflow** gibi forumlarda ve yeni öğrenmeye çalıştığınız bilgilerde hep dökümantasyonlarda bulunmaktadır.

Yeni başladığınız kütüphanelerin dökümanlarında her zaman **getting started** bölümünden başlamanız önerilir. Bu bölümde nasıl bilgisayarınıza kuracağınız ve dikkat etmeniz gereken önemli konulardan bahsedilir. Sonrasında çoğu dökümantasyonda basit bir proje yazarak adım adım sizi yönlendirir. Yeni bir kütüphaneyi öğrenmeye çalıştığınız zaman sizi en kolay alıştıracak bölümler bunlardır.

Bootstrap gibi arayüz kütüphanelerinde kendi projenize ek olarak ekleyebileceğiniz çok sayıda bileşen bulabilirsiniz. Mesela [dökümantasyonun components kısmında](https://getbootstrap.com/docs/4.5/components/alerts/) çok fazla sayıda hazır bileşen bulunmaktadır.

Bu bölümden bulduğunuz bileşenleri kendi uygulamanıza entegre etmek isterseniz, sitede hazır olarak bulunan kodu kullanabilirsiniz. Mesela örnek olarak yüklenme animasyonu olarak kullanabileceğiniz ["border spinner" sayfasına gelirseniz.](https://getbootstrap.com/docs/4.5/components/spinners/) Orada size verilen kodu kullanarak o bileşeni kendi kodunuzda da görebileceksiniz. **Çalışması için Bootstrap'i kodunuzda çağırdığınıza emin olun!**

```html
<div class="spinner-border" role="status">
  <span class="sr-only">Loading...</span>
</div>
```

Bootstrap dökümanında gezmeniz sizin için kütüphanenin size sunduğu tüm fırsatları görebilmeniz için çok büyük bir fırsattır. Her dersten sonra Bootstrap dökümanlarından ders konusunu bulup da tekrar edebilirsiniz. Bu da sizin ders konusunu daha iyi anlamanıza ve o konu hakkında başka yöntemler öğrenmenizi sağlayacaktır.

---

## 12'lik Izgara(Grid) Sistemini Anlamak
Bootstrap, sayfa düzeni (layout) oluşturmak için, CSS flexbox ile oluşturulmuş ızgara (grid) sistemini kullanmaktadır.

**Bootstrap ızgara sistemi 3 ana yapıdan oluşur:**

- Kapsayıcı (.container)
- Satırlar (.row)
- Kolonlar (col-*) (Örnek: .col-md-8)

Her bir sütun, 12 kolondan meydana gelmekte ve 12'lik Grid sistemi oluşturmaktadır. 12'lik ızgara sisteminde, kolon sayısı varyasyonları ile istenildiği gibi tasarım yapılabilmektedir.

![Bootstrap12'likGridSyst.](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/12lik-izgaragrid-sistemini-anlamak/figures/izgara-sistemi.jpg)

### Öntanımlı Kolon Sınıf Adları
Her ölçüdeki cihaza uyumlu (responsive) tasarımın oluşturulması için Bootstrap'te öntanımlı kolon sınıfları (class) kullanılır.

### Bootstrap Kolon Sınıfları
**Örnekler:**
![BootstrapKolonSınıfları](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/12lik-izgaragrid-sistemini-anlamak/figures/ornekler.jpg)

### Eşit Kolonlar
Eşit kolonlu tasarım için;

- 12 adet 1'er kolon (.col-[sınıfAdı]-1)
- 6 adet 2'li kolon (.col-[sınıfAdı]-2)
- 4 adet 3'lü kolon (.col-[sınıfAdı]-3)
- 3 adet 4'lü kolon (.col-[sınıfAdı]-4)
- 2 adet 6'lı kolon (.col-[sınıfAdı]-6)
- 1 adet 12'li kolon (.col-[sınıfAdı]-12) oluşturulabilir.
- 
Ya da `col` sınıfına sahip element sayısına göre (Örneğin; 3 adet `.col` sınıfı olan elementler 3 adet kolon oluşturur) otomatik olarak eşit kolonlara bölünebilir.

![EşitKolonlar](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/12lik-izgaragrid-sistemini-anlamak/figures/esit-kolonlu-tasarim.jpg)

```html
<div class="row">
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
</div>

<div class="row">
    <div class="col-2">Kolon</div>
    <div class="col-2">Kolon</div>
    <div class="col-2">Kolon</div>
    <div class="col-2">Kolon</div>
    <div class="col-2">Kolon</div>
    <div class="col-2">Kolon</div>
</div>

<div class="row">
    <div class="col-3">Kolon</div>
    <div class="col-3">Kolon</div>
    <div class="col-3">Kolon</div>
    <div class="col-3">Kolon</div>
</div>

<div class="row">
    <div class="col-4">Kolon</div>
    <div class="col-4">Kolon</div>
    <div class="col-4">Kolon</div>
</div>

<div class="row">
    <div class="col-6">Kolon</div>
    <div class="col-6">Kolon</div>
</div>

<div class="row">
    <div class="col-12">Kolon</div>
</div>
```

### Eşit Olmayan Kolonlar
Kolon sayılarının 12'ye tamamlanma zorunluluğu yoktur. Tasarıma göre istenilen sayıda kolonlar oluşturulabilir ve istenilen yerlerde boşluk bırakılabilir.

- 1 adet 2'li kolon (.col-[sınıfAdı]-2) ile 1 adet 10'lu kolon (.col-[sınıfAdı]-10) ya da 1 adet 8'li kolon (.col-[sınıfAdı]-8) ile 1 adet 4'lü kolon (.col-[sınıfAdı]-4) 12'ye tamamlanabilir.

Tek bir adet 8'li kolon (.col-[sınıfAdı]-8), tek bir adet 6'lı kolon (.col-[sınıfAdı]-6) ya da 1 adet 4'lü kolon (.col-[sınıfAdı]-4) ile 1 adet 5'li kolon (.col-[sınıfAdı]-5) kolon 12'ye tamamlanmadan bıraklabilir. Böylece **eksik bırakılan kolon değeri kadar** yan tarafta boşluk kalmış olur.

Verilen kolon değerlerinin toplamı 12'den fazla olması durumunda son kolon bloğu bozmayacağı için alt tarafa geçer. **Örnek olarak;**

1 adet 8'li kolondan sonra 1 adet 6'lı kolon değeri verilir ise 8 + 6 = 14 toplam kolon sayısı 12'den büyük olacağı için 6'lı kolon 8'li kolonun altına geçer.

Kolonların arasında da boşluk bırakmak mümkün. Bunun için `col` sınıfının yanına öntanımlı `margin` ve margin yönünü (`ml-auto` gibi) belirten bir sınıf adı daha eklenmelidir. Kolonun solunda boşluk bırakmak için margin (m) left (l) yani `ml-auto` sınıfı eklemeli, aynı şekilde sağ tarfında boşluk bırakılmak istenirse margin (m) right (r) yani `mr-auto` sınıfı eklemelidir.

Örneğin; `col-4 mr-auto` sınıfı olan bir kolonun sağ tarafında, `col-4 ml-auto` sınıfı ise kolonun solunda boşluk bırakır.

![EşitOlmayanKolonlar](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/12lik-izgaragrid-sistemini-anlamak/figures/esit-olmayan-kolonlar.jpg)

```html
<div class="row">
    <div class="col-2">2 Kolon</div>
    <div class="col-10">10 Kolon</div>
</div>

<div class="row">
    <div class="col-8">8 Kolon</div>
    <div class="col-4">4 Kolon</div>
</div>

<div class="row">
    <div class="col-8">8 Kolon</div>
    <div class="col-6">6 Kolon</div>
</div>

<div class="row">
    <div class="col-4">4 Kolon</div>
    <div class="col-5">5 Kolon</div>
</div>

<div class="row">
    <div class="col-4 mr-auto">4 Kolon</div>
    <div class="col-5">5 Kolon</div>
</div>

<div class="row">
    <div class="col-4">4 Kolon</div>
    <div class="col-5 ml-auto">5 Kolon</div>
</div>
```

### Kolonların Sıralanması
Öntanımlı `order-[sıra numarası]` sınıfını ekleyerek kolonları sıralayabiliriz.

Örneğin; `col-3 order-3` üç kolonluk bölümü üçüncü sıraya yerleştirecektir.

![KolonlarınSıralanması](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/12lik-izgaragrid-sistemini-anlamak/figures/kolon-siralama.jpg)

```html
<div class="row">
    <div class="col-3 order-3">3 Kolon</div>
    <div class="col-4 order-2">4 Kolon</div>
    <div class="col order-1">5 Kolon</div>
</div>
```

### İç İçe Izgara Sistemi
Bir satırdaki (`row`) kolonun (`col`) içine başka bir satır eklenerek yine kolonlara bölünebilir.

Örneğin; 4'lük bir kolon (`.col-[sınıfAdı]-4`) ile 8'lik bir kolondan (`.col-[sınıfAdı]-8`) oluşan satırdaki 8'lik kolonun içinde yeni bir satır (row) eklenerek 2 adet 6'lık kolon (`.col-[sınıfAdı]-6`) oluşturulabilir.

![İçİçeIzgaraSist.](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/12lik-izgaragrid-sistemini-anlamak/figures/icice-izgara-sistemi.jpg)

```html
<div class="row">
    <div class="col-4">4 Kolon</div>
    <div class="col-8">
        8 Kolon

        <div class="row">
            <div class="col-6">6 Kolon</div>
            <div class="col-6">6 Kolon</div>
        </div>
    </div>
</div>
```

### Örnek Bir Sayfa İncelemesi

Sayfanın tasarımı yukarıdan aşağıya sırasıyla şöyle hazırlanmış; ilk bölüm 12 kolonlu, ikinci bölüm 8 ve 4 kolonlu, üçüncü bölüm 4 kolonlu üç eşit parça, dördüncü ve beşinci bölüm ise 3 kolonlu dört eşit parçadan oluşturulmuş.

![ÖrnekBirSayfa](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/12lik-izgaragrid-sistemini-anlamak/figures/ornek-sayfa.jpg)


### Alıştırma
Aşağıda görseli verilen sayfayı, Bootstrap 12'li ızgara sistemi ile tasarlayınız.


![AlıştırmaSite](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/12lik-izgaragrid-sistemini-anlamak/figures/uygulama.jpg)

---


# Container, Row ve Col Yapısı
**Container, row ve column** yapısı aslında Bootstrap kullanım mantığının temellerini oluşturuyor diyebiliriz. Bu yapıyı anlamak Bootstrap ile çalışmayı çok çok kolaylaştıracaktır. Öncelikle `container` ile başlayalım.

## `container`
Container'ı(konteynır) isminden de biraz anlaşılacağı gibi, içine web sayfamızda bulunması gereken yazıları, resimleri, videoları veya herhangi bir içeriği koyduğumuz kapsayıcı bir çerçeve, kutu gibi düşünebiliriz. Biz içeriklerimizi bu container içerisine koyuyoruz ve bir tarayıcıdan web sayfamız görüntülendiğinde container kendisini ekranın tam ortasına gelecek şekilde ayarlıyor. Görsel bir örnek üzerinde en ilerlemek daha açıklayıcı olacaktır. Örnek olarak aşağıda kodluyoruz'dan aldığım bir ekran görüntüsünü inceleyebiliriz.

Becerilerini geliştir, Mezunlar Kulübü'ne Katıl ve Şirketlerle Buluş kısımlarını kapsayan ancak bize gözükmeyen bir çerçeve olduğunu düşünelim. Bu çerçeve ile sayfayı görüntülediğim ekran arasında sağ taraftan ve sol taraftan eşit miktarda boşluklar var gördüğünüz gibi, yani container ortalanmış.

![Container](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-genel-tutucucontainer%2C-satir-bloklarirow-ve-koloncol-yapisi/figures/kodluyoruz-container-red.png)

İşte sayfamızın içeriklerini böyle belirli ölçülerde container'lar içerisine koyuyoruz ve ayrıca container'lara vereceğimiz class isimlerine göre onlara farklı özellikler katıyoruz. Örneğin containerlar boyutlarını değiştirip responsive bir tasarım yapmamıza yardımcı oluyorlar. Yani biz bir sayfayı cep telefonu, tablet veya laptop ile görüntülediğimizde cihazların ekran boyutları farklı olacağı için, container'ımızda kendisini bu ekran boyutuna göre yeniden ölçeklendiriyor, ortalıyor veya düzenliyor. Tüm sayfayı tek bir container içerisine koyup düzenleyebileceğimiz gibi, birden fazla container veya iç içe container'da kullanılabiliyor gerektiği durumlarda.

Aşağıdaki tabloyu [bootstrap](https://getbootstrap.com/docs/4.4/layout/overview/)'in official sayfasından bulabilirsiniz.

![ContainerTable](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-genel-tutucucontainer%2C-satir-bloklarirow-ve-koloncol-yapisi/figures/container-sizes.png)

En soldaki sütunda container class isimlerini görüyoruz, mesela `.container` veya `.container-md` gibi. Class'ların kullanımını örnek ile göstermek gerekirse; `<div class="container-md"></div>` şeklinde bir HTML dosyası içerisinde kullanabiliriz. HTML dosyası içerisinde class isimleri tanımlarken başındaki "."(nokta)'yı kaldırmamız gerekli. Peki bu tablo bize neyi anlatıyor? .container-md class'ını kullanarak bu tabloyu açıklamaya çalışacağım. .container-md class'ına sahip bir container;

- **extra small** bir cihazda, yani **576px'den küçük** olan bir cihazda, ekran boyutunun **100%**'ünü kaplamaktadır.
- **small** bir cihazda, yani **576px'den büyük veya eşit** olan bir cihazda, ekran boyutunun **100%**'ünü kaplamaktadır.
- **medium** bir cihazda, yani **768px'den büyük veya eşit** olan bir cihazda, bu containerın genişliği **720px** olacaktır.
- **large** bir cihazda, yani **992px'den büyük veya eşit** olan bir cihazda, bu containerın genişliği **960px** olacaktır.
- **X-large** bir cihazda, yani **1200px'den büyük veya eşit** olan bir cihazda, bu containerın genişliği **1140px** olacaktır.
- **XX-large** bir cihazda, yani **1400px'den büyük veya eşit** olan bir cihazda, bu containerın genişliği **1320px** olacaktır.

Container'larımız bu tablodaki verilen boyutlara göre kendilerini ortalayacak, etrafındaki boşlukları ayarlayacak ve değişen ekran boyutlarına tepki verecektir. Genel olarak container'ların kullanımı bu şekilde diyebiliriz.


## Row ve Column Yapısı
Row(satır), column(sütun) sistemi Bootstrap'in grid system(ızgara sistemi) denilen düzenini oluşturuyor. Grid system ile bir web sayfası 12 adet sütuna bölünmüş ve sayfanın içeriği bu sütunların boyutlarına göre düzenlenmiş diyebiliriz. Genel olarak göstermek gerekirse aşağıdaki resim örnek bir sayfanın 12 adet sütuna bölündüğünde hangi içeriğin hangi sütunlar boyutunda olacağını, aralarındaki boşlukları göstermektedir.

![Row ve Column Yapısı-1](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-genel-tutucucontainer%2C-satir-bloklarirow-ve-koloncol-yapisi/figures/overall-grid.png)

İçeriklerimizin genişliğini sütun yapısına göre belirliyoruz demiştik. Yani sayfamızda paylaşmak istediğimiz bir yazı, 12 sütunun 3 tanesini kapsayacak genişlikte olsun, kalan 9 sütun ise bir resim için ayrılmış olsun. Peki içeriklerin uzunluğunu neye göre belirliyoruz? İşte burada da satırları kullanıyoruz. Sayfamızı yukardan aşağıya satırlara bölüyoruz ve her satırın içerisinde ayrı ayrı sütun sayısı, boyutu belirleyebiliyoruz. Bu şekilde satırları ve sütunları bir container içerisinde kullandığımızda grid system uygulamış oluyoruz. Kafa karıştırıcı gibi gözükebilir ancak aşağıdaki resmi incelediğimizde her şey çok net anlaşılacaktır.

![Row ve Column Yapısı-2](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-genel-tutucucontainer%2C-satir-bloklarirow-ve-koloncol-yapisi/figures/grid-details.png)

- İlk Satır Birbirine Eşit Boyutta 12 Adet Sütundan
- İkinci Satır Birbirine Eşit Boyutta 3 Adet Sütundan
- Üçüncü Satır 2 Farklı Boyutta Sütundan
- Dördüncü Satır 2 Eşit Boyutta Sütundan
- Beşinci Satır İse Tek Bir Sütundan Oluşmaktadır.

Görüldüğü gibi 12 adet sütun yapısını istediğimiz biçimde birleştirerek, ayırarak satırlar ile birlikte kullanarak tasarımımızı yapabiliriz.

Son olarak ise grid yapısını oluşturmak için nasıl bir kod yapısı kullanmamız gerektiğini basit bir örnek ile anlamaya çalışalım.

![Örnek Grid Yapısı](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-genel-tutucucontainer%2C-satir-bloklarirow-ve-koloncol-yapisi/figures/sample-grid.png)

Bu resimde gördüğümüz 2 satırdan oluşan grid yapısını aşağıdaki kod ile oluşturabiliriz.

```html
<div class="container">
  <div class="row">
    <div class="col">
      1 of 2
    </div>
    <div class="col">
      2 of 2
    </div>
  </div>
  <div class="row">
    <div class="col">
      1 of 3
    </div>
    <div class="col">
      2 of 3
    </div>
    <div class="col">
      3 of 3
    </div>
  </div>
</div>
```

`div` HTML tag'lerine `class="row"` veya `class="col"` sınıfları vererek bu tag'lerin ne amaçla kullanılacağını belirttik. Ayrıca dikkat ederseniz bu grid bir `class="container"` içerisinde bulunmakta.

Row ve column yapısının kullanımı ve mantığı genel hatlarıyla bu şekilde diyebiliriz.

Dersteki kodlar;
```html
 <div class="container">
        <div class="row">
            <div class="col-sm-6 col-md-4 col-lg-3 col-xl-2 bg-primary">Lorem, ipsum.</div>
            <div class="col-sm-6 col-md-4 col-lg-3 col-xl-2 bg-secondary">Facilis, saepe!</div>
            <div class="col-sm-6 col-md-4 col-lg-3 col-xl-2 bg-success">Placeat, perferendis!</div>
            <div class="col-sm-6 col-md-4 col-lg-3 col-xl-2 bg-danger">Repellendus, laudantium.</div>
            <div class="col-sm-6 col-md-4 col-lg-3 col-xl-2 bg-warning">A, debitis.</div>
            <div class="col-sm-6 col-md-4 col-lg-3 col-xl-2 bg-dark">Nisi, deserunt?</div>
        </div>
      </div>
```

### Kaynaklar
- https://www.kodluyoruz.org/
- https://getbootstrap.com/docs/4.4/layout/overview/
- https://960.gs/
- https://www.w3schools.com/bootstrap/bootstrap_grid_system.asp
- https://getbootstrap.com/docs/4.0/layout/grid/


---

## Bootstrap - Ekran Çözünürlüğü / Cihaz Duyarlı(Responsive) Kolon Yapısı Kullanımları

<iframe width="1106" height="622" src="https://www.youtube.com/embed/9_mdnDE5UnA" title="Bootstrap Ekran Çözünürlüğü/Cihaz Duyarlı(Responsive) Kolon Yapısı Kullanımı #4" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

---

# Bootstrap - Satır Blokları (Row) Kullanımı
Grid sistem, **satırlardan(rows)** ve **sütunlardan(column)** oluşur. Bir satır(row) 12 column'dan oluşur. Bu satırları istediğimiz şekilde parçalayabiliriz. Aşağıdaki resimde de görüldüğü gibi istersek bunları 12 eşit parçaya ayırabilir ya da 12'ye tamamlanacak herhangi bir şekilde de bölebiliriz. Örneklerle bunları açıklamaya çalışayım.

![Row](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-satir-bloklari-row-kullanimi/figures/Bootstrap-part-2.png)

```html
<div class="row">
  <div class="col">Column</div>
  <div class="col">Column</div>
</div>
```
![2'li Column](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-satir-bloklari-row-kullanimi/figures/6of6.PNG)

```html
<div class="row">
  <div class="col">Column</div>
  <div class="col">Column</div>
  <div class="col">Column</div>
</div>
```
![3'lü Column](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-satir-bloklari-row-kullanimi/figures/3column.PNG)

```html
<div class="row">
  <div class="col">Column</div>
  <div class="col">Column</div>
  <div class="col">Column</div>
  <div class="col">Column</div>
</div>
```

![4'lü Column](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-satir-bloklari-row-kullanimi/figures/4column.PNG)

Yukarıdaki örneklerde de görüldüğü üzere satırları eşit parçalar halinde column'lara ayırdık. Peki eşit olmayan column'lar yapabilir miyiz? Tabii ki yapabiliriz. Şimdi de örneklerle eşit olmayan column'lar oluşturalım...

- Bu örnekte 2'ye 10'luk bir column oluşturduk.

```html
<div class="row">
  <div class="col-2">2 Column</div>
  <div class="col-10">10 Column</div> 
</div>
```

![2Column,10Column](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-satir-bloklari-row-kullanimi/figures/img-2.PNG)

- Alttaki örnekte ise satırı 8'e 4'lük bir column halinde bölmüş olduk.
```html
<div class="row">
  <div class="col-4">4 Column</div>
  <div class="col-8">8 Column</div> 
</div>
```

![8Column,4Column](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-satir-bloklari-row-kullanimi/figures/8of4.PNG)

- Satırları böldüğümüzde araya ya da herhangi bir kenara boşluk ekleyebiliriz onu da şu şekilde gösterelim;

```html
<div class="row">
  <div class="col-4 mr-auto">4 Column</div> <--mr: margin right (sağından boşluk bırak)-->
  <div class="col-5">5 Column</div> 
</div>

<div class="row">
  <div class="col-4"></div>
  <div class="col-5 ml- auto"></div> <--ml: margin left (solundan boşluk bırak)-->
</div>
```

![4-5-4-5 Column](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-satir-bloklari-row-kullanimi/figures/img-7.PNG)


İki kod bloğunun çıktısı aynı olacak fakat birinci `col` sağından sola doğru itecek ve boşluk bırakacak diğerinde ise tam tersi ikinci col solundan sağa doğru iterek boşluk bırakacak.

- Bir satırı 4'e 8'lik column'lar halinde böldüğümüzü düşünelim bu satırlar daha sonra kendi içlerinde de tekrar 12'lik column gibi düşünülerek bölünebilir. Bunlara iç içe satırlar diyebiliriz. Aşağıdaki örnekte önce satırı 4'e 8'lik olacak şekilde parçaladık daha sonra 8'lik column'u kendi içinde eşit 2 parçaya böldük.

```html
<div class="row">
			<div class="col-4 border">4 Column</div>
			<div class="col-8 border">8 Column
				
				<div class="row">
					<div class="col bg-primary">6 Column</div> <!--bg: background, primary:color-->
					<div class="col bg-danger">6 Column</div>  <!--bg: background, primary:color-->
				</div>
			
			
			</div>
		</div>
```

![4-8-6-6 Column](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/bootstrap/bootstrap-satir-bloklari-row-kullanimi/figures/img8.PNG)

### Kaynaklar

[Komple Uygulamalı Web Geliştirme Eğitimi](https://www.udemy.com/course/komple-web-developer-kursu/learn/lecture/9815366#overview)
[Bootstrap Grid Sistem 1](https://www.sadikturan.com/bootstrap/bootstrap-grids/1201)
[Bootstrap Grid Sistem 2](https://www.tutorialspoint.com/bootstrap/bootstrap_grid_system.htm)
[Bootstrap Layout](https://getbootstrap.com/docs/4.1/layout/overview/)
[Bootstrap Izgara Grid Sistemi](https://fatihhayrioglu.com/bootstrap-izgara-Grid-sistemi-1/)

---

# Bootstrap - Ödev 1

## Bootstrap Özelliklerini Kullanarak Yaptığımız Siteyi Geliştirelim
Hatırlar mısınız CSS'in ilk ödevinde boynu bükük bir site yapmıştık. Bu site CSS'in özelliklerini kullanan bir müzik aleti satış sitesiydi. Bu siteyi **Bootstrap** ile tekrar tasarlayacağız.

## **Sizden Beklediklerimiz**
- HTML kısmını önceki ödevden alabilirsiniz fakat baştan yapmanızı öneririz.
- Menüyü koyu renkli olarak düzenleyin. İsterseniz arka plan rengi de verebilirsiniz.
- Ana sayfaya bir **jumbotron** koyup içeriğinizin açıklamasını yazınız.
- Arka plan rengini `#E9ECEF` ile değiştirin.
- Ürünlerimiz sayfasında **card** yapısını kullanın.
- Kullandığınız **card** yapısını **grid** sistemin içinde kullanın.
- Ürün **card** boyutlarının **tamamen aynı** olduğuna dikkat edin.
- Hakkımızda sayfasını da bir **card** yapısı içine alın.
- [Bootstrap Dökümantasyonu](https://getbootstrap.com/docs/4.5/getting-started/introduction/)'nu iyi inceleyip farklı elementleri denemeye çalışın.

![ÖdevÖnizleme](https://github.com/Kodluyoruz/taskforce/blob/bootstrap/bootstrap/odev1/figures/bootstrap.gif?raw=true)

Tebrikler, Bootstrap ile ilk sitenizi oluşturdunuz.

---






