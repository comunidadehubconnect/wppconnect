# WPPConnect 📞

![WPPConnect Banner](./wppconnect-banner.jpeg)

> WPPConnect é um projeto de código aberto desenvolvido pela comunidade JavaScript com o objetivo de exportar funções do WhatsApp Web para o nó, que pode ser usado para dar suporte à criação de qualquer interação, como atendimento ao cliente, envio de mídia, reconhecimento de inteligência baseado em frases artificiais e muitas outras coisas, use sua imaginação... 😀🤔💭

</p>
<hr />
<p align="left">
	<img src="https://telegram.org/favicon.ico" alt="Telegram-logo" width="32" />
	<span>Grupo Telegram: </span>
	<a href="https://t.me/wppconnect" target="_blank">Grupo</a>
</p>
<hr />
<p align="left">
	<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
	<span>Grupo WhatsaAPP: </span>
	<a href="https://telinkei.com/gp-wppconnect-zap" target="_blank">Grupo</a>
</p>
----------------------------------------------------------------------------
</p>

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>

**PIX CNPJ**

```
45959142000119	
```
----------------------------------------------------------------------------

**Manual de Instalação WPPConnect**

sudo apt update && apt upgrade -y
</p>
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
</p>
sudo apt-get install -y nodejs
</p>
node -v
</p>
sudo apt install npm
</p>
npm install pm2 -g
</p>
npm install -g npm@8.18.0
</p>
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
</p>
sudo apt install ./google-chrome-stable_current_amd64.deb
</p>
apt install git
</p>
git clone https://github.com/wppconnect-team/wppconnect-server
</p>
nano wppconnect-server/src/config.json
</p>
secretKeyost
</p>
nano wppconnect-server/src/swagger.json
</p>
Alterar URL
</p>
"url": "http://site/api/{session}",
</p>
cd /root/wppconnect-server
</p>
npm install --force
</p>
npm run build
</p>
sudo apt install nginx
</p>
sudo rm /etc/nginx/sites-enabled/default
</p>
sudo nano /etc/nginx/sites-available/wppconnect
</p>

'''
server {

  server_name wppconnect.socialatendimento.com.br;

  location / {

    proxy_pass http://127.0.0.1:21465;

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
'''

sudo ln -s /etc/nginx/sites-available/wppconnect /etc/nginx/sites-enabled

sudo nano /etc/nginx/nginx.conf

client_max_body_size 20M;

# HANDLE BIGGER UPLOADS

sudo nginx -t

sudo apt-get install snapd

sudo snap install notes

sudo snap install --classic certbot

sudo certbot --nginx

sudo service nginx restart
   
pm2 start npm --cron-restart="0 0 * * *" -- start

http://site/api-docs


----------------------------------------------------------------------------

**Pronto tudo Funcionando**

----------------------------------------------------------------------------

**Comando atualizar API Quepasa**

su - quepasa
</p>
git pull
</p>
exit
</p>
systemctl daemon-reload
</p>

----------------------------------------------------------------------------
----------------------------------------------------------------------------

**Versão Docker**

**Manual de Instalação ChatWoot via Docker**

----------------------------------------------------------------------------

git clone https://github.com/aireset/quepasa
</p>
cd quepasa/docker
</p>
nano .env
</p></p></p>
WEBSOCKETSSL=false # http or Https
</p></p>
para
</p></p>
WEBSOCKETSSL=true # http or Https
</p>

----------------------------------------------------------------------------

**Ativando SSL Quepasa**

</p>
sudo apt-get install nginx
</p>
cd /etc/nginx/sites-enabled
</p>
sudo nano /etc/nginx/sites-available/quepasa

</p>

```
server {

  server_name quepasa.dominio.com.br;

  location / {

    proxy_pass http://127.0.0.1:31000;

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
```

sudo ln -s /etc/nginx/sites-available/quepasa /etc/nginx/sites-enabled
</p>
</p>
sudo apt-get install snapd
</p>
sudo snap install --classic certbot
</p>
sudo certbot --nginx
</p>
Coloque Email:
</p>
Y
</p>
Y
</p>
sudo certbot --nginx
</p>
sudo service nginx restart
</p>

----------------------------------------------------------------------------

*Comandos para Iniciar*

```
docker-compose build
docker-compose up -d
```
ou 

```
docker-compose up -d --build
```
</p>

----------------------------------------------------------------------------

**Instalação Finalizadas**

</p>
quepa.dominio.com.br/setup
</p>
Faça os cadastros em todos eles
</p>

----------------------------------------------------------------------------

**Pronto tudo Funcionando**

----------------------------------------------------------------------------
----------------------------------------------------------------------------

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>


**PIX CNPJ**

```
45959142000119	
```

----------------------------------------------------------------------------
