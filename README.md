# Projeto 3: Configuração de Máquina Virtual com Vagrant e NGINX

Este projeto configura uma máquina virtual com Vagrant utilizando VirtualBox como provedor. A máquina é configurada para hospedar um servidor NGINX e sincronizar pastas locais para a VM, permitindo fácil desenvolvimento e hospedagem local.

## Configurações Principais

- **Nome da VM:** `projeto3_maquina_server_nginx`
- **Memória:** 1024 MB
- **CPUs:** 2
- **Box Utilizada:** `hashicorp/bionic64` (Ubuntu 18.04)
- **Porta Localhost:** A porta 80 da máquina virtual é encaminhada para a porta 8090 no host.
- **Sincronização de Pastas:**
  - A pasta `site/` no host é sincronizada com `/var/www/html` na máquina virtual.
  - A pasta `./data` no host é sincronizada com `/vagrant_data` na máquina virtual.
- **Provisionamento:** Um script externo `nginx-install.sh` é utilizado para instalar e configurar o NGINX.

## Requisitos

Certifique-se de ter as ferramentas abaixo instaladas em sua máquina:

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)

## Como Utilizar

1. Clone o repositório ou copie os arquivos para um diretório local.
2. Certifique-se de que os seguintes arquivos estão no mesmo diretório:
   - `Vagrantfile`
   - O script de provisionamento em `./scripts/nginx-install.sh`
   - As pastas `site/` e `data/` contendo os arquivos a serem sincronizados.
3. Abra um terminal no diretório do projeto.
4. Execute o comando abaixo para iniciar a máquina virtual:
   ```bash
   vagrant up

5. Estrutura de pastas
    ```bash
    /
    ├── Vagrantfile
    ├── scripts/
    │   └── nginx-install.sh
    ├── site/        # Arquivos do site sincronizados com /var/www/html
    └── data/        # Dados adicionais sincronizados com /vagrant_data
    ```
