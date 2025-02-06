# Git Yükleme

  **git-scm.com**'den kurulum yapılabilirsiniz. Kurulum aşamasında default değerlerle kurulum yapmak yeterlidir. 
Windows bilgisayarınıza Git'i kurmak için [Git](https://git-scm.com/downloads/win) bağlantısını kullanabilirsiniz. Bu aslında Git'in kendisi değil Windows için bir uygulamadır. Kurulum sonrasında bilgisayarınızda **Git Bash** uygulaması yüklenmiş olacak.


# Temel Terminal Komutları
**pwd :** Çalışılan klasörü gösterir. (Print working directory)<br>
**ls :** İçinde bulunduğunuz dizindeki dosyaları,klasörleri .. gösterir.<br>
**cd :** Dizini değiştirir. (Change directory) <br>
**cd.. :** Bir üst dizine geçer.<br>
**clear :** Ekranı temizler. <br>
**touch :** Dosya oluşturur. <br>
**rm :** Dosya siler.<br>
**rm -rf :** Klasör siler. (r:Rekürsif,f:Zorla sil.)<br>
**mk dir :** Klasör oluşturur. (Make directory)<br>
**clear :** Ekranı temizler. 

# Git Ayarları
- Git'i kodumda kullandığımda bu kodların benim tarafımdan yazıldığını garantiye alan imza ifadesidir.<br>

```
git config --global user.name "kulllaniciAd kulllaniciSoyad"
```
 
```
git config --global user.mail `"kullanicimail@mailadresim.com"`
```

# Git Başlatmak
- Git'in o anki statüsünü gösterir.
 ```
git status
```
- Aktif klasörde Git'i aktif hale getirir. (ls ile görünmez. Çünkü gizli dosya olarak oluşturur.)
```
git init
```

**_git init_** çalıştırılmadan önce; **_git status_** ile statü kontrolü yapılmalı, sonrasında gerekli ise init ile devam edilmelidir.

# Commit 
**git add :** Dosyayı takibe al.<br>
**git add . :** Tüm dosyaları takibe al.<br>
**git commit -m :** Commit et. *m* parametresi ile commit mesajı eklenir. <br>
**git rm --cached "dosya adı" :** Dosyayı unstage et, takip etme. Bu işlem dosyayı *silmez*, sadece takip etmeyi bırakır. <br>
**git log :** Daha önceden atılmış commitleri gösterir. <br>
**git restore "dosya adı" :** Commit atılmamışsa bir önceki hale döndürür. <br>

# Branch

Git'te branch, uygulamanın farklı versiyonlarını aynı anda geliştirmek için kullanılan bir yöntemdir. Her geliştirici, projede farklı özellikler veya düzeltmeler üzerinde çalışırken kendi branch'ini oluşturabilir ve bu branch üzerinde çalışabilir. 
Yine branch oluşturma sayesinde bir geliştirici de aynı anda bir problemin çözümü için farklı yöntemleri farklı branchler altında geliştirip karşılaştırabilir. 

**git branch :** Aktif branch' verir. <br>
**git branch *yeniBranchAdi* :** yeniBranchAdi adında yeni bir ranch oluşturur.<br>
**git switch *konumlanilacakBranch* :** konumlanilacakBranch adındaki branche gider.<br>

# Merge 
##  Fast Forward Stratejisi ile Merge İşlemi
 
2 adımda gerçekleştirilir.
- Değişiklikleri eklemek istediğimiz yani güncelleme yapmak istediğimiz branch’e geçiyoruz.
- Sonra, birleştirmek istediğimiz branch’i merge komutu ile parametre olarak geçiyoruz.

Örnek olarak feature branch’indeki değişiklikleri master branch’e aktaralım: 
```
git checkout master # güncelleyeceğimiz branch’e geçtik. Böylece master branchi aktif (HEAD) olur.
git merge feature      # feature branch’indeki commit edilmiş değişiklikler master'a entegre edilir.
```

# Commitler Arası Gezinme
- GidilecekCommitId özel değerli commite dönmek <br>
```
git checkout GidilecekCommitId  
```
*Not:* Bu esnada head pozisyonu bu önceki commite dönmüş olur. switchle tekrar son commit e gidilirse geri dönme işlemi iptal olur. <br>

- Önceki bir commit'e gidip ordan yeni bir branch açıp devam etmek 
  
```
git checkout GidilecekCommitId // Önceki bir commit'e dön.
git branch feature2   // Yeni bir branch oluştur.
git switch feature2   //Yeni branche geç.
..... Yapmak istediğin değişiklikleri tamamla.
git add . // Değişiklikleri takibe al.
git commit -m "Commit mesajı ekle."
```

# Reset ve Revert
- Belirtilen commit'e döner, aradaki her commit silinir. Log'dan da silinirler.
```
git resert --hard parCommitId
```
- Belirtilen commit'e döner . Ancak aradaki commitler kalıcı olarak silinmez. İlk committen farklı olduğu için bir commit daha atar. 
```
git revert parCommitId /
```


# Stash ve Tag
## Stash
- Son committen sonra yapılan tüm değişiklikleri zulalar.
```
git stash

```

- Stashleri listeler.

```
git stash list

```

- Değişiklikler geri gelir.

```
git stash pop
```
## Tag
- Versiyonlama için kullanılır.
Örneğin aşağıdaki ifade ile 1.0.2 versiyonunda çalışıyorum demiş oluruz.
```
git tag 1.0.2
``` 




 

