# Sistema de Agendamento para Albergue Noturno (TCC)

Este é o repositório principal e orquestrador do projeto de TCC, que implementa um sistema de agendamento completo utilizando uma arquitetura desacoplada com Frontend (Angular) e Backend (Laravel), containerizada com Docker.

## Arquitetura

O projeto foi estruturado em múltiplos repositórios para simular um ambiente de desenvolvimento profissional, seguindo práticas de microsserviços.

-   **Frontend:** Repositório contendo a aplicação Angular. ([appointment-front-end](https://github.com/MarcosV1996/appointment-front-end))
-   **Backend:** Repositório contendo a API em Laravel. ([appointment-backend](https://github.com/MarcosV1996/appointment-backend))
-   **Orquestrador (Este repositório):** Utiliza `git submodules` para unificar os serviços e o `docker-compose.yml` para configurar e executar o ambiente completo.

## Tecnologias Utilizadas

-   **Backend:** Laravel, PHP 8.2, SQLite
-   **Frontend:** Angular, TypeScript, Bootstrap
-   **Containerização:** Docker, Docker Compose
-   **Servidor Web:** Nginx

## Como Executar a Aplicação

**Pré-requisitos:**
* Git
* Docker
* Docker Compose

Com apenas alguns comandos no terminal, todo o ambiente será configurado e executado.

#### Passo 1: Clonar o Repositório
A flag `--recurse-submodules` é essencial para baixar o código do frontend e do backend junto.
```bash
git clone --recurse-submodules [https://github.com/MarcosV1996/hostel-system-Tcc.git](https://github.com/MarcosV1996/hostel-system-Tcc.git)
```

#### Passo 2: Entrar na Pasta do Projeto
```bash
cd hostel-system-Tcc
```

#### Passo 3: Construir e Iniciar os Containers
Este comando lê o `docker-compose.yml`, constrói as imagens do backend e do frontend e inicia os serviços em segundo plano.
```bash
docker-compose up -d --build
```

#### Passo 4: Preparar o Banco de Dados
Na primeira vez que o projeto roda, o banco de dados é criado vazio. Este comando executa as "migrations" do Laravel para criar as tabelas e popula o banco com dados iniciais.
```bash
docker-compose exec app php artisan migrate --seed
```

---

Após a execução de todos os passos, a aplicação estará disponível nos seguintes endereços:

-   **Aplicação Frontend:** [http://localhost:8080](http://localhost:8080)
-   **API Backend:** [http://localhost:8000](http://localhost:8000)
