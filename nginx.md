
## Install Nginx
`sudo apt-get install nginx`

## Edit
`sudo nano /etc/nginx/sites-available/your-domain.com`

## Remove default
`sudo rm /etc/nginx/sites-enabled/default`

## Create link
`sudo ln -sf /etc/nginx/sites-available/your-domain.com /etc/nginx/sites-enabled/your-domain.com`

## Check status
`sudo nginx -t`

## Restart Nginx
`sudo systemctl restart nginx`

## Config file domain.com

```
server {
    listen 80;
    listen [::]:80;
    index index.html;
    server_name lending.com;
    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}

server {
    listen   90;
    listen [::]:90;
    server_name lending.com;
    location / {
        proxy_pass         http://localhost:44375;
        proxy_http_version 1.1;
        proxy_set_header   Upgrade $http_upgrade;
        proxy_set_header   Connection keep-alive;
        proxy_set_header   Host $host;
        proxy_cache_bypass $http_upgrade;
        proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header   X-Forwarded-Proto $scheme;
    }
}
```