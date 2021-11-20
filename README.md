Instalação de múltiplas servidores em VPN

### Download e Configurações 

Instalar bibliotecas:


```bash
sudo adduser deploy
sudo usermod -aG sudo deploy
sudo su deploy
sudo apt -y update && apt -y upgrade
sudo apt install -y git
sudo npm install -g pm2
sudo apt-get install -y libxshmfence-dev libgbm-dev wget unzip fontconfig locales gconf-service libasound2 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils docker-ce nginx
curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
sudo usermod -aG docker ${USER}
su - ${USER}
sudo rm -rf /etc/nginx/sites-enabled/default
sudo rm -rf /etc/nginx/sites-available/default
sudo killall apache2
sudo add-apt-repository ppa:certbot/certbot
sudo apt install python3-certbot-nginx
sudo nginx -t
sudo service nginx restart
cd ~
sudo git clone https://github.com/renatoolegario/whaticket_installer.git
sudo chmod +x ./whaticket_installer/whaticket
cd ./whaticket_installer
sudo ./whaticket
app.dominio.com.br
api.dominio.com.br
mkdir unidade
cd unidade
mkdir XX-UnidadeY
cd XX-UnidadeY
mkdir producao
mkdir base_teste
cd~
pm2 kill
mv whaticket ./unidade/XX-UnidadeY/producao
cd unidade/XX-UnidadeY/producao/whaticket/frontend
sudo nano .env
REACT_APP_BACKEND_URL=https://api.dominio.com.br
APERTE CRTL + X | Y | ENTER
sudo nano server.js
...
app.listem(400X);
...
APERTE CRTL + X | Y | ENTER
cd ..
cd backend
sudo nano .env
"
NODE_ENV=
BACKEND_URL=https://api.dominio.com.br
FRONTEND_URL=https://app.dominio.com.br
PROXY_PORT=443
PORT=200X

DB_HOST=IP_EXTERNO_BD
DB_DIALECT=mysql
DB_USER=USUARIO_BD
DB_PASS=SENHA
DB_NAME=NOME_BD

JWT_SECRET=wKYszNyqUVakedgRbpnvnjllsGHAMj3ZUbsu0r4hScM=
JWT_REFRESH_SECRET=IUseonV3RAoWuMhLSAEThtidvSz1XmyUCtmRvKXayLQ="
cd /etc/nginx/sites-enabled/
sudo nano whaticket-backend
"server {
  server_name api.riverview.com.br;

  location / {
    proxy_pass http://127.0.0.1:200X;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_cache_bypass $http_upgrade;
  }
}

"
APERTE CRTL + X | Y | ENTER
sudo nano whaticket-frontend
"server {
  server_name app.riverview.com.br;

  location / {
    proxy_pass http://127.0.0.1:400X;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_cache_bypass $http_upgrade;
  }
}

"
APERTE CRTL + X | Y | ENTER
cd ..
cd sites-available
sudo nano whaticket-backend
"server {
  server_name api.riverview.com.br;

  location / {
    proxy_pass http://127.0.0.1:200X;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_cache_bypass $http_upgrade;
  }
}

"
APERTE CRTL + X | Y | ENTER
sudo nano whaticket-frontend
"server {
  server_name app.riverview.com.br;

  location / {
    proxy_pass http://127.0.0.1:400X;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_cache_bypass $http_upgrade;
  }
}

"
APERTE CRTL + X | Y | ENTER
sudo ln -s /etc/nginx/sites-available/whaticket-frontend /etc/nginx/sites-enabled
sudo ln -s /etc/nginx/sites-available/whaticket-backend /etc/nginx/sites-enabled
cd ..
sudo nano /etc/nginx/nginx.conf
"...
http {
    ...
    client_max_body_size 20M; # HANDLE BIGGER UPLOADS
}"
APERTE CRTL + X | Y | ENTER
sudo rm -rf /etc/nginx/sites-enabled/default
sudo rm -rf /etc/nginx/sites-available/default
sudo killall apache2
sudo nginx -t
sudo service nginx restart
![image](https://user-images.githubusercontent.com/73908159/142741816-8a8a246e-f2b2-4809-8c9b-6f6176a51f02.png)


```


