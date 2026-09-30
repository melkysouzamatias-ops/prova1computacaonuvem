# prova1computacaonuvem

NOME: Melky Souza Matias dos Santos
RA:f4547efb59dab1772c5e

## O que fiz

Executei uma página web em um conteiner Docker chamado atendimento. Usei a imagem nginx:alpine e a porta 8082 do ambiente.

## verificação do conteiner

docker run -d --name atendimento -p 8082:80 nginx:alpine
Unable to find image 'nginx:alpine' locally
alpine: Pulling from library/nginx
e2de96513ba9: Pull complete 
d9aae54b5831: Pull complete 
6c53d0b2a666: Pull complete 
745dfb2690dd: Pull complete 
9a9a644fdd6a: Pull complete 
64c8194480fe: Pull complete 
e76228b47809: Pull complete 
e72112c14215: Pull complete 
Digest: sha256:df221db836e1754089190208cee7eeda94f233197056426eda74a43ab1abeac2
Status: Downloaded newer image for nginx:alpine
cf1646bbe13219701e1b5c5254a04f57f9918a182e42c7e231f568afef63fd90
root@ubuntu:~$ docker cp index.html atendimento:/usr/share/nginx/html/index.html
Successfully copied 2.05kB to atendimento:/usr/share/nginx/html/index.html

## Teste da pagina

curl http://localhost:8082
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Atendimento</title>
</head>
<body>
<h1>Atendimento disponivel</h1>
</body>
</html>

## Explicação

A diferença entre a imagem nginx:alpine e o conteiner de atendimento se deve ao fato de o endereço IP de pertencerem à bibliotecas diferentes, o mapeamento 8082:80 possibilitou a comunicação entre ambas.
