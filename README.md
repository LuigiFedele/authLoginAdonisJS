# Sistema de Login e Cadastro - API

Este repositório contém uma API de login e cadastro de usuários construída com AdonisJS e TypeScript. A aplicação permite que os usuários se cadastrem, façam login e acessem rotas protegidas com autenticação JWT. A solução é simples e escalável, ideal para sistemas que necessitam de autenticação de usuários.

## Tecnologias Utilizadas

- **AdonisJS**: Framework Node.js baseado em TypeScript, ideal para construir APIs escaláveis e de alta performance.
- **SQLite**: Banco de dados SQL leve e fácil de configurar, utilizado para armazenar dados de usuários.
- **JWT (JSON Web Tokens)**: Utilizado para autenticação e autorização de usuários nas rotas protegidas.

## Funcionalidades

- **Cadastro de Usuários**: Permite o registro de novos usuários.
- **Login de Usuários**: Realiza a autenticação do usuário e gera um token JWT para acesso a rotas protegidas.
- **Proteção de Rotas**: Algumas rotas requerem autenticação via JWT para acesso, garantindo a segurança dos dados.
- **Validação de Dados**: Validação dos dados de entrada no cadastro e login para garantir que os dados sejam corretos e seguros.

## Requisitos

Certifique-se de ter as seguintes ferramentas instaladas:

- **Node.js** (versão LTS recomendada)

## Como Rodar a Aplicação

### 1. Clone o Repositório

Clone o repositório para o seu ambiente local:

```bash
git clone https://github.com/seu-usuario/nome-do-repositorio.git
cd nome-do-repositorio
```

### 2. Instale as Dependências

Instale as dependências usando o npm::

```bash
npm install
```

### 3. Rode as Migrações

Clone o repositório para o seu ambiente local:

```bash
node ace migration:run
```

### 4. Inicie o Servidor

Agora, inicie o servidor de desenvolvimento:

```bash
npm run dev
```

### 5. Teste as Rotas

Você pode testar as rotas utilizando ferramentas como [Postman](https://www.postman.com/) ou [Insomnia](https://insomnia.rest/). As rotas estão descritas abaixo.

## Rotas

### **Cadastro de Usuário**

- **POST** `/register`: Realiza o cadastro de um novo usuário.
  - **Body**:
    ```json
    {
      "email": "usuario@example.com",
      "password": "senha_segura",
      "name": "Nome do Usuário"
    }
    ```
  - **Resposta**:
    - **Sucesso**:
      ```json
      {
        "message": "Usuário criado com sucesso!"
      }
      ```
    - **Erro**: Erro de validação ou duplicação de email.

### **Login de Usuário**

- **POST** `/login`: Realiza o login de um usuário e gera um token JWT.
  - **Body**:
    ```json
    {
      "email": "usuario@example.com",
      "password": "senha_segura"
    }
    ```
  - **Resposta**:
    - **Sucesso**:
      ```json
      {
        "token": "jwt_token_aqui"
      }
      ```
    - **Erro**: Credenciais inválidas.

### **Rota Protegida**

- **GET** `/profile`: Rota protegida que retorna os dados do usuário autenticado.
  - **Cabeçalho**:
    - **Authorization**: Bearer `jwt_token_aqui`
  - **Resposta**:
    ```json
    {
      "id": 1,
      "name": "Nome do Usuário",
      "email": "usuario@example.com"
    }
    ```
----

