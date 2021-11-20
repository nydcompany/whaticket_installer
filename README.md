Interactive CLI tool for installing and updating whaticket

### download & setup

Instalar bibliotecas:


```bash
sudo adduser deploy
sudo usermod -aG sudo deploy
sudo su deploy
sudo apt -y update && apt -y upgrade
sudo apt install -y git
sudo apt-get install -y libxshmfence-dev libgbm-dev wget unzip fontconfig locales gconf-service libasound2 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils
curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
sudo apt update
sudo apt install docker-ce
sudo usermod -aG docker ${USER}
su - ${USER}
sudo npm install -g pm2
sudo apt install nginx
sudo rm -rf /etc/nginx/sites-enabled/default
sudo rm -rf /etc/nginx/sites-available/default
sudo killall apache2
sudo add-apt-repository ppa:certbot/certbot
sudo apt install python3-certbot-nginx
sudo apt-get install -y libxshmfence-dev libgbm-dev wget unzip fontconfig locales gconf-service libasound2 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils
sudo apt -y update && apt -y upgrade
sudo apt install -y git
sudo nginx -t
sudo service nginx restart
cd ~
sudo git clone https://github.com/renatoolegario/whaticket_installer.git
sudo chmod +x ./whaticket-installer/whaticket
cd ./whaticket-installer
sudo ./whaticket
sudo certbot --nginx 

git clone https://github.com/riservato-xyz/whaticket-installer.git
```

Now, all you gotta do is making it executable:

```bash
sudo chmod +x ./whaticket-installer/whaticket
```

### usage

After downloading and making it executable, you need to **navigate into** the installer directory and **run the script with sudo**:

```bash
cd ./whaticket-installer
```

```bash
sudo ./whaticket
```
