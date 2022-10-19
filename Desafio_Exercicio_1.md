# Exercício 1

<br/>

### 1) Execute um container baseado nas informações abaixo:
1.a) Baixe a imagem quay.io/redhattraining/httpd-parent; <br>
<img width="473" alt="image" src="https://user-images.githubusercontent.com/102270053/196194046-92d84722-880b-4dc0-89a0-c0ae0211fd29.png">
<br/><br/>
1.b) Use a tag 2.4 da imagem; <br>
<img width="475" alt="image" src="https://user-images.githubusercontent.com/102270053/196196338-5750fbac-325c-476d-b9fa-988485ba3fda.png">
<br/><br/>
1.c) O nome do container deve chamar httpd-basic; <br>
1.d) O container deve ser executado em background; <br>
1.e) O serviço deve ser disponivel na porta 8080 e redirecionar para a porta 80 do container. <br>
<img width="775" alt="image" src="https://user-images.githubusercontent.com/102270053/196198201-97fb3acf-3e00-4a26-a070-4ca274855a0e.png"> 
<img width="273" alt="image" src="https://user-images.githubusercontent.com/102270053/196198440-6dc65eb1-5e7b-4f64-851a-31d494e6837b.png">

<br/>

### 2) Customize a mensagem apresentada em seu navegador quando é acessado o endereço http://localhost:8080.
2.a) Acesse o seu container que esta sendo executado; <br>
2.b) Dentro do container acessar o endereço /var/www/html e verifique se dentro desta pasta existe um arquivo index.html; <br>
<img width="952" alt="image" src="https://user-images.githubusercontent.com/102270053/196208923-5aec9ace-ea17-4506-b0ec-248de2812b06.png">
<br/><br/>
2.c) Ainda dentro do container, subistitua a mensagem atual por uma nova "Ola mundo!" que esta no arquivo index.html. <br>
<img width="681" alt="image" src="https://user-images.githubusercontent.com/102270053/196208562-c520167e-6a5b-416c-a768-c7f11bbe7163.png">
<br/><br/>
2.d) Saia do container e verifique se a nova mensagem foi inserida. <br>
<img width="272" alt="image" src="https://user-images.githubusercontent.com/102270053/196209997-e3a9b7c6-c530-4752-a488-c001c7c0534a.png">

</br>

### 3 Pare o container que esta sendo executado.
<img width="929" alt="image" src="https://user-images.githubusercontent.com/102270053/196212926-9f305fef-af5d-4de1-96d0-89fe25a3e74f.png">
