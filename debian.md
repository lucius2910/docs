`mkdir name_dir`  
`rmdir name_dir`

## update app
`sudo apt-get update`

## install nginx
`sudo apt install nginx`

## install firewall
`sudo apt-get install ufw`

## check nginx
`sudo ufw app list`

## enable 
`sudo ufw allow 'nginx HTTP'`
`sudo ufw delete allow ssh`

## check all port
`sudo ufw status verbose`

## test nginx
`sudo nginx -t`

## restart nginx
`sudo systemctl restart nginx`

## install tmux
`sudo apt-get install tmux`

## Create new session
`tmux new -s s_name`

## Attack sesstion name
`tmux a -t s_name`

## list session
`tmux ls`

## Kill session
`tmux kill-session -t s_name`