# API de Livros 📚

Este projeto foi desenvolvido durante as aulas com o objetivo de criar uma API para gerenciamento de livros utilizando **Python, FastAPI e MySQL**.

Nesta primeira etapa, o foco foi preparar todo o ambiente e deixar a estrutura inicial da aplicação funcionando. A ideia é que, nas próximas etapas, a API seja aprimorada com funções para cadastrar, consultar, alterar e excluir livros.

## 🎯 Objetivo do projeto

O objetivo principal é desenvolver uma API que permita trabalhar com informações de livros de forma organizada, utilizando um banco de dados para armazenar essas informações.

Cada livro terá dados como:

* **ID:** identificação única do livro;
* **Título:** nome do livro;
* **Autor:** nome do autor;
* **Ano de publicação:** ano em que o livro foi publicado;
* **Disponibilidade:** informa se o livro está disponível ou não.

## 🛠️ Tecnologias utilizadas

Para desenvolver o projeto foram utilizadas as seguintes tecnologias:

* **Python:** linguagem utilizada no desenvolvimento da aplicação;
* **FastAPI:** framework utilizado para criar a API;
* **Uvicorn:** servidor responsável por executar a aplicação;
* **SQLAlchemy:** biblioteca utilizada para fazer a comunicação com o banco de dados;
* **PyMySQL:** permite a comunicação entre Python/SQLAlchemy e o MySQL;
* **Pydantic Settings:** utilizado para trabalhar com as configurações da aplicação;
* **MySQL:** banco de dados responsável por armazenar as informações;
* **XAMPP e phpMyAdmin:** utilizados para configurar e administrar o banco de dados;
* **Visual Studio Code:** ambiente utilizado para desenvolver o projeto;
* **Git e GitHub:** utilizados para versionar e armazenar o projeto.

## 📁 Estrutura do projeto

A estrutura inicial do projeto foi organizada da seguinte maneira:

```text
api-livros/
├── .env
├── .gitignore
├── requirements.txt
├── database/
│   └── biblioteca_db.sql
└── app/
    ├── __init__.py
    ├── database.py
    └── main.py
```

Cada arquivo possui uma função específica dentro do projeto. O `main.py` é responsável pela aplicação FastAPI, enquanto o `database.py` contém a configuração da conexão com o banco de dados.

O arquivo `requirements.txt` guarda as dependências utilizadas no projeto, permitindo que elas sejam instaladas novamente quando necessário.

Também foi criado o `.gitignore` para impedir que arquivos que não devem ser enviados ao GitHub, como o `.env` e o ambiente virtual, sejam versionados.

## 🗄️ Banco de dados

Para o projeto foi criado o banco de dados **biblioteca_db** no MySQL.

O banco foi configurado utilizando o XAMPP e o phpMyAdmin. Depois da criação, sua estrutura foi salva no arquivo:

```text
database/biblioteca_db.sql
```

Esse arquivo serve para guardar a estrutura do banco e facilitar sua reconstrução caso o projeto seja aberto em outro computador.

Uma parte importante dessa configuração foi também utilizar o arquivo `.env` para armazenar informações da conexão, principalmente a senha do banco. Dessa forma, essas informações não ficam expostas no GitHub.

## 🔌 Conexão com o MySQL

A conexão entre a API e o banco de dados foi configurada utilizando **SQLAlchemy** junto com o **PyMySQL**.

O projeto utiliza as informações presentes no `.env` para montar a conexão com o banco:

```text
DB_USER=root
DB_PASSWORD=senha
DB_HOST=localhost
DB_PORT=3306
DB_NAME=biblioteca_db
```

Com isso, a aplicação consegue acessar o banco de dados sem precisar deixar essas informações diretamente no código.

## 🚀 FastAPI

Depois da configuração do banco, foi criada a aplicação utilizando o FastAPI.

Também foi criada uma rota chamada:

```text
/health
```

Essa rota serve para verificar se a API está funcionando e se ela consegue se conectar ao banco de dados.

Ao acessar a rota, a resposta esperada é:

```json
{
    "status": "ok",
    "database": "connected"
}
```

Isso significa que o servidor está funcionando corretamente e que a conexão com o MySQL foi realizada com sucesso.

## ▶️ Executando o projeto

Para iniciar o servidor, é utilizado o comando:

```bash
uvicorn app.main:app --reload
```

Depois de iniciar, a API fica disponível localmente e pode ser acessada pelo navegador.

A rota de teste pode ser acessada em:

```text
http://127.0.0.1:8000/health
```

O FastAPI também disponibiliza uma documentação automática da API, que pode ser utilizada para visualizar e testar as rotas.

## 📌 Próximas etapas

Esta primeira etapa foi focada principalmente na preparação do ambiente, criação do banco e conexão entre o FastAPI e o MySQL.

Nas próximas etapas, o projeto será desenvolvido para realmente realizar as operações com os livros, como:

* Cadastrar novos livros;
* Listar os livros cadastrados;
* Consultar um livro específico;
* Atualizar informações;
* Excluir livros.

Posteriormente, também será criada uma interface utilizando **HTML, CSS e JavaScript**, que irá consumir a API pelo navegador.

## 💡 Conclusão

Nesta etapa consegui montar a base do projeto e entender melhor como funciona a comunicação entre uma API e um banco de dados. A estrutura foi preparada para que o projeto possa crescer nas próximas aulas, adicionando novas funcionalidades de forma organizada.

A atividade também ajudou a entender na prática a função de cada tecnologia utilizada, principalmente a relação entre **FastAPI, SQLAlchemy e MySQL**.
