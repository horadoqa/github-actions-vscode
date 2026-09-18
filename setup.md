# SETUP

Instalar a extensão do GITHUB ACTIONS no VSCODE

Instalar o ACT

MAC

WINDOWS

LINUX (zsh)

curl -s https://raw.githubusercontent.com/nektos/act/master/install.sh | sudo bash

sudo mv ./bin/act /usr/local/bin/act

rehash

which act
/usr/local/bin/act

Saber aversão instalada

act --version
act version 0.2.89

Testando o WORKFLOW

act -l

act -l
INFO[0000] Using docker host 'unix:///var/run/docker.sock', and daemon socket 'unix:///var/run/docker.sock' 
Stage  Job ID         Job name                           Workflow name             Workflow file  Events                    
0      api-test       Executar testes CRUD da API        Teste de API - ServeRest  test.yaml      schedule,workflow_dispatch
1      registrar-log  Registrar resultado da execução    Teste de API - ServeRest  test.yaml      schedule,workflow_dispatch


 Se seu workflow é acionado por push. Ele só responde a:
 
 act

Se seu workflow é acionado por schedule ou workflow_dispatch. Ele só responde a:

Neste caso use:

act workflow_dispatch -P ubuntu-latest=catthehacker/ubuntu:act-latest

Se quiser executar somente o job de testes da API:

act workflow_dispatch -j api-test

E somente o registro:

act workflow_dispatch -j registrar-log


Se quiser ver mais detalhes
Use:

act workflow_dispatch --verbose

ou:

act workflow_dispatch -j api-test --verbose


act workflow_dispatch -P ubuntu-latest=catthehacker/ubuntu:act-latest