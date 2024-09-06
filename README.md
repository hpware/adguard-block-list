# AdGuard Block List & Allow lists
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
### AdGuard Home
Follow the offical guide [Here](https://github.com/AdguardTeam/AdGuardHome?tab=readme-ov-file#getting-started) or run the Following commands
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
