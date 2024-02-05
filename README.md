# Atividade Linux - AWS 🐧☁️

## Descrição 

A tarefa envolverá a criação de uma chave pública para acesso, o provisionamento de uma instância EC2 utilizando o sistema operacional Amazon Linux 2, a alocação de um endereço IP elástico que será associado à instância EC2, a abertura de portas de comunicação para permitir acesso público, a configuração do sistema de arquivos NFS, a criação de um diretório correspondente ao nome do usuário no filesystem do NFS, a instalação e configuração do servidor Apache, a elaboração de um script para verificar a disponibilidade do serviço e enviar os resultados para o diretório NFS, e a configuração da execução automatizada do script a cada intervalo de 5 minutos.

_ _ _

## Detalhes da Configuração.

### Instancia AWS:
- Chave pública para acesso ao ambiente
- Amazon Linux 2
    - t3.small
    - 16 GB SSD
- 1 Elastic IP associado a instancia
- Portas de comunicação liberadas
    - 22/TCP (SSH)
    - 111/TCP e UDP (RPC)
    - 2049/TCP/UDP (NFS)
    - 80/TCP (HTTP)
    - 443/TCP (HTTPS)

### Configurações Linux:

- Configurar o NFS entregue;
- Criar um diretorio dentro do filesystem do NFS com seu nome;
- Subir um apache no servidor - o apache deve estar online e rodando;
- Criar um script que valide se o serviço esta online e envie o resultado da validação para o seu diretorio no nfs;
    - O script deve conter - Data HORA + nome do serviço + Status + mensagem personalizada de ONLINE ou offline;
    - O script deve gerar 2 arquivos de saida: 1 para o serviço online e 1 para o serviço OFFLINE;
    - Execução automatizada do script a cada 5 minutos.

---

## Guia Detalhado para Configuração.

### Geração de chave pública de acesso e anexá-la à uma nova instância EC2 na AWS.
- Acessar a AWS na pagina do serviço EC2, e clicar em "Pares de chaves" no menu lateral esquerdo.
- Clicar em "Criar par de chaves".
- Inserir um nome para a chave e clicar em "Criar par de chaves".
- Salvar o arquivo .pem gerado em um local seguro.
- Clicar em "Instâncias" no menu lateral esquerdo.
- Clicar em "Executar instâncias".
- Configurar as Tags da instância (Name, Project e CostCenter) para instâncias e volumes.
- Selecionar a imagem Amazon Linux 2 AMI (HVM), SSD Volume Type.
- Selecionar o tipo de instância t3.small.
- Selecionar a chave gerada anteriormente.
- Colocar 16 GB de armazenamento gp2 (SSD).
- Clicar em "Executar instância".

