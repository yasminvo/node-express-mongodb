# Node Express MongoDB - Dockerized

## Repositório origem

O trabalho nesse repositário é originário de https://github.com/bezkoder/node-express-mongodb. O trabalho foi usado como base, devido à estrutura web padrão, para prática da disciplina de DevOps (2025/1).

## Participante

Yasmin Victoria Oliveira RA: 812308

## Descrição do Projeto

Este projeto é uma API backend simples desenvolvida em **Node.js + Express**, com persistência de dados em um banco **MongoDB**. A aplicação permite realizar operações CRUD (Create, Read, Update e Delete) de tutoriais.

A interface de administração do banco de dados é feita utilizando o **Mongo Express**, uma interface web que facilita a visualização e gestão dos dados armazenados no MongoDB.

O objetivo deste repositório é demonstrar a conteinerização completa de uma aplicação web, utilizando **Docker** e **Docker Compose**, com múltiplos contêineres se comunicando entre si.

---

## Funcionalidades da API

- Criar tutoriais
- Listar todos os tutoriais
- Buscar por título
- Atualizar um tutorial
- Deletar um tutorial
- Marcar como publicado ou não publicado

---

## Arquitetura dos Contêineres

O projeto roda utilizando **3 contêineres**, cada um com uma responsabilidade específica:

| Contêiner      | Descrição                                                                                         | Porta Local |
|----------------|---------------------------------------------------------------------------------------------------|-------------|
| `node-app`     | API desenvolvida em **Node.js + Express**, que gerencia os dados dos tutoriais                   | `8080`      |
| `mongo`        | Banco de dados **MongoDB**, responsável por armazenar os dados                                    | `27017`     |
| `mongo-express`| Interface web para visualizar e gerenciar o MongoDB de forma gráfica                              | `8081`      |


---

## Como Executar o Projeto

### Clone o repositório e suba os containers

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
docker-compose up -d
```
## Acessos

- API Backend:
http://localhost:8080/api/tutorials

- Mongo Express (Interface do Banco):
http://localhost:8081

## Testes Rápidos com cURL
```bash
curl -X POST http://localhost:8080/api/tutorials \
-H "Content-Type: application/json" \
-d '{
  "title": "Primeiro teste",
  "description": "Funciona!!!",
  "published": true
}'

curl http://localhost:8080/api/tutorials

curl http://localhost:8080/api/tutorials?title=Primeiro

```

