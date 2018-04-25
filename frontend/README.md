# Sistemas para Internet - SecDevOps

***nac:***
Criação de uma aplicação no formato "CRUD" executada em containers
com base na linguagem "PHP" e no banco de dados "MySQL";

---

***Importante:***

-   RM:78710
-   Nome:Andre Cainelli Tolentino.


***1.INSTALAR DOCKER EM SUA MÁQUINA:***

-   https://docs.docker.com/docker-for-windows/install/

***2.EXECUTAR E DAR UM FORK NO REPOSITÓRIO ABAIXO:***

https://github.com/fiapsecdevops/php-sample-app/

***3.NO DIRETÓRIO EXECUTE O SEGUINTE COMANDON:***

-   git clone “O seu repositorio do projeto”

-   Obs: o repositorio é aquele que você deu fork, o meu no caso é:

-   https://github.com/andrecainelli/php-sample-app/

***4.VERIFIQUE SE A PASTA ABAIXO FOI CRIADA:***

-   php-sample-app/

-   Na pasta backend adicionar um arquivo chamado Dockerfile

***5.ADICIONE AS SEGUINTES LINHAS DENTRO DESSE ARQUIVO:***

FROM mysql:5.7

COPY ./demo.sql /docker-entrypoint-initdb.d

Obs: Adicionando uma imagem do mysql na versão 5.7 no seu docker.

***6.VOLTE PARA O DIRETÓRIO PHP-SAMPLE-APP E ENTRE NA PASTA FRONTEND:***

-   Na pasta frontend adicionar um arquivo chamado Dockerfile

-   FROM php:7.2-apache

# Enable mysqli to connect to databse
RUN docker-php-ext-install mysqli

WORKDIR /var/www/html/

COPY . /var/www/html/
