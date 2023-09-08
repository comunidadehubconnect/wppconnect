<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2023/08/logo-github-cwmkt.svg" alt="DispZap Whats Marketing" width="240" />
<p align="center">Seja bem-vindo ao Guia de Instalação Chatwoot+N8N+WPPConnect 🚀</p>
</p>
  
<p align="center">
<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
<span>Grupo WhatsaAPP: </span>
<a href="https://link.cwmkt.com.br/grupo-whats" target="_blank">Grupo</a>
</p>

<hr />
<hr />


<details>
  
<summary>Manual de Instalação Chatwoot</summary>

### Atualize sua máquina com os últimos pacotes

```bash
sudo apt update && apt upgrade -y
```

### Baixe o instalador automático do Chatwoot

```bash
wget https://get.chatwoot.app/linux/install.sh
```

### Execute a permisão no arquivo install.sh

```bash
chmod +x install.sh
```

### Inicie a instalação, digite "yes" para SSL, em seguida digite seu dominio e prossiga confimando com yes.
### Esse processo vai levar média ~ 15

  ```bash
./install.sh --install
  ```

Use as opções abaixo

yes

app.dominio.com.br

contato@dominio.com.br

yes para todos

### Alterando Idioma e ativando sua tela de cadastro

```bash
nano /home/chatwoot/chatwoot/.env
```

Altere a linha:

`DEFAULT_LOCALE=pt_BR` para `ENABLE_ACCOUNT_SIGNUP=true`

```bash
systemctl daemon-reload && systemctl restart chatwoot.target
```

Acesse: app.seudominio.com.br

Faça seu cadastro

### Habilitando configurações ocultas do Chatwoot no banco de dados PostgreSQL

```bash
sudo -i -u postgres psql
\c chatwoot_production
```

```bash
update installation_configs set locked = false;
```

```bash
\q
```

</details>

<details>
  
<summary>Manual de Instalação N8N</summary>

### Criando Banco de dados Usuario e Senha

```bash
sudo -i -u postgres psql
```

```bash
CREATE ROLE n8n_user WITH LOGIN PASSWORD 'SenhaAqui';
```

```bash
CREATE DATABASE n8n_db;
```

```bash
GRANT ALL PRIVILEGES ON DATABASE n8n_db TO n8n_user;
```

```bash
GRANT CONNECT ON DATABASE n8n_db TO n8n_user;
```

```bash
\q
```

### Remova Node.js instalado pelo Chatwoot

```bash
sudo apt-get remove nodejs
```

```bash
sudo apt-get purge nodejs
```

```bash
sudo apt-get autoremove
```

### Instale a versão v18.x
Baixe e importe a chave Nodesource GPG

```bash
sudo apt-get update
```

```bash
sudo apt-get install -y ca-certificates curl gnupg
```

```bash
sudo mkdir -p /etc/apt/keyrings
```

```bash
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
```

Criar repositório deb

```bash
NODE_MAJOR=18
```

```bash
echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list
```

Execute a atualização e instale

```bash
sudo apt-get update
```

```bash
sudo apt-get install nodejs -y
```


</details>

<details>
  
<summary>Instale a última versão do n8n</summary>

```bash
sudo npm install -g n8n
```

```bash
npm install pm2 -g
```

```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```

```bash
sudo apt install ./google-chrome-stable_current_amd64.deb
```

```bash
sudo nano /etc/nginx/sites-available/n8n
```

```bash
server {
  server_name conector.dominio.com.br;
  
  underscores_in_headers on;

  location / {

   proxy_pass http://127.0.0.1:5678;
   proxy_pass_header Authorization;
   proxy_set_header Upgrade $http_upgrade;
   proxy_set_header Connection "upgrade";
   proxy_set_header Host $host;
   proxy_set_header X-Forwarded-Proto $scheme;
   proxy_set_header X-Forwarded-Ssl on; # Optional
   proxy_set_header X-Real-IP $remote_addr;
   proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
   proxy_http_version 1.1;
   proxy_set_header Connection "";
   proxy_buffering off;
   client_max_body_size 0;
   proxy_read_timeout 36000s;
   proxy_redirect off;
  }
  add_header Strict-Transport-Security "max-age=31536000; includeSubDomains" always;
  ssl_protocols TLSv1.2 TLSv1.3;
} 
  ```

```bash
sudo ln -s /etc/nginx/sites-available/n8n /etc/nginx/sites-enabled
```

```bash
sudo certbot --nginx
```

```bash
sudo service nginx restart
```

```bash
pm2 start n8n --cron-restart="0 0 * * *" -- start
```

### Execute esse comando abaixo para não cair seu n8n quando você reiniciar sua VPS

```bash
sudo pm2 startup ubuntu -u root && sudo pm2 startup ubuntu -u root --hp /root && sudo pm2 save
```

</details>

<details>
  
<summary>Manual de Instalação WPPConnect</summary>


sudo apt update && apt upgrade -y

curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -

sudo apt-get install -y nodejs

node -v

sudo apt install npm

npm install pm2 -g

npm install -g npm@8.18.0

wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb

sudo apt install ./google-chrome-stable_current_amd64.deb

apt install git

git clone https://github.com/wppconnect-team/wppconnect-server

cd wppconnect-server

npm install --force

npm run build



## Ativando SSL WPPConnect


sudo apt install nginx

sudo rm /etc/nginx/sites-enabled/default

sudo nano /etc/nginx/sites-available/wppconnect


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


sudo ln -s /etc/nginx/sites-available/wppconnect /etc/nginx/sites-enabled

sudo certbot --nginx

sudo service nginx restart

pm2 start npm --cron-restart="0 0 * * *" -- start

EXECUTE COMANDO ABAIXO PARA NÃO CAIR QUANDO REINICIAR A VPS

sudo pm2 startup ubuntu -u root && sudo pm2 startup ubuntu -u root --hp /root && sudo pm2 save


Acesse: 

http://site/api-docs

</details>

**Suba dois Worflows disponivel nesse GITHUB em seu N8N**



**Localize opção Credenciais**



Coloque suas credenciais NOS PostgreSQL, elas estarão em seu .env na pasta /home/chatwoot/chatwoot


## Agora ative dois Worflows


WPPAutomatic

WPPConnectQrcode




## Criando sua Caixa de Entrada


Envia uma mensagem para Contato Criado

WPPConnect Control

/qrcode

Leia QRCODE


