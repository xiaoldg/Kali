```
arch顯示機器的處理器架構（1）
uname -m顯示機器的處理器架構（2）
uname -r顯示正在使用的內核版本
dmidecode -q顯示硬件系統部件 - （SMBIOS / DMI）
hdparm -i / dev / hda羅列一個磁盤的架構特性
hdparm -tT / dev / sda在磁盤上執行測試性讀取操作
cat / proc / cpuinfo顯示CPU信息
cat / proc / interrupts顯示中斷
cat / proc / meminfo校驗內存使用
cat / proc / swaps顯示哪些交換被使用
cat / proc / version顯示內核的版本
cat / proc / net / dev顯示網絡適配器及統計
cat / proc / mounts顯示已加載的文件系統
lspci -tv羅列PCI設備
lsusb -tv顯示USB設備
日期顯示系統日期
cal 2007顯示2007年的日曆表
日期041217002007.00設置日期和時間 - 月日時分年。秒
clock -w將時間修改保存到BIOS 
關機（系統的關機，重啟以及登出）
shutdown  - h now關閉系統（1）
init 0關閉系統（2）
telinit 0關閉系統（3）
shutdown -h hours：minutes＆按預定時間關閉系統
shutdown -c取消按預定時間關閉系統
shutdown -r now重啟（1）
reboot重啟（2）
logout註銷
```
---
# 文件和目錄
```
cd / home進入'/ home'目錄' 
cd ..返回上一級目錄
cd ../ ..返回上兩級目錄
cd進入個人的主目錄
cd~user1進入個人的主目錄
cd  - 返回上次所在的目錄
pwd顯示工作路徑
ls查看目錄中的文件
ls -F查看目錄中的文件
ls -l顯示文件和目錄的詳細資料
ls -a顯示隱藏文件
ls [0-9]顯示包含數字的文件名和目錄名
樹顯示文件和目錄由根目錄開始的樹形結構（1）
lstree顯示文件和目錄由根目錄開始的樹形結構（2）
mkdir dir1創建一個叫做'dir1'的目錄' 
mkdir dir1 dir2同時創建兩個目錄
mkdir -p / tmp / dir1 / dir2創建一個目錄樹
rm -f file1刪除一個叫做'file1'的文件' 
rmdir dir1刪除一個叫做'dir1'的目錄' 
rm -rf dir1刪除一個叫做'dir1'的目錄並同時刪除其內容
rm -rf dir1 dir2同時刪除兩個目錄及它們的內容
mv dir1 new_dir重命名/移動一個目錄
cp file1 file2複製一個文件
cp目錄/ *。複製一個目錄下的所有文件到當前工作目錄
cp -a / tmp / dir1。複製一個目錄到當前工作目錄
cp -a dir1 dir2複製一個目錄
ln -s file1 lnk1創建一個指向文件或目錄的軟鏈接
ln file1 lnk1創建一個指向文件或目錄的物理鏈接
觸摸-t 0712250000 file1修改一個文件或目錄的時間戳 - （YYMMDDhhmm）
文件file1輸出文件的mime類型作為文本
iconv -l列出已知的編碼
iconv -f fromEncoding -t toEncoding inputFile> outputFile通過假設它是從給定的輸入文件創建一個新的在fromEncoding中編碼並將其轉換為toEncoding。
找 。-maxdepth 1 -name * .jpg -print -exec convert“{}”-resize 80x60“thumbs / {}”; 批量調整當前目錄中的文件大小並將它們發送到縮略圖目錄（需要從Imagemagick轉換）
```
---
# 文件搜索
```
find / -name file1從'/'開始進入根文件系統搜索文件和目錄
查找/ -user user1搜索屬於用戶'user1'的文件和目錄
查找/ home / user1 -name * .bin在目錄'/ home / user1 '中搜索帶有'.bin'結尾的文件
查找/ usr / bin -type f -atime +100搜索在過去100天內未被使用過的執行文件
查找/ usr / bin -type f -mtime -10搜索在10天內被創建或者修改過的文件
find / -name * .rpm -exec chmod 755'{}'; 搜索以'.rpm'結尾的文件並定義其權限
find / -xdev -name * .rpm搜索以'.rpm'結尾的文件，忽略光驅，捷盤等可移動設備
locate * .ps尋找以'.ps '結尾的文件 - 先運行'updatedb'命令
wherei halt顯示一個二進製文件，源碼或man的位置
哪個停止顯示一個二進製文件或可執行文件的完整路徑
```
---
# 掛載一個文件系統
```
mount / dev / hda2 / mnt / hda2掛載一個叫做hda2的盤 - 確定目錄'/ mnt / hda2'已經存在
umount / dev / hda2卸載一個叫做hda2的盤 - 先從掛載點'/ mnt / hda2'退出
fuser -km / mnt / hda2當設備繁忙時強制
卸載umount -n / mnt / hda2運行卸載操作而不寫入/ etc / mtab文件 - 當文件為只讀或當磁盤寫滿時非常有用
mount / dev / fd0 / mnt / floppy掛載一個軟盤
mount / dev / cdrom / mnt / cdrom掛載一個cdrom或dvdrom 
mount / dev / hdc / mnt / cdrecorder掛載一個cdrw或dvdrom 
mount / dev / hdb / mnt / cdrecorder掛載一個cdrw或dvdrom 
mount -o loop file.iso / mnt / cdrom掛載一個文件或ISO鏡像文件
mount -t vfat / dev / hda5 / mnt / hda5掛載一個Windows FAT32文件系統
mount / dev / sda1 / mnt / usbdisk掛載一個usb捷盤或閃存設備
mount -t smbfs -o username = user，password = pass // WinClient / share / mnt / share掛載一個windows網絡共享
```
---
# 磁盤空間
```
df -h顯示已經掛載的分區列表
ls -lSr |更多以尺寸大小排列文件和目錄
du -sh dir1估算目錄'dir1'已經使用的磁盤空間' 
du -sk * | sort -rn以容量大小為依據依次顯示文件和目錄的大小
rpm -q -a --qf'％10 {SIZE} t％{NAME} n'| sort -k1,1n以大小為依據依次顯示已安裝的rpm包所使用的空間（fedora，redhat類系統）
dpkg-query -W -f ='$ {Installed-Size; 10} t $ {Package} n '| sort -k1,1n以大小為依據顯示已安裝的deb包所使用的空間（ubuntu，debian類系統）
```
---
# 用戶和群組
```
groupadd group_name創建一個新用戶組
groupdel group_name刪除一個用戶組
groupmod -n new_group_name old_group_name重命名一個用戶組
useradd -c“姓名姓氏”-g admin -d / home / user1 -s / bin / bash user1創建一個屬於“ admin“用戶組的用戶
useradd user1創建一個新用戶
userdel -r user1刪除一個用戶（'-r'排除主目錄）
usermod -c”用戶FTP“-g system -d / ftp / user1 -s / bin / nologin user1修改用戶屬性
passwd修改口令
passwd user1修改一個用戶的口令（只允許root執行）
chage -E 2005-12-31 user1設置用戶口令的失效期限
pwck檢查'/ etc / passwd'的文件格式和語法修正以及存在的用戶
grpck檢查'/ etc / passwd'的文件格式和語法修正以及存在的群組
newgrp group_name登陸進一個新的群組以改變新創建文件的預設群組
```
---
# 文件的權限
```
---使用“+”設置權限，使用“ - ”用於取消ls -lh顯示權限
ls / tmp | pr -T5 -W $ COLUMNS將終端劃分成5欄顯示
chmod ugo + rwx directory1設置目錄的所有人（u），群組（g）以及其他人（o）以讀（r），寫（w）和執行（x）的權限
chmod go-rwx directory1刪除群組（g）與其他人（o）對目錄的讀寫執行權限
chown user1 file1改變一個文件的所有人屬性
chown -R user1 directory1改變一個目錄的所有人屬性並同時改變改目錄下所有文件的屬性
chgrp group1 file1改變文件的群組
chown user1：group1 file1改變一個文件的所有人和群組屬性
find / -perm -u + s羅列一個系統中所有使用了SUID控制的文件
chmod u + s / bin / file1設置一個二進製文件的SUID位 - 運行該文件的用戶也被賦予和所有者同樣的權限
chmod us / bin / file1禁用一個二進製文件的SUID位
chmod g + S /家庭/公共設置一個目錄的SGID位-類似SUID，不過這是針對目錄的
CHMOD GS /家用/公用禁用一個目錄的SGID位
搭配chmod O + T /家用/公用設置一個文件的STIKY位-只允 合法所有人刪除文件
chmod ot / home / public禁用一個目錄的STIKY位
```
---
# 文件的特殊屬性
```
- 使用“+”設置權限，使用“ - ”用於取消
chattr + a file1只允許以追加方式讀寫文件
chattr + c file1允許這個文件能被內核自動壓縮/解壓
chattr + d file1在進行文件系統備份時，dump程序將忽略這個文件
chattr + i file1設置成不可變的文件，不能被刪除，修改，重命名或者鏈接
chattr + s file1允許一個文件被安全地刪除
chattr + S file1一旦應用程序對這個文件執行了寫操作，使系統立刻把修改的結果寫到磁盤
chattr + u file1若文件被刪除，系統會允許你在以後恢復這個被刪除的文件
lsattr顯示特殊的屬性
```
---
# 打包和壓縮文件
```
bunzip2 file1.bz2解壓一個叫做'file1.bz2'的文件
bzip2 file1壓縮一個叫做'file1'的文件
gunzip file1.gz解壓一個叫做'file1.gz'的文件
gzip file1壓縮一個叫做'file1'的文件
gzip  - 9 file1最大程度壓縮
rar a file1.rar test_file創建一個叫做'file1.rar'的包
rar a file1.rar file1 file2 dir1同時壓縮'file1'，'file2'以及目錄' 
dir1'rar x file1.rar解壓rar包
unrar x file1.rar解壓rar包
tar -cvf archive.tar file1創建一個非壓縮的tarball 
tar -cvf archive.tar file1 file2 dir1創建一個包含了'file1'，'file2'以及'dir1'的檔案文件
tar -tf archive.tar顯示一個包中的內容
tar -xvf archive.tar釋放一個包
tar -xvf archive.tar -C / tmp將壓縮包釋放到/ tmp目錄下
tar -cvfj archive.tar。bz2 dir1創建一個bzip2格式的壓縮包
tar -xvfj archive.tar.bz2解壓一個bzip2格式的壓縮包
tar -cvfz archive.tar.gz dir1創建一個gzip格式的壓縮包
tar -xvfz archive.tar.gz解壓一個gzip格式的壓縮包
zip file1.zip file1創建一個zip格式的壓縮包
zip -r file1.zip file1 file2 dir1將幾個文件和目錄同時壓縮成一個zip格式的壓縮包
unzip file1.zip解壓一個zip格式壓縮包
RPM包 - （Fedora，Redhat及類似系統）
rpm -ivh package.rpm安裝一個rpm包
rpm -ivh --nodeeps package.rpm安裝一個rpm包而忽略依賴關係警告
rpm -U package.rpm更新一個rpm包但不改變其配置文件
rpm -F package.rpm更新一個確定已經安裝的rpm包
rpm -e package_name.rpm刪除一個rpm包
rpm -qa顯示系統中所有已經安裝的rpm包
rpm -qa | grep httpd顯示所有名稱中包含“httpd”字樣的rpm包
rpm -qi package_name獲取一個已安裝包的
特殊信息rpm -qg“System Environment / Daemons”顯示一個組件的rpm包
rpm -ql package_name顯示一個已經安裝的rpm包提供的文件列表
rpm -qc package_name顯示一個已經安裝的rpm包提供的配置文件列表
rpm -q package_name --whatrequires顯示與一個rpm包存在依賴關係的列表
rpm -q package_name --whatprovides顯示一個rpm包所佔的體積
rpm -q package_name  -  ** s顯示在安裝/刪除期間所執行的腳本l 
rpm -q package_name  -  changelog顯示一個rpm包的修改歷史
rpm -qf /etc/httpd/conf/httpd.conf確認所給的文件由哪個rpm包所提供
rpm -qp package.rpm -l顯示由一個尚未安裝的rpm包提供的文件列表
rpm --import / media / cdrom / RPM-GPG-KEY導入公司數字證書
rpm --checksig package.rpm確認一個rpm包的完整性
rpm -qa gpg-pubkey確認已安裝的所有rpm包的完整性
rpm -V package_name檢查文件尺寸，許可，類型，所有者，群組，MD5檢查以及最後修改時間
rpm -Va檢查系統中所有已安裝的rpm包 - 小心使用
rpm -Vp package.rpm確認一個rpm包還未安裝
rpm2cpio package.rpm | cpio --extract --make-directories bin從一個rpm包運行可執行文件
rpm -ivh / usr / src / redhat / RPMS / arch/package.rpm從一個rpm源碼安裝一個構建好的包
rpmbuild --rebuild package_name。 src.rpm從一個rpm源碼構建一個rpm包
YUM軟件包升級器 - （Fedora，RedHat及類似系統）
yum install package_name下載並安裝一個rpm包
yum localinstall package_name.rpm將安裝一個rpm包，使用你自己的軟件倉庫為你解決所有依賴關係
yum update package_name。 rpm更新當前系統中所有安裝的rpm包
yum update package_name更新一個rpm包
yum remove package_name刪除一個rpm包
yum list列出當前系統中安裝的所有包
yum search package_name在rpm倉庫中搜尋軟件包
yum clean packages清理rpm緩存刪除下載的包
yum clean headers刪除所有頭文件
yum clean all刪除所有緩存的包和頭文件
DEB包（Debian，Ubuntu以及類似系統）
dpkg -i package.deb安裝/更新一個deb包
dpkg -r package_name從系統刪除一個deb包
dpkg -l顯示系統中所有已經安裝的deb包
dpkg -l | grep httpd顯示所有名稱中包含“httpd”字樣的deb包
dpkg -s package_name獲得已經安裝在系統中一個特殊包的信息
dpkg -L package_name顯示系統中已經安裝的一個deb包所提供的文件列表
dpkg  -內容package.deb顯示尚未安裝的一個包所提供的文件列表
dpkg -S / bin / ping確認所給的文件由哪個deb包提供
APT軟件工具（Debian，Ubuntu以及類似系統）
apt-get install package_name安裝/更新一個deb包
apt-cdrom install package_name從光盤安裝/更新一個deb包
apt-get update升級列表中的軟件包
apt-get upgrade升級所有已安裝的軟件
apt-get remove package_name從系統刪除一個deb包
apt-get check確認依賴的軟件倉庫正確
apt-get clean從下載的軟件包中清理緩存
apt-cache search搜索包返回包含所要搜索字符的串名稱軟件包
報導查看頂部索引^ 
查看文件內容
貓文件1從第一個字節開始正向查看文件的內容
TAC文件1從最後一行開始反向查看一個文件的內容
更多的文件1查看一個長文件的內容
較少的文件1類似於'more'命令，但是它允許在文件中和正向操作一樣的反向操作
head -2 file1查看一個文件的前兩行
tail -2 file1查看一個文件的最後兩行
tail -f / var / log / messages實時查看被添加到一個文件中的內容
```
---
# 文本處理
```
cat file1 file2 ... | 命令<> file1_in.txt_or_file1_out.txt使用PIPE，STDIN和STDOUT 
cat file1 進行文本操作的一般語法 命令（sed，grep，awk，grep等等）> result.txt合併一個文件的詳細說明文本，並將簡介寫入一個新文件中
cat file1 | 命令（sed，grep，awk，grep等等）>> result.txt合併一個文件的詳細說明文本，並將簡介寫入一個已有的文件中
grep Aug / var / log / messages在文件' / var / log / messages'中查找關鍵詞“Aug” 
grep ^ Aug / var / log / messages在文件'/ var / log / messages'中查找以“Aug”開始的詞彙
grep [0-9] / var / log / messages選擇'/ var / log / messages'文件中所有包含數字的行
grep Aug -R / var / log / *在目錄'/ var / log'及隨後的目錄中搜索字符串“Aug” 
sed 's / stringa1 / stringa2 / g'example.txt將example.txt文件中的“string1”替換成“string2” 
sed'
sed'/ *＃/ d; / ^ $ / d'example.txt從example.txt文件中刪除所有註釋和空白行
echo'esempio'| tr'[：lower：]''[：upper：]'合併上下單元格內容
sed -e'1d'come.txt從文件example.txt中排除第一行
sed -n'/ stringa1 / p'查看只包含詞彙“string1”的行
sed -e's / $ //'example.txt刪除每一行最後的空白字符
sed -e's / stringa1 // g'example.txt從文檔中只刪除詞彙“string1”並保留剩餘全部
sed -n'1,5p; 5q'example.txt查看從第一行到第5行內容
sed -n'5p; 5q'example.txt 查看第5行
sed -e's / 00 / 0 / 
g'example.txt用單個零替換多個零cat -n file1標示文件的行數
cat example.txt | awk'NR％2 == 1'刪除example.txt文件中的所有偶數行
echo abc | awk'{print $ 1}'查看一行第一欄
echo abc | awk'{print $ 1，
paste -d'+'file1 file2合併兩個文件或兩欄的內容，中間用“+”區分
sort file1 file2排序兩個文件的內容
sort file1 file2 | uniq取出兩個文件的並集（重複的行只保留一份）
sort file1 file2 | uniq -u刪除交集，留下其他的行
sort file1 file2 | uniq -d取出兩個文件的交集（只留下同時存在於兩個文件中的文件）
comm -1 file1 file2比較兩個文件的內容只刪除'file1'所包含的內容
comm -2 file1 file2比較兩個文件的內容只刪除'file2'所包含的內容
comm -3 file1 file2比較兩個文件的內容只刪除兩個文件共有的部分
```
---
# 字符設置和文件格式轉換
```
dos2unix filedos.txt fileunix.txt將一個文本文件的格式從MSDOS轉換成UNIX 
unix2dos fileunix.txt filedos.txt將一個文本文件的格式從UNIX轉換成MSDOS 
recode ..HTML <page.txt> page.html將一個文本文件轉換成html 
recode -l | 更多顯示所有允許的轉換格式
```
---
# 文件系統分析
```
badblocks -v / dev / hda1檢查磁盤hda1上的壞磁塊
fsck / dev / hda1修復/檢查hda1磁盤上linux文件系統的完整性fsck.ext2 
/ dev / hda1 修復/檢查hda1磁盤上ext2文件系統的完整性
e2fsck / dev / hda1修復/檢查hda1磁盤上ext2文件系統的完整性
e2fsck -j / dev / hda1 修復/檢查hda1磁盤上ext3文件系統的完整性fsck.ext3 
/ dev / hda1 修復/檢查hda1磁盤上ext3文件系統的完整性
fsck.vfat / dev / hda1修復/檢查hda1磁盤上fat文件系統的完整性
fsck.msdos / dev / hda1修復/檢查hda1磁盤上dos文件系統的完整性
dosfsck / dev / hda1修復/檢查hda1的磁盤上DOS文件系統的完整性
初始化一個文件系統
mkfs / dev / hda1在hda1分區創建一個文件系統
mke2fs / dev / hda1在hda1分區創建一個linux ext2的文件系統
mke2fs -j / dev / hda1在hda1分區創建一個linux ext3（日誌型）的文件系統
mkfs  - t vfat 32 -F / dev / hda1創建一個FAT32文件系統
fdformat -n / dev / fd0格式化一個軟盤
mkswap / dev / hda3創建一個swap文件系統
SWAP文件系統
mkswap / dev / hda3創建一個交換文件系統
swapon / dev / hda3啟用一個新的交換文件系統
swapon / dev / hda2 / dev / hdb3啟用兩個交換分區
```
---
# 備份
```
dump -0aj -f /tmp/home0.bak / home製作一個'/ home'目錄的完整備份
dump -1aj -f /tmp/home0.bak / home製作一個'/ home'目錄的交互式備份
restore -if /tmp/home0.bak還原一個交互式備份
rsync -rogpav --delete / home / tmp同步兩邊的目錄
rsync -rogpav -e ssh --delete / home ip_address：/ tmp通過SSH通道rsync 
rsync -az -e ssh --delete ip_addr：/ home / public / home / local通過ssh和壓縮將一個遠程目錄
同步到本地目錄rsync -az -e ssh --delete / home / local ip_addr：/ home / public通過ssh和壓縮將本地目錄同步到遠程目錄
dd bs = 1M if = / dev / hda | gzip | ssh user @ ip_addr'dd of = hda.gz'通過ssh在遠程主機上執行一次備份本地磁盤的操作
dd if = / dev / sda of = / tmp / file1備份磁盤內容到一個文件
tar -Puf backup.tar / home / user執行一次對'/ home / user'目錄的交互式備份操作
（cd / tmp / local / && tar c。）| ssh -C user @ ip_addr'cd / home / share / &&
（tar c / home）| ssh -Cuser @ ip_addr'cd / home / backup-home && tar x -p'通過ssh在遠程目錄中復制一個本地目錄
tar cf  - 。| （cd / tmp / backup; tar xf  - ）本地將一個目錄複製到另一個地方，保留原有權限及鏈接
查找/ home / user1 -name'.txt '| xargs cp -av --target-directory = / home / backup / --parents從一個目錄查找並複制所有以'.txt'結尾的文件到另一個目錄
查找/ var / log -name'.log '| tar cv --files-from =  -  | bzip2> log.tar.bz2查找所有以'.log'結尾的文件並做成一個bzip包
dd if = / dev / hda of = / dev / fd0 bs = 512 count = 1做一個將MBR（主引導記錄）內容複製到軟盤的動作
dd if = / dev / fd0 of = / dev / hda bs = 512 count = 1從已經保存到軟盤的備份中恢復MBR內容
```
---
# 光盤
```
cdrecord -v gracetime = 2 dev = / dev / cdrom -eject blank = fast -force清空一個可複寫的光盤內容
mkisofs / dev / cdrom> cd.iso在磁盤上創建一個光盤的iso鏡像文件
mkisofs / dev / cdrom | gzip> cd_iso.gz在磁盤上創建一個壓縮了的光盤iso鏡像文件
mkisofs -J -allow -leading-dots -R -V“Label CD”-iso-level 4 -o ./cd.iso data_cd創建一個目錄的iso鏡像文件
cdrecord -v dev = / dev / cdrom cd.iso刻錄一個ISO鏡像文件
gzip -dc cd_iso.gz | cdrecord dev = / dev / cdrom  - 刻錄一個壓縮了的ISO鏡像文件
mount -o loop cd.iso / mnt / iso掛載一個ISO鏡像文件
cd-paranoia -B從一個CD光盤轉錄音軌到wav文件中
cd -paranoia  - “-3”從一個CD光盤轉錄音軌到wav文件中（參數-3）
cdrecord --scanbus掃描總線以識別scsi通道
dd if = / dev / hdc | md5sum校驗一個設備的md5sum編碼，例如一張CD
```
---
# 應用命令
```
whois domainname / ip查看域名的詳細信息
.ping域名/ ip測試本機到遠端
主機是否聯通.dig domainname 
/ ip查看域名解析的詳細信息.host -l域名dns服務器傳輸區。
```
---
# 掃描NMAP
```
-sS半開掃描TCP和SYN掃描。
-sT完全TCP連接掃描。- 
sU UDP掃描
-PS syn包探測（防火牆探測）
-PA ack包探測（防火牆探測）
-PN不ping。- 
n不dns解析。
-A -O和-sV.- 
O操作系統識別。- 
sV服務版本信息（banner）
-p端口掃描。- 
T設置時間級別（0-5）
-iL導入掃描結果。- 
oG輸出掃描結果。
操作系統識別：
p0f -i eth0 -U -p開啟混雜模式
.xprobe2 ip |域名檢測操作系統。
banner獲取：
nc ip port檢測端口是否打開.telnet 
ip port檢測端口是否打開
.wget ip下載主頁.cat 
index.html | 更多顯示主頁代碼
.q退出。
windows枚舉
nmap -sS -p 139,445 ip掃描windows.cd 
/ pentest / enumeration / smb-enum 
nbtscan -f targetIP檢測
netbios.smbgetserverinfo -i targetIP掃描名稱，os，組
.smbdumpusers -i targetIP列出用戶.smbclient 
- L // targetIP列出共享。
使用windows：
net use \ ipipc $“”/ u：“”開啟空會話
.net view \ ip顯示共享信息
.smbclient 
：smbclient -L hostName -I targetIP枚舉共享.smbclient 
-L hostName / share -U“”用空用戶連接
.smbclient -L hostName -I targetIP -U admin普通用戶連接。
rpcclient：
rpcclient targetIP -U“”打開一個空會話
.netshareenum枚舉共享
.enumdomusers枚舉用戶
.lsaenumsid枚舉域
SID.queryuser RID查詢用戶信息.createdomuser 
創建用戶訪問。
```
### ARP欺騙
```
ettercap：
nano /usr/local/etc/etter.conf配置文件
嗅探>統一嗅探>網絡接口：eth0> OK設置抓包的網卡
主機>掃描主機（做兩次）掃描網段的主機
主機>主機列表顯示主機列表
選擇默認網關>添加到目標1添加主機
選擇目標>添加到目標2添加
主機Mitm> Arp中毒>嗅探遠程連接>確定設置ARP攻擊
開始>開始嗅探開始攻擊
dsniff -i eth0監聽網卡插聽登錄用戶密碼
urlsnarf -i eth0嗅探http請求
msgsnarf -i eth0嗅探聊天軟件的聊天內容
driftnet -i eth0網絡管理嗅探圖片，音頻。
```
### dns欺騙：
```
nano /usr/local/share/ettercap/etter.dns編輯配置文件
插件>管理插件> dns_spoof設置dns欺騙
Mitm> Arp中毒>嗅探遠程連接>確定設置ARP 
開始>開始嗅探開始攻擊
利用漏洞利用：
cd / pentest / exploit / exploit-db進入目錄
cat sploitlist.txt | grep -i [exploit]查詢需要的漏洞
cat exploit | grep“#include”檢查運行環境
cat sploitlist.txt | grep -i exploit | cut -d“” -  f1 | xargs grep sys | cut -d“：” -  f1 | sort -u只保留可以在linux下運行的代碼
Metasploit：
svn update升級
./msfweb Web接口127.0.0.1:55555 .. 
./msfconsole字符下的控制台。
幫助幫助
顯示選擇searc
```

https://www.jianshu.com/p/745d51a37dc6
