# Afya Strapi App

Uma aplicação Strapi que serve como um CMS headless, permitindo a criação e gerenciamento de conteúdo de forma flexível e escalável.

## Índice

- [Descrição](#descrição)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Instalação](#instalação)
- [Uso](#uso)
- [Configuração](#configuração)
- [Geração de Chaves](#geração-de-chaves)
- [Contribuição](#contribuição)
- [Licença](#licença)

## Descrição

Este projeto é uma aplicação Strapi que utiliza PostgreSQL como banco de dados. O Strapi é um CMS headless que permite a criação de APIs de forma rápida e fácil, com um painel de administração baseado em React.

## Tecnologias Utilizadas

- **Node.js** (JavaScript/TypeScript)
- **Strapi** (v5)
- **PostgreSQL** (banco de dados)
- **Yarn** (gerenciador de pacotes)
- **Docker** (para containerização)

## Instalação

Para instalar e configurar o projeto, siga os passos abaixo:

1. Clone o repositório:
   ```bash
   git clone https://github.com/usuario/afya-strapi-app.git

2. Navegue até o diretório do projeto:
    - cd afya-strapi-app

3. Crie um arquivo .env baseado no arquivo .env.example e modifique as variáveis conforme necessário.    

4. Execute o Docker Compose para iniciar os serviços:
    - docker-compose down (Caso já tenha rodado a aplicação em seu local)
    - docker-compose up --build

## Uso

Após a instalação, você pode acessar a aplicação Strapi em http://localhost:1337. O painel de administração pode ser acessado em http://localhost:1337/admin.

Para iniciar a aplicação em modo de desenvolvimento, você pode usar o seguinte comando:
    yarn develop

## Configuração

Variáveis de Ambiente
As variáveis de ambiente necessárias estão listadas no arquivo .env.example. 
Certifique-se de configurar as seguintes variáveis:

- HOST: O endereço do host (default: 0.0.0.0)
- PORT: A porta em que o Strapi será executado (default: 1337)
- APP_KEYS, API_TOKEN_SALT, ADMIN_JWT_SECRET, TRANSFER_TOKEN_SALT, JWT_SECRET, ENCRYPTION_KEY: Chaves e segredos para a aplicação.

### Geração de Chaves

Para gerar as chaves necessárias para o arquivo `.env`, você pode usar o seguinte comando em um terminal Node.js:

```bash
node -e "console.log('APP_KEYS=' + Array.from({length: 4}, () => require('crypto').randomBytes(32).toString('base64')).join(','));"
node -e "console.log('API_TOKEN_SALT=' + require('crypto').randomBytes(16).toString('base64'));"
node -e "console.log('ADMIN_JWT_SECRET=' + require('crypto').randomBytes(32).toString('base64'));"
node -e "console.log('TRANSFER_TOKEN_SALT=' + require('crypto').randomBytes(16).toString('base64'));"
node -e "console.log('ENCRYPTION_KEY=' + require('crypto').randomBytes(32).toString('base64'));"
```

Isso irá gerar valores aleatórios que você pode copiar e colar no seu arquivo `.env`.

### Banco de Dados

O projeto utiliza PostgreSQL como banco de dados. As credenciais do banco de dados podem ser configuradas no arquivo .env.

## Contribuição

Contribuições são bem-vindas! Para contribuir, siga os passos abaixo:

Fork o repositório.
Crie uma nova branch (git checkout -b feature/nome-da-feature).
Faça suas alterações e commit (git commit -m 'Adiciona nova feature').
Envie para o repositório remoto (git push origin feature/nome-da-feature).
Abra um Pull Request.

## Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo LICENSE para mais detalhes.    