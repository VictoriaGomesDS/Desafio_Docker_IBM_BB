# Exercicios

### 1 Crie uma imagem utilizando o _Dockerfile_ baseado nos parâmetros abaixo:
* A imagem de base é redhat/ubi8:8.5;
* Define o nome do autor desejado e o ID de e-mail com a instrução MAINTAINER;
* Define a variável de ambiente PORT para 8080;
* Instale o Apache (pacote httpd);
* Altere o arquivo de configuração do Apache /etc/httpd/conf/httpd.conf para ouvir a porta 8080 em vez da porta 80 padrão;
* Altere a propriedade das pastas /etc/httpd/logs e /run/httpd para o usuário e grupo apache (UID e GID são 48);
```
sed -ri -e "/^Listen 80/c\Listen ${PORT}" /etc/httpd/conf/httpd.conf && \
    chown -R apache:apache /etc/httpd/logs/ && \
    chown -R apache:apache /run/httpd/
```
<br/>
<img width="441" alt="image" src="https://user-images.githubusercontent.com/102270053/196781858-e9f19d47-d5b4-48f9-8962-f8cab99c24df.png"> <br/>
<br/>


* Exponha o valor definido na variável de ambiente PORT para que os usuários do contêiner saibam como acessar o Apache Web Server;
* Crie uma pasta chamada src, e depois crie uma arquivo index.html. O conteúdo da pasta src/ deve ser copiado para o arquivo Apache DocumentRoot (/var/www/html/) dentro do container;
  
_index.html_
```
<html>
 <header><title>Olá mundo</title></header>
 <body>
   Este é meu apache! 
 </body>
</html>
```

* A pasta src deve conter apenas o arquivo index.html criado no passo anterior que imprime uma mensagem "Este é meu apache!";
<br/>
<img width="422" alt="image" src="https://user-images.githubusercontent.com/102270053/196781062-cf3accea-a094-48f2-845c-d877865030ef.png"> <br/>
<br/>

* Inicie o daemon Apache httpd em primeiro plano usando a instrução CMD e o seguinte comando:

```
httpd -D FOREGROUND
```
<br/>
<img width="444" alt="image" src="https://user-images.githubusercontent.com/102270053/196781415-3e1df7a7-4a00-4d71-9295-0a378223f00b.png"> <br/>
<br/>

IMAGEM FINAL
<br/>
<img width="444" alt="image" src="https://user-images.githubusercontent.com/102270053/196781999-5c6fc8c6-feef-4845-a9c6-54786d6b834d.png"> <br/>
<br/>

<br/>

### 2 Com o seu Dockerfile pronto, execute o comando docker build e o nome da imagem deve ser _seunome/custom-apache_ e verifiquei se esta imagem esta disponivel localmente.
<br/>
<img width="600" alt="image" src="https://user-images.githubusercontent.com/102270053/196782578-d127de9d-73ba-4290-a26f-bce17579f6d5.png">
<img width="525" alt="image" src="https://user-images.githubusercontent.com/102270053/196783152-2ab5b5cd-8dd1-4f8e-8ea6-08613f46950e.png"> <br/>
<br/>
<br/>

### 3 Com a imagem disponível localmente, crie um novo container com as características abaixo:

* Nome do container deve ser _meuapache_;
* Faça um redirecionamento de portas, da porta do host 20080 para a porta do contêiner 8080;
* Execute o container em modo daemon.
<img width="700" alt="image" src="https://user-images.githubusercontent.com/102270053/196784299-a25004cd-c968-4863-a4e2-363fa28689f8.png">
<img width="700" alt="image" src="https://user-images.githubusercontent.com/102270053/196784450-32276a57-453c-45ec-b336-c3538e9bd69b.png"> <br/>
<br/>
<br/>

### 4 Verifique se o seu container esta sendo executado utilizando o comando docker e também através do seu navegador acessando o endereço https://localhost:20080.

<img width="255" alt="image" src="https://user-images.githubusercontent.com/102270053/196784500-a75db000-d7e5-417e-93eb-11735f389f62.png"> <br/>
<br/>
<br/>

### 5 Apos verificar se o container esta sendo executado corretamente e você conseguiu verificar a mensagem utilizando o seu navegador, para ele e então suba a sua imagem criada para o docker hub.
