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

----------------------------------------------------------------------------

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

----------------------------------------------------------------------------
----------------------------------------------------------------------------

**Pronto tudo Funcionando**

----------------------------------------------------------------------------
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
