# Criação e configuração de LoadBalancer    -   Nginx + Docker + app React 

### Itens necessários
* Build da aplicação React
* Nginx
* Docker

## 1° passo
copie todos os arquivos do build, /build ou /dist, e cole no '/var/www/html/'

```
sudo cp -R ~/keyControlFront/build/* /var/www/html/
``` 
_keyControlFront_ é o nome do app React

## 2° passo
criar os nós, referenciando aos arquivos builds
```
docker run -d --name node1 -v /var/www/html:/usr/share/nginx/html nginx:1.29.3-alpine
docker run -d --name node2 -v /var/www/html:/usr/share/nginx/html nginx:1.29.3-alpine
docker run -d --name node3 -v /var/www/html:/usr/share/nginx/html nginx:1.29.3-alpine
docker run -d --name node4 -v /var/www/html:/usr/share/nginx/html nginx:1.29.3-alpine
docker run -d --name node5 -v /var/www/html:/usr/share/nginx/html nginx:1.29.3-alpine
```
## 3° passo
criar a pasta de configuração dos nós
```
mkdir -p /home/user/node-config
```
criar a configuração
```
nano /home/user/node-config/default.conf
```
