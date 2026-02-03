# Ansible Role: AlmaLinux 9 Web Stack

Este repositório contém uma automação completa para configurar um ambiente servidor no **AlmaLinux 9** com Apache, PHP 8.5 (via Remi) e Java 17.

## Requisitos
- Ansible 2.10+
- Acesso SSH ao servidor alvo (AlmaLinux 9)

## Variáveis da Role
Você pode customizar a instalação alterando as variáveis em `roles/webserver/defaults/main.yml` ou passando-as no seu inventário:

| Variável | Padrão | Descrição |
|----------|---------|-------------|
| `php_version` | `8.5` | Versão do PHP a ser instalada via Remi |
| `php_modules` | `[php-gd, ...]` | Lista de extensões PHP para instalar |

## Como usar

1. Configurar o Inventário (inventory.ini)
O arquivo de inventário diz ao Ansible em qual servidor ele deve trabalhar. Abra o arquivo inventory.ini e adicione o IP do seu servidor:

Ini, TOML
[meu_servidor]
192.168.1.10 ansible_user=seu_usuario ansible_ssh_private_key_file=~/.ssh/id_rsa
Nota: Substitua 192.168.1.10 pelo IP real do seu servidor e seu_usuario pelo usuário com permissões de sudo (como o root).

2. Personalizar Módulos do PHP
A flexibilidade desta automação permite que você escolha exatamente quais extensões do PHP deseja instalar. Para gerenciar os módulos, acesse o arquivo: roles/webserver/defaults/main.yml

Basta adicionar ou remover itens da lista php_modules:

roles/webserver/defaults/main.yml
php_modules:
  - php-gd
  - php-mysqlnd
  - php-zip
  - php-intl
3. Rodar a Playbook
Com tudo configurado, execute o comando abaixo no terminal para iniciar o provisionamento:

Bash
ansible-playbook -i inventory.ini playbook.yml

4. Clone o repositório:

git clone [https://github.com/SamuCamilo/ansible-almalinux-stack.git](https://github.com/SamuCamilo/ansible-almalinux-stack.git)
