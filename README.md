# 📋 CRUD API em Python com Flask

Este projeto é uma API simples de CRUD para gerenciamento de tarefas (Tasks), desenvolvida em Python utilizando o framework Flask. A API permite criar, visualizar, atualizar e excluir tarefas, mantendo os dados temporariamente em uma lista na memória.

## 🚀 Endpoints da API

A API oferece os seguintes endpoints para o gerenciamento de tarefas:

### ➕ Criar Tarefa

- **URL**: `/tasks`
- **Método HTTP**: `POST`
- **Descrição**: Cria uma nova tarefa com um título e uma descrição.
- **Exemplo de Corpo da Requisição**:
    ```json
    {
        "title": "Exemplo de Tarefa",
        "description": "Descrição da tarefa de exemplo"
    }
    ```
- **Resposta**: Retorna uma mensagem de sucesso.

### 📜 Obter Todas as Tarefas

- **URL**: `/tasks`
- **Método HTTP**: `GET`
- **Descrição**: Retorna uma lista de todas as tarefas criadas.
- **Resposta**:
    ```json
    {
        "tasks": [
            {
                "id": 1,
                "title": "Exemplo de Tarefa",
                "description": "Descrição da tarefa de exemplo",
                "completed": false
            }
        ],
        "total_tasks": 1
    }
    ```

### 🔍 Obter Tarefa por ID

- **URL**: `/tasks/<int:id_task>`
- **Método HTTP**: `GET`
- **Descrição**: Retorna os detalhes de uma tarefa específica.
- **Resposta**: Retorna a tarefa encontrada ou uma mensagem de erro caso a tarefa não exista.

### ✏️ Atualizar Tarefa

- **URL**: `/tasks/<int:id>`
- **Método HTTP**: `PUT`
- **Descrição**: Atualiza uma tarefa existente com novas informações de título, descrição e status de conclusão.
- **Exemplo de Corpo da Requisição**:
    ```json
    {
        "title": "Título Atualizado",
        "description": "Descrição atualizada",
        "completed": true
    }
    ```
- **Resposta**: Retorna uma mensagem de sucesso ou erro caso a tarefa não seja encontrada.

### 🗑️ Deletar Tarefa

- **URL**: `/task/<int:id>`
- **Método HTTP**: `DELETE`
- **Descrição**: Exclui uma tarefa específica com base no ID fornecido.
- **Resposta**: Retorna uma mensagem de sucesso ou erro caso a tarefa não seja encontrada.

## 📂 Estrutura do Projeto

O projeto possui a seguinte estrutura:

- **app.py**: Arquivo principal com os endpoints da API e lógica de CRUD.
- **models/task.py**: Definição da classe `Task` (presume-se que a classe tenha métodos para manipulação dos dados, incluindo o método `to_dict` para conversão a dicionário JSON).

## 🛠️ Executando o Projeto

1. Instale as dependências do Flask:
    ```bash
    pip install flask
    ```

2. Execute o servidor Flask:
    ```bash
    python app.py
    ```

3. Acesse a API em `http://127.0.0.1:5000`.

## 📝 Observações

Este projeto armazena dados em uma lista temporária na memória (`tasks`) e é ideal para testes e aprendizado. Para armazenamento persistente, considere integrar um banco de dados, como SQLite ou PostgreSQL.

## 📜 Licença

Este projeto está licenciado sob a licença MIT. Sinta-se à vontade para usá-lo e modificá-lo conforme necessário.

---

Desenvolvido com ❤️ em Python e Flask.
