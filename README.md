# conversao-distancia

### Comandos:

Criar imagem:
`docker build -t conversao-distancia -f Dockerfile . `

Listar imagem:
`docker image ls`

Configurar porta que irá acessar o projeto via browser:
`docker container run -d -p 8181:5000 conversao-distancia`

listar as imagens no docker:
`docker imagee ls`

Colocar versão na imagem:
`docker build -t nobr3c/conversao-distancia:v1 . `

listar as imagens no docker:
`docker image ls`

Limpar imagens não utilizadas como lixo cache
`docker image prune`

listar as imagens no docker:
`docker image ls`

Realizar push do projeto:
´docker login´

Inserir login e senha da conta dockerhub

Realizar o push da imagem docker no dockerhub
`docker push nobr3c/conversao-distancia:v1`

Subir a imagem latest

`docker tag nobr3c/conversao-distancia:v1 nobr3c/conversao-distancia:latest`

Verificar a imagem latest no docker:
`docker image ls`

Realizar o push da imagem docker no dockerhub
`docker push nobr3c/conversao-distancia:latest`

Link para o repositorio github: https://hub.docker.com/r/nobr3c/conversao-distancia/tags

O projeto roda na porta 5000

----------------------------------------------------------------------------
instalar o kubernets (https://kubernetes.io/pt-br/docs/tasks/tools/install-kubectl-windows/#install-nonstandard-package-tools)
instalar o k3d (https://k3d.io/stable/#other-installers)
Aula 2
criar um cluster k3d
k3d cluster create

listar os nós
kubectl get nodes

mostrar quantos clusters estão rodando 
 k3d cluster list

verificar quantos container irá criar 
 docker container ls

deletar cluster 
k3d cluster delete

definir nome e quantidade servers, ambiente mais complexo
k3d cluster create meucluster --servers 3 --agents 3
kubectl get nodes
k3d cluster list
docker container ls
k3d cluster delete meucluster

criar um cluster com o comando 
k3d cluster create meucluster --servers 1 --agents 2

elementos que fazem parte de um deploy eficiente em kubernets
kubectl get nodes

kubectl api-resources


kubectl apply -f k8s/deployment.yaml

listar os pods
kubectl get pods

descrever o pod 
kubectl describe pod 

Descrever replicaset
kubectl get replicaset

<!--kubectl apply -f k8s/deployment.yaml && watch 'kubectl get pods'--> kubectl apply -f k8s/deployment.yaml; watch kubectl get pods

kubectl get pod -o wide
kubectl delete pod nomedopod
kubectl get deployment

rodar aplicaçao web
kubectl port-forward pod/conversao-distancia-868f4cb9b9-6cc5k 8080:5000

para acessar http://localhost:8080

kubectl apply -f k8s/deployment.yaml

kubectl get all

kubectl port-forward service/conversao-distancia 8080:80 
Acessara em http://localhost:8080/

Deletar o cluste e recriar 
k3d cluster delete meucluster
Criar o cluster com outro comando 
k3d cluster create meucluster --servers 1 --agents 2 -p "8080:30000@loadbalancer"
docker container ls
kubectl apply -f k8s/deployment.yaml
kubectl get all
http://localhost:8080/

