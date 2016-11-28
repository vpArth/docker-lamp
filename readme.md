
Install:
---

```sh
git clone https://github.com/vpArth/docker-lamp
cd $_

cp .env.dist .env
vim .env

docker-compose build
docker-compose up -d

# Get mysql IP
DB_IP=$(docker network inspect lamp_default | grep IPv4Address | cut -d\" -f4 | cut -d/ -f1)
# check
echo 'SELECT 5+POW(2, 5)+5 Answer' | mysql -h$DB_IP -uuser -p
Enter password:
Answer
42

# Stop
docker-compose stop

```
