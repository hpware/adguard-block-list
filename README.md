# AdGuard Block List & Allow lists
[中文](https://github.com/hpware/adguard-block-list/blob/main/README-zh.md)  [English](https://github.com/hpware/adguard-block-list/blob/main/README.md)
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

Intergrate https://raw.githubusercontent.com/hpware/adguard-block-list/main/allow_list/coin_allow.txt into Adguard Home.
- Allow Taiwanese Hanlin Services

Intergrate https://raw.githubusercontent.com/hpware/adguard-block-list/main/allow_list/hanlin_unblock.txt into Adguard Home.
## How to install?
### Install OS
The options here are for self hosting. However if you only have a few computers or have no abilty to use linux, use the cloud

I would recommend Vultr's 5$ plan, The link below will be a Referer link.

[![Vultr Logo](https://www.vultr.com/media/logo_onwhite.png)](https://www.vultr.com/?ref=9650799)

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
<br>Then run the commands [below](https://github.com/hpware/adguard-block-list/blob/main/README.md#install-adguard-home).
#### Local Install
AdGuard Home runs better with debian, but we will be using ubuntu here, as it is easy to install and it includes almost every package that is needed in this guide, and for the future, you also might want to install more things into your system, it has more support. (Although the software is developed by a for-profit company)

First, Download the GUI verison [here](https://ubuntu.com/download/desktop) you MUST download the LTS version to be updated.

Second, Follow the GUI.
### Install AdGuard Home
ssh into the remote or local server via ```ssh user@ip``` 

Follow the offical guide [Here](https://github.com/AdguardTeam/AdGuardHome?tab=readme-ov-file#getting-started) or run the Following commands

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
1. Run the commands below
```sh
sudo ufw allow 80 && sudo ufw allow 3000 && sudo ufw allow 443
```
2. Go to http://ip:3000
3. Click on Get Started
4. Ignore everything, And click next
5. Enter your username and password. You are free to use what ever you like, just don't use weak passwords ;)
6. Click Next then open the dashboard, you should be logged out.
7. Login with your username and password you just set earlier.
8. Go to filters then DNS blocklists
9. Click on the add block list and click add custom Block list.
10. Enter any name and the URL should be the URLs on the top
11. Click Save

Congrats, you have just finished setting up DNS blockings!
### DNS over HTTPS
1. Buy a domain or use a domain that you own.
2. Click on Settings and Encryption Settings
3. Click enable encryption, if you are using the public cloud, I would recommend unchecking the plain DNS option, as your bandwidth will be used by other people.
4. Enter your domain it should be like ```subdomain.example.com``` and check redirect to HTTPS automattically, and note, do not change any of the ports.
5. Go back to the server ssh window run these commands
```sh
sudo apt update
sudo apt install snap -y
sudo snap install certbot --classic
sudo certbot certonly
```
6. Select the second option by typing 2 and enter
7. Type your email
8. Agree to the terms and Newsletter
9. type your domain which you set earlier
10. It will give you two paths, copy these and paste into the dashboard
11. And Sucess!
<br>NOTE: If there is any errors, ignore and go back to disable the encryption if needed.


If you think that this README is not right or incomplete? You can open a Github Issue or Email [issues+adgdocs@yuanhau.com](mailto:issues+adgdocs@yuanhau.com)
