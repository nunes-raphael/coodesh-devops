**Projeto Wordpress - challenge by coodesh**

Este projeto tem como objetivo disponibilizar um site wordpress na AWS de forma automatizada utilizando as seguintes tecnologias:

* Terraform
  * Provisiona a VPC;
  * Cria uma máquina EC2 na AWS.
* Ansible
  * Faz a atualização dos pacotes;
  * Instala o Docker, Docker-Compose;
  * Copia o arquivo de configutação do nginx;
  * Copia o docker-compose.yml  
  * Executa o docker-compose para a criação dos containers Nginx (proxy), wordpress e mysql;   
* ShellScript
  * Através do shell script é criada uma pipeline para construção do albiente 100% automatizada. 
    
INSTRUÇOES DE USO:

Pré-requisito:
Na máquina que será executada o script 'run.sh' é necessário instalar o terraform e o ansible:

Terraform - Procedimento de Instalação
* https://learn.hashicorp.com/tutorials/terraform/install-cli

Ansible - Procedimento de Instalação
* https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

CONFIGURANDO O AMBIENTE:

* Clonar o repositório: 
  - [https://github.com/nunes-raphael/oodesh-devop.git](https://github.com/nunes-raphael/oodesh-devops.git);
* Configurando a chave de acesso AWS
  - chmod 400 ./aws_ec2/wordpress-ec2.pem
  - ssh-add ./aws_ec2/wordpress-ec2.pem
* Criando a infraestrutura na AWS
  - ./run.sh
* Excluindo a infraestrutura na AWS
  - ./run.sh --destroy
