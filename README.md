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

1. Clone o repositório:
   ```bash
   git clone [https://github.com/seu-usuario/ansible-almalinux-stack.git](https://github.com/seu-usuario/ansible-almalinux-stack.git)
