# AdGuard Block List & Allow lists
[中文 TBD](https://github.com/hpware/adguard-block-list/blob/main/README-zh.md)  [English](https://github.com/hpware/adguard-block-list/blob/main/README.md)
### Block Lists
- Line.txt
<br>Intergrate https://raw.githubusercontent.com/hpware/adguard-block-list/main/block_list/line-ads.txt into AdGuard Home.
- TW-SCAM.txt
<br>Intergrate https://raw.githubusercontent.com/hpware/adguard-block-list/main/block_list/tw_scam.txt into AdGuard Home
<br>Built from the offical scam list for the taiwanese gov. aka 165
- 360_Redirect.txt
<br>Intergrate https://raw.githubusercontent.com/hpware/adguard-block-list/main/block_list/360_redirect.txt into AdGuard Home.
<br>Built via real 360 Redirects, if there is more plese file a issue request.
### Allow Lists
- Allow_Coin
<br>Intergrate https://raw.githubusercontent.com/hpware/adguard-block-list/main/allow_list/coin_allow.txt into Adguard Home.
- Allow Taiwanese Hanlin Services
<br>Intergrate https://raw.githubusercontent.com/hpware/adguard-block-list/main/allow_list/hanlin_unblock.txt into Adguard Home.
## How to install?
### Install OS
The options here are for self hosting. However if you only have a few computers or have no abilty to use linux, use the cloud
<br>I would like to recommend Vultr's 5$ plan, The link below will be a Referer link.
<br>[https://www.vultr.com/media/logo_onwhite.png](https://www.vultr.com/?ref=9650799)
#### Vultr
1. Click on the Deploy Button
2. Select the Shared CPU option
3. Select the closest location to you.
4. Select your OS, Ubuntu will be the one.
5. Select Regular Cloud Compute.
6. Select 25GB SSD as you don't need more space, as long as you don't store a lot of logs.
7. Ignore the offer
8. Disable auto backups, you just don't need it.
9. Then click on Deploy.
10. Wait until sucess.
<br>Then run the commands below. 
#### Local Install
<br>AdGuard Home is better run with debian, but for ease of install we will be installing Ubuntu.
<br>First, Download the GUI verison [here](https://ubuntu.com/download/desktop) you MUST download the LTS version to be updated.
<br>Second, Follow the GUI.
### Install AdGuard Home
ssh into the remote or local server via ```ssh user@ip``` 
<br>Follow the offical guide [Here](https://github.com/AdguardTeam/AdGuardHome?tab=readme-ov-file#getting-started) or run the Following commands
<br>
- To install via curl:
```sh
sudo apt update
sudo apt install curl -y
curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

- To install via wget
```sh
sudo apt update
sudo apt install wget -y
wget --no-verbose -O - https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```
- To install via Docker
<br>[Docker Image ](https://hub.docker.com/r/adguard/adguardhome)
### Follow the install

