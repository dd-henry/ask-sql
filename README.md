# Ask-SQL

Ask-SQL é uma ferramenta de linha de comando que traduz perguntas em linguagem natural para consultas SQL e as executa em seu banco de dados.

## Descrição

Este projeto utiliza modelos de linguagem (através do Ollama) para converter perguntas de usuários em consultas SQL válidas. Ele se conecta a um banco de dados PostgreSQL para executar a consulta e retornar o resultado, permitindo que usuários sem conhecimento de SQL possam consultar os dados.

## Recursos

*   Traduz linguagem natural para SQL.
*   Integração com Ollama para processamento de linguagem natural.
*   Conecta e executa consultas em um banco de dados PostgreSQL.
*   Arquitetura modular para fácil extensão.

## Como Funciona

1.  O usuário insere uma pergunta via linha de comando.
2.  O componente `Prompter` formata a pergunta em um prompt adequado para o modelo de linguagem.
3.  O componente `Translator` envia o prompt para o Ollama e recebe a consulta SQL gerada.
4.  O `Executor` se conecta ao banco de dados PostgreSQL.
5.  A consulta SQL é executada no banco de dados.
6.  O resultado é exibido para o usuário.

## Instalação

1.  **Clone o repositório:**
    ```bash
    git clone <url-do-seu-repositorio>
    cd ask-sql
    ```

2.  **Crie e ative um ambiente virtual:**
    ```bash
    python -m venv venv
    source venv/bin/activate
    ```

3.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Configure as variáveis de ambiente:**
    Crie um arquivo `.env` na raiz do projeto e adicione as informações de conexão com o banco de dados e a URL do Ollama.
    ```
    DB_HOST=localhost
    DB_PORT=5432
    DB_USER=seu_usuario
    DB_PASSWORD=sua_senha
    DB_NAME=seu_banco
    OLLAMA_API_URL=http://localhost:11434
    ```

## Como Usar

Para executar a aplicação, utilize o `app.py`:

```bash
python app.py "Sua pergunta em linguagem natural aqui"
```

**Exemplo:**

```bash
python app.py "Quantos usuários se cadastraram no último mês?"
```

## Executando os Testes

Para rodar a suíte de testes, use o `pytest`:

```bash
pytest
```
