![image](https://github.com/user-attachments/assets/e8c794c7-6305-4281-9d11-fac81995c9dd)

# GitBash adlı bir dizin oluşturma ve dizine gitmek
mkdir GitBash
cd GitBash

# Yeni bir Git deposu 
git init

# Git kullanıcı adı ayarı
git config --global user.name "ErayKeles"

# Git kullanıcı e-postasını ayarı
git config --global user.email "eraykelesk@gmail.com"

# Gereksiz dosyalar için .gitignore dosyası
echo ".DS_Store" >> .gitignore
echo "node_modules/" >> .gitignore

# Boş commit
git commit --allow-empty -m "Initial commit"

# Ana (master) dalın oluşturulması
git checkout -b master

# r2.5.4 dalının oluşturulması
git checkout -b r2.5.4

# r2.5.5 dalının oluşturulması
git checkout -b r2.5.5

# r3.0 dalının oluşturulması
git checkout -b r3.0

# r2.5.4 dalına geri dönün
git checkout r2.5.4

# Hata düzeltme dalını oluşturun ve bu dala geçin
git checkout -b r2.5.4.1_Bugfix

# Hata düzeltmelerini yapın ve tüm değişiklikleri sahneleyin
git add .

# Değişiklikleri commit yapın
git commit -m "r2.5.4.1 Bugfix: [Hatayı açıklaması]"

# r2.5.4 dalına geri dönmek ve hatayı burada birleştirin
git checkout r2.5.4
git merge r2.5.4.1_Bugfix

# r2.5.5 dalına geçmek ve r2.5.4 dalındaki değişiklikleri burada birleştirmek
git checkout r2.5.5
git merge r2.5.4

# r3.0 dalına geçmek ve r2.5.5 dalındaki değişiklikleri burada birleştirmek
git checkout r3.0
git merge r2.5.5

# Uzak depo bağlantısını güncelleme
git remote set-url origin https://github.com/ErayKeles/GitBash.git

# Değişiklikleri uzak depoya göndermek
git push -u origin master
git push -u origin r2.5.4
git push -u origin r2.5.5
git push -u origin r3.0
git push -u origin r2.5.4.1_Bugfix
