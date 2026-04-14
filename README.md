    # API de Cadastro - Sistema de Gerenciamento

Uma API RESTful completa para gerenciamento de clientes, produtos e usuários, desenvolvida com Node.js e Express.

## 🚀 Tecnologias Utilizadas

- **Node.js** - Runtime JavaScript
- **Express.js** - Framework web
- **CORS** - Habilita requisições cross-origin
- **File System** - Armazenamento de dados em arquivos JSON

## 📋 Requisitos

- Node.js instalado
- NPM ou Yarn

## 🔧 Instalação

```bash
# Clone o repositório
git clone <url-do-repositorio>

# Entre na pasta do projeto
cd api-cadastro

# Instale as dependências
npm install

# Inicie o servidor
node index.js
```

O servidor será iniciado em `http://localhost:3000`

## � Estrutura do Projeto

```
api-cadastro/
├── index.js           # Arquivo principal da API
├── clientes.json      # Base de dados de clientes
├── produtos.json      # Base de dados de produtos
├── usuarios.json      # Base de dados de usuários
├── package.json       # Dependências do projeto
└── README.md         # Documentação
```

## 🔌 Endpoints da API

### 📋 Clientes

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| POST | `/clientes` | Cadastrar novo cliente |
| GET | `/clientes` | Listar todos os clientes |
| GET | `/clientes/:cpf` | Buscar cliente por CPF |
| DELETE | `/clientes/:cpf` | Deletar cliente por CPF |

**Formato do Cliente:**
```json
{
  "cpf": "12345678909",
  "nome": "João Silva",
  "idade": 30,
  "endereco": "Rua das Flores, 123",
  "bairro": "Centro",
  "contato": "11999999999"
}
```

### 📦 Produtos

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| POST | `/produtos` | Cadastrar novo produto |
| GET | `/produtos` | Listar todos os produtos |
| GET | `/produtos/:id` | Buscar produto por ID |
| DELETE | `/produtos/:id` | Deletar produto por ID |

**Formato do Produto:**
```json
{
  "id": 1,
  "nome": "Produto Exemplo",
  "descricao": "Descrição detalhada do produto",
  "valor": 99.99
}
```

### 👥 Usuários

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| POST | `/usuarios` | Cadastrar novo usuário |
| GET | `/usuarios` | Listar todos os usuários |
| GET | `/usuarios/:email` | Buscar usuário por email |
| DELETE | `/usuarios/:codigo` | Deletar usuário por código |
| POST | `/login` | Autenticar usuário |

**Formato do Usuário:**
```json
{
  "codigo": "123456",
  "nome": "Maria Silva",
  "email": "maria@email.com",
  "senha": "senha123"
}
```

## 📊 Exemplos de Uso

### Cadastrar Cliente
```bash
curl -X POST http://localhost:3000/clientes \
  -H "Content-Type: application/json" \
  -d '{
    "cpf": "12345678909",
    "nome": "João Silva",
    "idade": 30,
    "endereco": "Rua das Flores, 123",
    "bairro": "Centro",
    "contato": "11999999999"
  }'
```

### Listar Produtos
```bash
curl http://localhost:3000/produtos
```

### Deletar Usuário
```bash
curl -X DELETE http://localhost:3000/usuarios/123456
```

### Login
```bash
curl -X POST http://localhost:3000/login \
  -H "Content-Type: application/json" \
  -d '{
    "email": "maria@email.com",
    "senha": "senha123"
  }'
```

## ⚙️ Configuração

- **Porta:** 3000
- **CORS:** Habilitado para todas as origens
- **Dados:** Armazenados localmente em arquivos JSON

## 🔒 Validações

### Clientes
- Todos os campos são obrigatórios
- CPF não pode ser duplicado
- CPF aceita formato numérico ou string

### Produtos
- Todos os campos são obrigatórios
- ID não pode ser duplicado
- ID aceita formato numérico ou string

### Usuários
- Todos os campos são obrigatórios
- Email e código não podem ser duplicados
- Código aceita formato numérico ou string

## 📝 Notas Importantes

- Os dados são persistidos em arquivos JSON locais
- Não há sistema de autenticação complexo (apenas login básico)
- A API foi desenvolvida para fins educacionais e demonstração
- IDs e CPFs aceitam tanto formato numérico quanto string para maior flexibilidade

## 🤝 Contribuições

Contribuições são bem-vindas! Por favor, siga os padrões do projeto e faça testes adequados.

## 📄 Licença

Este projeto está sob licença MIT.