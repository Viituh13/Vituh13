
# Chat-Bot Melly (API em Python + Flask + SQLite)

Este repositório contém a API do **Chat-Bot Melly**, desenvolvida em **Python**, utilizando **Flask** e **SQLite**.  
Abaixo você encontra um passo a passo para rodar o projeto no seu ambiente local.

---

## ✅ Pré-requisitos

Antes de começar, certifique-se de ter instalado na sua máquina:

- [Python 3.x](https://www.python.org/)
- [Poetry](https://python-poetry.org/) (gerenciador de dependências do Python)
- Git (opcional, mas recomendado para clonar o repositório)

Você pode verificar se estão instalados com:

```bash
python --version
poetry --version
git --version
````

---

## Passo 1: Clonar o repositório

Clone este repositório para sua máquina local:

```bash
git clone https://github.com/seu-usuario/nome-do-repositorio.git
```

Entre na pasta do projeto:

```bash
cd nome-do-repositorio
```

> Substitua `seu-usuario` e `nome-do-repositorio` pelos valores corretos do seu GitHub.

---

## Passo 2: Configurar o ambiente Python com Poetry

Dentro da pasta do projeto, instale as dependências usando o **Poetry**:

```bash
poetry install
```

Esse comando irá ler o arquivo `pyproject.toml` e instalar todas as dependências necessárias (Flask, etc).

Se quiser entrar no ambiente virtual criado pelo Poetry:

```bash
poetry shell
```

---

## Passo 3: Configurar variáveis de ambiente (opcional)

Se o projeto utilizar variáveis de ambiente (por exemplo, chave secreta, URL do banco, etc), verifique se existe um arquivo:

```bash
.env.example
```

Caso exista:

1. Faça uma cópia do arquivo:

   ```bash
   cp .env.example .env
   ```
2. Edite o arquivo `.env` com os valores para o seu ambiente.

Se o projeto não usar `.env`, você pode pular este passo.

---

## Passo 4: Inicializar o banco de dados SQLite

Se o projeto já vier com o banco pronto (por exemplo, um arquivo `database.db` ou `melly.db`), você não precisa fazer nada.

Caso exista um script para criar ou popular o banco (por exemplo, `init_db.py`), execute:

```bash
poetry run python init_db.py
```

> Ajuste o nome do arquivo de acordo com o que o projeto realmente usa.

---

## Passo 5: Rodar a API Flask

Existem duas formas comuns de rodar o servidor Flask, dependendo de como o projeto foi configurado.

### 🅰️ Usando o comando `flask --app`

Se o arquivo principal da aplicação for `app.py` (ou um pacote `app`), você pode rodar:

```bash
poetry run flask --app app run
```

ou, se estiver dentro do `poetry shell`:

```bash
flask --app app run
```

### 🅱️ Usando `python app.py`

Em alguns projetos, o arquivo `app.py` já chama `app.run()` diretamente.
Nesse caso, você pode rodar:

```bash
poetry run python app.py
```

O servidor será iniciado normalmente em:

```text
http://127.0.0.1:5000
```

ou

```text
http://localhost:5000
```

---

## Passo 6: Testar as rotas da API

Com o servidor rodando, você pode testar as rotas utilizando:

* Navegador (para rotas GET simples)
* [Postman](https://www.postman.com/)
* [Insomnia](https://insomnia.rest/)
* `curl` no terminal

Exemplo usando `curl`:

```bash
curl http://localhost:5000/
```

> Ajuste a rota conforme a documentação das rotas do Chat-Bot Melly (por exemplo: `/chat`, `/mensagens`, etc).

---

## Passo 7: Modificar o projeto

Agora que o projeto está rodando localmente, você pode:

* Alterar o código Python (lógica do bot, rotas, integração com banco, etc)
* Ajustar o modelo de dados no SQLite
* Adicionar novas rotas à API

Após qualquer alteração, basta reiniciar o servidor Flask.

---

## Passo 8: Publicar suas modificações

Se quiser enviar suas alterações para um repositório remoto no GitHub:

1. Crie um **novo repositório** vazio no GitHub.
2. No terminal, dentro da pasta do projeto, rode:

```bash
git remote set-url origin https://github.com/seu-usuario/nome-do-novo-repositorio.git
git add .
git commit -m "Minhas modificações no Chat-Bot Melly"
git push -u origin master
```

> Ajuste o nome da branch (`master` ou `main`) conforme o padrão do seu repositório.

---

## 🧠 Dúvidas?

Se algo não funcionar (por exemplo, erro ao importar `app`, erro de banco, etc), verifique:

* Se você está **na pasta correta** do projeto.
* Se o arquivo principal realmente se chama **`app.py`**.
* Se rodou `poetry install` antes de tentar iniciar o servidor.
