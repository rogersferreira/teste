# Ambiente modelo de desenvolvimento Laravel 12 (PHP 8.3 e MariaDB) para GitHub Codespaces

Este repositório fornece uma configuração para facilitar a configuração de um ambiente de desenvolvimento Laravel 12 baseado no PHP 8.3 no GitHub Codespaces . Você pode configurar rapidamente um ambiente de desenvolvimento usando MariaDB e Docker.

---

## 🚀 Instruções de configuração para GitHub Codespaces

### 1️⃣ Lançar Codespaces

1. Abra este repositório no GitHub
2. Clique no botão `<> Code`
3. Selecione na aba `Codespaces` > `Create Codespace on main`

Depois de configurar o Codespaces, seu ambiente de desenvolvimento será criado automaticamente.

---

### 2️⃣ Configurando o Laravel 12

Depois que o Codespaces estiver em execução, execute os seguintes comandos no terminal em ordem:

#### 🔹 2-1. Criar um projeto Laravel

```bash
composer create-project laravel/laravel:^12 laravel-app
cd laravel-app
```

#### 🔹 2-2. Configurações do ambiente (atualizar arquivo .env)

`.env` Edite o arquivo e atualize as informações de conexão do MariaDB.

```dotenv
DB_CONNECTION=mysql
DB_HOST=mariadb
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=secret
```

#### 🔹 2-3. Gerar uma chave de aplicação

```bash
php artisan key:generate
```

#### 🔹 2-4. Migração de banco de dados

```bash
php artisan migrate
```

#### 🔹 2-5. Iniciando o servidor

```bash
php artisan serve --host=0.0.0.0 --port=8080
```

Um pop-up aparecerá, então clique em "Abrir no navegador" para abrir uma nova aba.

---

## 🛠 Usando as ferramentas de linha de comando do MariaDB

Agora que você tem o cliente MariaDB instalado, você pode se conectar ao MariaDB com o seguinte comando:

```bash
mysql -h mariadb -uroot -p
```

Quando for solicitado que você insira uma senha, insira `.env` a senha que você definiu (por exemplo:`secret`)

---

## 🔍 Informações adicionais para Codespaces

### ✅ Configurações .devcontainer

Este repositório contém a configuração para GitHub Codespaces `.devcontainer`. Isso significa que quando você inicia o Codespaces, um ambiente de desenvolvimento é criado automaticamente.

### ✅ Usando Git

O Codespaces vem com o Git instalado, então os comandos usuais do Git estão disponíveis.

```bash
git add .
git commit -m "Update project"
git push origin main
```
