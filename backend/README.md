Obs: Os comandos acima significam que ele está baixando uma imagem com o apache configurado para rodar php com mysql.

***7.Rode o seguinte comando dentro da pasta backend para de fato adicionar a imagem do mysql e criar um container chamado db na versão 0.0.1.***
docker build . -t db:0.0.1

Obs.: Agora você criou uma imagem chamada db:0.0.1. e o docker executou os comandos dentro da dockerfile localizada dentro da pasta backend.

***8.Rode o seguinte comando para iniciar o banco:***

docker run -d -e MYSQL_DATABASE='demo' -e MYSQL_ALLOW_EMPTY_PASSWORD='yes' --name backend db:0.0.1

No comando acima você está criando um container chamado backend utilizando a imagem db:0.0.1

Para testar a conexão com o banco:
docker exec -ti backend mysql -u root -p

***9.A seguir entre na pasta frontend e execute o seguinte comando:***

docker build . -t frontend:0.0.1

Obs: no codigo acima o docker leu a dockerfile localizada na pasta frontend e criou a seguinte imagem frontend:0.0.1

***10.Para rodar a imagem criado basta rodar o seguinte comando docker run -d --rm --name frontend -p 80:80 --link backend frontend:0.1.***

Obs:Ao rodar o comando acima uma imagem chamada frontend será criada e já estará a disposição na porta 80 interna e externa.

***11.Agora é só digitar no seu navegador a url: http://localhost/ e você entrará na aplicação.***
