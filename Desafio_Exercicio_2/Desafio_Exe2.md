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

* Inicie o daemon Apache httpd em primeiro plano usando a instrução CMD e o seguinte comando:

```
httpd -D FOREGROUND
```
