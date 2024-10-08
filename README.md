
# Ecommerce API

Esta é uma API de ecommerce desenvolvida com Flask. A API permite realizar operações de autenticação de usuários, gerenciar produtos e realizar operações de carrinho de compras, como adicionar itens ao carrinho, visualizar e realizar checkout.

## Requisitos

- Python 3.12
- SQLite (ou outro banco de dados compatível com SQLAlchemy)

## Instalação

1. Clone o repositório:

   ```bash
   git clone https://github.com/srmatheusmaciel/flask_api.git

2. Instale as depêndencias do projeto:
    ```bash
    pip install -r requirements.txt

3. Execute a aplicação
    ```bash
    python app.py


## Endpoints

### Autenticação

- **Login**
  - Rota: `/login`
  - Método: `POST`
  - Descrição: Autentica o usuário.
  - Dados de entrada:
    ```json
    {
      "username": "string",
      "password": "string"
    }
    ```

- **Logout**
  - Rota: `/logout`
  - Método: `POST`
  - Descrição: Faz o logout do usuário autenticado.

### Produtos

- **Listar produtos**
  - Rota: `/api/products`
  - Método: `GET`
  - Descrição: Retorna todos os produtos disponíveis.

- **Adicionar produto**
  - Rota: `/api/products/add`
  - Método: `POST`
  - Descrição: Adiciona um novo produto. (Requer autenticação)
  - Dados de entrada:
    ```json
    {
      "name": "string",
      "price": "float",
      "description": "string"
    }
    ```

- **Deletar produto**
  - Rota: `/api/products/delete/<product_id>`
  - Método: `DELETE`
  - Descrição: Deleta um produto específico pelo ID. (Requer autenticação)

- **Atualizar produto**
  - Rota: `/api/products/update/<product_id>`
  - Método: `PUT`
  - Descrição: Atualiza as informações de um produto específico pelo ID. (Requer autenticação)
  - Dados de entrada:
    ```json
    {
      "name": "string",
      "price": "float",
      "description": "string"
    }
    ```

- **Ver detalhes de um produto**
  - Rota: `/api/products/<product_id>`
  - Método: `GET`
  - Descrição: Retorna os detalhes de um produto específico.

### Carrinho

- **Adicionar item ao carrinho**
  - Rota: `/api/cart/add/<product_id>`
  - Método: `POST`
  - Descrição: Adiciona um produto ao carrinho. (Requer autenticação)

- **Remover item do carrinho**
  - Rota: `/api/cart/remove/<product_id>`
  - Método: `DELETE`
  - Descrição: Remove um produto do carrinho. (Requer autenticação)

- **Visualizar carrinho**
  - Rota: `/api/cart`
  - Método: `GET`
  - Descrição: Retorna os itens do carrinho do usuário autenticado.

- **Checkout**
  - Rota: `/api/cart/checkout`
  - Método: `POST`
  - Descrição: Realiza o checkout, limpando o carrinho. (Requer autenticação)

## Banco de Dados

- **Usuários (User)**: Armazena informações dos usuários cadastrados.
- **Produtos (Product)**: Armazena informações dos produtos.
- **Itens do Carrinho (CartItem)**: Relaciona usuários com produtos adicionados ao carrinho.

## Tecnologias Utilizadas

- **Flask**: Framework web utilizado para desenvolver a API.
- **Flask-SQLAlchemy**: ORM usado para gerenciar o banco de dados.
- **Flask-Login**: Gerenciamento de autenticação.
- **Flask-CORS**: Gerenciamento de CORS.
- **SQLite**: Banco de dados utilizado por padrão.

## Dependências

As dependências estão listadas no arquivo `requirements.txt`:

```
Flask==2.3.0
Flask-SQLAlchemy==3.1.1
Flask-Login==0.6.2
Flask-Cors==3.0.10
Werkzeug==2.3.0
```


    
