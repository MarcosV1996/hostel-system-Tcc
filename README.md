# Sistema de Agendamento para Albergue Noturno (TCC)

Este é o repositório principal e orquestrador do projeto de TCC, que implementa um sistema de agendamento completo utilizando uma arquitetura desacoplada com Frontend (Angular) e Backend (Laravel), containerizada com Docker.

## Arquitetura

O projeto foi estruturado em múltiplos repositórios para simular um ambiente de desenvolvimento profissional, seguindo práticas de microsserviços.

-   **Frontend:** Repositório contendo a aplicação Angular.
-   **Backend:** Repositório contendo a API em Laravel.
-   **Orquestrador (Este repositório):** Utiliza `git submodules` para unificar os serviços e o `docker-compose.yml` para configurar e executar o ambiente completo.

## Tecnologias Utilizadas

-   **Backend:** Laravel, PHP, SQLite
-   **Frontend:** Angular, TypeScript, Bootstrap
-   **Containerização:** Docker, Docker Compose

## Como Executar a Aplicação

**Pré-requisitos:**
* Git
* Docker
* Docker Compose

Com apenas 3 comandos no terminal, todo o ambiente será configurado e executado.

**1. Clone este repositório (orquestrador) com seus submódulos:**
   A flag `--recurse-submodules` é essencial para baixar o código do frontend e do backend junto.
   ```bash
   git clone --recurse-submodules [https://github.com/MarcosV1996/hostel-system-Tcc.git](https://github.com/MarcosV1996/hostel-system-Tcc.git)
   ```

**2. Entre na pasta do projeto:**
   ```bash
   cd hostel-system-Tcc
   ```

**3. Inicie os containers com Docker Compose:**
   O comando `--build` permite que as imagens Docker serão construídas a partir do zero.
   ```bash
   docker-compose up -d --build
   ```

Após a execução, a aplicação estará disponível nos seguintes endereços:

-   **Aplicação Frontend:** `http://localhost:8080`
-   **API Backend:** `http://localhost:8000`

---
