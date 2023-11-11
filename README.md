# ERPNext-V14-Install-Code

Update and Upgrade Packages

sudo apt-get update -y && sudo apt-get upgrade -y

Create a new user – (bench user)

sudo adduser frappe
sudo usermod -aG sudo frappe
su - frappe 

sudo apt-get install git

sudo apt-get install python3-dev python3.10-dev python3-setuptools python3-pip python3-distutils

sudo apt-get install python3.10-venv

sudo apt-get install software-properties-common

sudo apt install mariadb-server mariadb-client

sudo apt-get install redis-server

sudo apt-get install xvfb libfontconfig wkhtmltopdf

sudo apt-get install libmysqlclient-dev

sudo mysql_secure_installation

sudo nano /etc/mysql/my.cnf
[mysqld]
character-set-client-handshake = FALSE
character-set-server = utf8mb4
collation-server = utf8mb4_unicode_ci

[mysql]
default-character-set = utf8mb4

sudo service mysql restart

sudo apt install curl

curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash

source ~/.profile

nvm install 16.15.0

sudo apt-get install npm

sudo npm install -g yarn

export LC_ALL=C.UTF-8

sudo -H pip3 install frappe-bench
bench init frappe-bench --verbose --frappe-branch version-14

cd frappe-bench

chmod -R o+rx /home/frappe

bench new-site site1.local

bench use site1.local

bench get-app --branch version-14 erpnext
bench get-app payments
bench get-app hrms

bench --site site1.local install-app erpnext
bench --site site1.local install-app payments
bench --site site1.local install-app hrms

bench start


bench set-config developer_mode 1
bench enable-scheduler
bench set-maintenance-mode off

export LC_ALL=C.UTF-8
sudo bench setup production frappe

bench setup nginx
sudo supervisorctl restart all
sudo bench setup production frappe


sudo systemctl restart nginx


**************

sudo systemctl reload nginx

sudo systemctl stop nginx

sudo systemctl start nginx

sudo systemctl reload nginx

sudo systemctl restart nginx


***********Multitenant*********

bench config dns_multitenant on

bench new-site first.site

bench setup nginx

sudo service nginx reload


***************

Set port
   bench set-nginx-port education 81
Re generate nginx config
   bench setup nginx
Reload nginx
  sudo service nginx reload
Reload supervisor
  sudo service supervisor restart

sudo bench setup production erpnext




