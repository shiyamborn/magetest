# magetest
Magento test environment


Setup Local
============================

Install Nginx 1.18

sudo apt update
sudo apt install nginx
systemctl status nginx
sudo systemctl enable nginx

Install PHP 8.1

sudo apt update
sudo apt install --no-install-recommends php8.1
sudo apt-get install -y php8.1-cli php8.1-common php8.1-mysql php8.1-zip php8.1-gd php8.1-mbstring php8.1-curl php8.1-xml php8.1-bcmath

Install MySql 8

wget -c https://dev.mysql.com/get/mysql-apt-config_0.8.11-1_all.deb
sudo dpkg -i mysql-apt-config_0.8.11-1_all.deb
sudo apt-get update
sudo apt-get install mysql-server
sudo mysql_secure_installation

Install Composer

sudo apt update
sudo apt install composer

Install Varnish 7

sudo apt update
sudo apt install varnish
sudo systemct1 status varnish

Install Elasticsearch

curl -fsSL https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
sudo apt update
sudo apt install elasticsearch
sudo nano /etc/elasticsearch/elasticsearch.yml
    network.host: localhost
sudo systemctl start elasticsearch
sudo systemctl enable elasticsearch
sudo ufw allow from 198.51.100.0 to any port 9200
sudo ufw enable
sudo ufw status
curl -X GET 'http://localhost:9200'

Install Redis

sudo apt-get update
sudo apt install redis
redis-cli --version
sudo systemctl status redis

