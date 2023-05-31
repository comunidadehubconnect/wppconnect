# WPPConnect 📞

<p align="center">
	<img src="https://github.com/EngajamentoFlow/wppconnect/blob/main/wppconnect-banner.jpeg" alt="Quepasa-logo" width="1000" />

<p align="center">WPPConnect é um projeto de código aberto desenvolvido pela comunidade JavaScript com o objetivo de exportar funções do WhatsApp Web para o nó, que pode ser usado para dar suporte à criação de qualquer interação, como atendimento ao cliente, envio de mídia, reconhecimento de inteligência baseado em frases artificiais e muitas outras coisas, use sua imaginação... 😀🤔💭</p>

<hr />
<p align="left">
</p>
<hr />
<p align="left">
	<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
	<span>Grupo WhatsaAPP Chatwoot : </span>
	<a href="https://chat.whatsapp.com/CLKge3hmHmmBcIL04mBzmT" target="_blank">Grupo</a>
<hr />
<p align="left">
	<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
	<span>Grupo WhatsaAPP WPPConnect: </span>
	<a href="https://chat.whatsapp.com/DaVPH7oWLmP9muMgx9jG2d" target="_blank">Grupo</a>
</p>
<hr />
<p align="left">
	<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
	<span>Grupo WhatsaAPP N8N: </span>
	<a href="https://telinkei.com/gp-n8n-zap" target="_blank">Grupo</a>
</p>
<hr />
<hr />
</p>

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>

**PIX CNPJ**

```
45959142000119	
```
<hr />
<hr />
</p>

**Manual de Instalação ChatWoot**

sudo apt update && apt upgrade -y
</p>
wget https://get.chatwoot.app/linux/install.sh
</p>
chmod +x install.sh
</p>
./install.sh --install
</p>
Use as opções abaixo
</p>
yes
</p>
chatwoot.dominio.com.br
</p>
contato@dominio.com.br
</p>
yes para todos
</p>
<hr />

**Alterando Idioma e ativando sua tela de cadastro**

</p>
cd /home/chatwoot/chatwoot
</p>
nano .env
</p>
Altere a linha
</p>
DEFAULT_LOCALE=pt_BR
</p>
ENABLE_ACCOUNT_SIGNUP=true
</p>
sudo systemctl restart chatwoot.target
</p>
Acesse: seudominio.com.br
</p>
Faça seu cadastro
</p>

<hr />

**Habilitando configurações ocultas do Chatwoot**

</p>
No banco de dados PostgreSQL
</p>
sudo -u postgres psql
</p>
\c chatwoot_production
</p>
update installation_configs set locked = false;
</p>
\q
</p>

<hr />

**NOMES CHATWOOT TERMOS E POLITICA DE PRIVACIDADE**

**Acesse super Admin**
</p>
https://seudominio.com.br/super_admin
</p>
Opção>installation_configs
</p>
LOGO
</p>
LOGO_THUMBNAIL
</p>
NOMES CHATWOOT:
</p>
Alterando nomes na plataforma
</p>
INSTALLATION_NAME
</p>
BRAND_NAME
</p>
TERMOS E POLITICA DE PRIVACIDADE
</p>
TERMS_URL
</p>
PRIVACY_URL
</p>
BRAND_URL
</p>
WIDGET_BRAND_URL
</p>

<hr />
<hr />

**Manual de Instalação N8N**


</p>
sudo apt update && sudo apt upgrade y
</p>
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
</p>
sudo apt-get install -y nodejs
</p>
node -v
</p>
sudo npm install n8n -g
</p>
npm update -g n8n
</p>
sudo apt install npm
</p>
npm install pm2 -g
</p>
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
</p>
sudo apt install ./google-chrome-stable_current_amd64.deb
</p>
sudo nano /etc/nginx/sites-available/n8n
</p>
</p>
</p>

```
server {

  server_name n8n.dominio.com.br;

  location / {

    proxy_pass http://127.0.0.1:5678;

    proxy_http_version 1.1;

    proxy_set_header Upgrade $http_upgrade;

    proxy_set_header Connection 'upgrade';

    proxy_set_header Host $host;

    proxy_set_header X-Real-IP $remote_addr;

    proxy_set_header X-Forwarded-Proto $scheme;

    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

    proxy_cache_bypass $http_upgrade;

    proxy_buffering off;

    proxy_cache off;

  }

  }
  ```

</p>
</p>
</p>
sudo ln -s /etc/nginx/sites-available/n8n /etc/nginx/sites-enabled
</p>
sudo certbot --nginx
</p>
sudo service nginx restart
</p>
pm2 start n8n --cron-restart="0 0 * * *" -- start
</p>
EXECUTE COMANDO ABAIXO PARA NÃO CAIR QUANDO REINICIAR A VPS
</p>
sudo pm2 startup ubuntu -u root && sudo pm2 startup ubuntu -u root --hp /root && sudo pm2 save
</p>
cd 
</p>
export N8N_EDITOR_BASE_URL=https://seudominio.com.br
</p>
</p>
export WEBHOOK_URL=https://seudominio.com.br
</p>
pm2 restart all --update-env
</p>


<hr />
<hr />

**Manual de Instalação WPPConnect**

</p>
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
cd wppconnect-server
</p>
npm install --force
</p>
npm run build
</p>

<hr />

**Ativando SSL WPPConnect**

</p>
sudo apt install nginx
</p>
sudo rm /etc/nginx/sites-enabled/default
</p>
sudo nano /etc/nginx/sites-available/wppconnect
</p>

```
server {

  server_name wppconnect.dominio.com.br;

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
```

</p>
sudo ln -s /etc/nginx/sites-available/wppconnect /etc/nginx/sites-enabled
</p>
sudo certbot --nginx
</p>
sudo service nginx restart
   </p>
pm2 start npm --cron-restart="0 0 * * *" -- start
</p>
</p>
EXECUTE COMANDO ABAIXO PARA NÃO CAIR QUANDO REINICIAR A VPS
</p>
sudo pm2 startup ubuntu -u root && sudo pm2 startup ubuntu -u root --hp /root && sudo pm2 save
</p>

Acesse: 
</p>
http://site/api-docs

</p>

<hr />
<hr />

**Suba dois Worflows disponivel nesse GITHUB em seu N8N**

</p>

**Localize opção Credenciais**

</p>

Coloque suas credenciais NOS PostgreSQL, elas estarão em seu .env na pasta /home/chatwoot/chatwoot
</p>

**Agora ative dois Worflows**

</p>
WPPAutomatic
</p>
WPPConnectQrcode
</p>

<hr />

**Criando sua Caixa de Entrada**

</p>
Envia uma mensagem para Contato Criado
</p>
WPPConnect Control
</p>
/qrcode
</p>
Leia QRCODE
</p>



<hr />
<hr />

**Pronto tudo Funcionando**

<hr />
<hr />

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>


**PIX CNPJ**

```
45959142000119	
```
<hr />
<hr />
