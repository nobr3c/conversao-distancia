# conversao-distancia

### Comandos:

Criar imagem:
´docker build -t conversao-distancia -f Dockerfile .´

Listar imagem:
´docker image ls´

Configurar porta que irá acessar o projeto via browser:
´docker container run -d -p 8181:5000 conversao-distancia´

listar as imagens no docker:
´docker imagee ls´

Colocar versão na imagem:
´docker build -t nobr3c/conversao-distancia:v1 .´

listar as imagens no docker:
´docker image ls´

Limpar imagens não utilizadas como lixo cache
´docker image prune´

listar as imagens no docker:
´docker image ls´

Realizar push do projeto:
´docker login´

Inserir login e senha da conta dockerhub

Realizar o push da imagem docker no dockerhub
´docker push nobr3c/conversao-distancia:v1´

Subir a imagem latest

´docker tag nobr3c/conversao-distancia:v1 nobr3c/conversao-distancia:latest´

Verificar a imagem latest no docker:
´docker image ls´

Realizar o push da imagem docker no dockerhub
´docker push nobr3c/conversao-distancia:latest´

Link para o repositorio github: https://hub.docker.com/r/nobr3c/conversao-distancia/tags

O projeto roda na porta 5000