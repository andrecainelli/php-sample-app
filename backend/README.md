***7.Dentro da pasta backend adicione a imagem do mysql para criar um container na versão 0.0.1***

-   docker build . -t db:0.0.1

Obs.: A imagem db:0.0.1 foi criada e o docker executou os comandos dentro da dockerfile localizada dentro da pasta backend.

***8.Para iniciar o banco:***

-   docker run -d -e MYSQL_DATABASE='demo' -e MYSQL_ALLOW_EMPTY_PASSWORD='yes' --name backend db:0.0.1

No comando acima você está criando um container chamado backend utilizando a imagem db:0.0.1

***9.Testar a conexão com o banco:***

-   docker exec -ti backend mysql -u root -p

***10.Dentro da pasta frontend executar o comando:***

-   docker build . -t frontend:0.0.1

***11.Para rodar a imagem criado basta rodar o seguinte comando**

-   docker run -d --rm --name frontend -p 80:80 --link backend frontend:0.0.1

Obs: Cria a imagem chamada frontend disponibilizando para porta 80 interna e externa.

***12.Digite em seu navegador a url: http://localhost/ para entrar na aplicação.***
