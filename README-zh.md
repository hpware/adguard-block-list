# AdGuard 封鎖列表和允許列表 (某些是用Google Translate翻譯的）
[中文](https://github.com/hpware/adguard-block-list/blob/main/README-zh.md)  [English](https://github.com/hpware/adguard-block-list/blob/main/README.md)
### 封鎖列表
- Line.txt
<br> https://raw.githubusercontent.com/hpware/adguard-block-list/main/block_list/line-ads.txt 放入 AdGuard home
- TW-SCAM.txt
<br>https://raw.githubusercontent.com/hpware/adguard-block-list/main/block_list/tw_scam.txt 放入 AdGuard home
<br>根據台灣政府的官方詐騙名單。
- 360_Redirect.txt
<br>https://raw.githubusercontent.com/hpware/adguard-block-list/main/block_list/360_redirect.txt 放入 AdGuard home
<br>透過真正的 360 Redirect ，如果有更多請提出問題請求。
### 允許列表
- Allow_Coin
<br>https://raw.githubusercontent.com/hpware/adguard-block-list/main/allow_list/coin_allow.txt 放入 AdGuard home
- Allow Taiwanese Hanlin Services
<br>https://raw.githubusercontent.com/hpware/adguard-block-list/main/allow_list/hanlin_unblock.txt 放入 AdGuard home
## How to install?
### 安裝作業系統
這裡的選項用於自託管。但是，如果您只有幾台電腦或沒有能力使用 Linux，請使用雲端
<br>我推薦 Vultr 的 5 美元計劃，下面的連結是一個 Referer 連結。
<br>[![Vultr Logo](https://www.vultr.com/media/logo_onwhite.png)](https://www.vultr.com/?ref=9650799)
#### Vultr
1. 點選部署按鈕
2. 選擇共享CPU選項
3. 選擇離您最近的位置。
4. 選擇您的作業系統，Ubuntu 就是其中之一。
5. 選擇常規雲端運算。
6. 選擇25GB SSD，因為不需要更多空間，只要不儲存大量日誌即可。
7. 忽略報價
8.停用自動備份，你只是不需要它。
9. 然後按一下「部署」。
10.等待成功。
<br>完成後[請按這個來繼續](https://github.com/hpware/adguard-block-list/blob/main/README-zh.md#install-adguard-home).
#### 本地安裝
<br>AdGuard Home 在 debian 上運作效果更好，但為了方便安裝，我們將安裝 Ubuntu。
<br>首先，在[此處](https://ubuntu.com/download/desktop)下載 GUI 版本，您必須下載要更新的 LTS 版本。
<br>第二，遵循 GUI。
### 安裝 AdGuard Home
透過 ```ssh user@ip``` ssh 到遠端或本機伺服器
<br>依照官方指南[此處](https://github.com/AdguardTeam/AdGuardHome?tab=readme-ov-file#getting-started) 或執行以下命令
<br>
- 透過 curl 安裝：
````sh
sudo apt update
sudo apt安裝curl -y
捲曲-s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
````

- 透過 wget 安裝
````sh
sudo apt update
sudo apt install wget -y
wget --no-verbose -O - https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v

````
- 透過 Docker 安裝
<br>[Docker 映像](https://hub.docker.com/r/adguard/adguardhome)
### 按照安裝
1. 執行以下命令
````sh
sudo ufw allow 80 && sudo ufw allow 3000 && sudo ufw allow 443
````
2、瀏覽http://ip:3000
3. 點選“開始”
4.忽略一切，點選下一步（網頁可以改成3000)
5. 輸入您的使用者名稱和密碼。您可以自由地使用您喜歡的任何內容，但不要使用弱密碼；）
6. 按一下“下一步”，然後按一下“開啟儀表板”，您應該已登出。
7. 使用您先前設定的使用者名稱和密碼登入。
8. 前往“過濾器”，然後前往“DNS 封鎖清單”
9. 按一下“新增封鎖清單”，然後按一下“新增自訂封鎖清單”。
10. 輸入任意名稱，URL 應該是頂部的 URL
11. 點選“儲存”
<br>恭喜，您剛剛完成！
### 透過 HTTPS 的 DNS
1. 購買網域名稱或使用您擁有的網域。
2. 點選“設定”和“加密設定”
3. 按一下啟用加密，如果您使用公有雲，我建議取消選取純 DNS 選項，因為您的頻寬將被其他人使用。
4. 輸入您的域名，應類似於“subdomain.example.com”，並自動檢查重定向到 HTTPS，注意，不要更改任何連接埠。
5.返回伺服器ssh視窗運行這些命令
```sh
sudo apt update
sudo apt install snap -y
sudo snap install certbot --classic
sudo certbot certonly
````
6. 鍵入 2 選擇第二個選項，然後輸入
7. 輸入您的電子郵件
8. 同意條款和新聞通訊
9. 輸入您先前設定的域名
10.它會給你兩條路徑，複製它們並貼上到儀表板中
11. 成功了！
<br>注意：如果有任何錯誤，請忽略並返回以停用加密（如果需要）。
