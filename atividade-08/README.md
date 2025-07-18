

# Tarefa 08

- Criar um deployment  e um serviço (Ip cluster) para a app nginx
- Criar um deployment e um seviçco (NodePort) para a app nginx2
- Demonstrar as formas de acesso "por fora do cluster" via curl e browser


## Resolução

- Subir cluster a partir de uma configuração para expor portas no kind
https://kind.sigs.k8s.io/docs/user/configuration/#extra-port-mappings

```sh
kind create cluster --config cluster-config.yaml
```
## Step 1

- deploy cluster IP `kubectl apply -f nginx-cluster-ip.yaml`

![alt text](assets/img1.png)

## Step 2

- deploy Node port `kubectl apply -f nginx-node-port.yaml`

![alt text](assets/img2.png)

## Step 3

- Acessar os sites

#### Cluster IP https://localhost:8080
![alt text](assets/img5.png)
![alt text](assets/img4.png)

#### Node Port https://localhost:30950
![alt text](assets/img3.png)