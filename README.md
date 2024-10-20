# geysiane-ap1_est-gio

Sistema de Agendamento de Laboratórios: 
Este projeto é uma aplicação web que permite a professores agendar laboratórios para suas atividades, gerenciar reservas e consultar a disponibilidade de laboratórios.

> Funcionalidades Principais:

- Cadastro de Professores: Permite que professores se cadastrem no sistema.
Login de Professores: Autenticação segura de professores cadastradas.
Listagem de Laboratórios: Exibe todos os laboratórios disponíveis para reserva.
Agendamento de Laboratórios: Professores podem reservar laboratórios para datas e horários específicos.
Consulta de Agendamentos: Visualização dos agendamentos de laboratórios em datas específicas.
Atualização de Agendamento: Permite editar detalhes de um agendamento existente.
Exclusão de Agendamento: Permite remover agendamentos do sistema.
Definição do Banco de Dados
O banco de dados do sistema é estruturado da seguinte forma:

> Entidades

- Users (Professores)
id: Identificador único (PK)
name: Nome do professor(STRING)
email: Email do professor (STRING)
password: Senha criptografada (STRING)

- Labs (Laboratórios)
id: Identificador único (PK)
name: Nome do laboratório (STRING)

- Bookings (Agendamentos)
id: Identificador único (PK)
user_id: Chave estrangeira referenciando a tabela de professores (FK)
lab_id: Chave estrangeira referenciando a tabela de laboratórios (FK)
date: Data do agendamento (STRING ou formato de data)
time: Horário do agendamento (STRING)

> Relacionamentos
- Users possui uma relação de um-para-muitos com bookings (um professor pode fazer vários agendamentos).
- Labs possui uma relação de um-para-muitos com bookings (um laboratório pode ser reservado várias vezes).

> Rotas da API (CRUD Funcional)
A aplicação utiliza ExpressJS para implementar as seguintes rotas:

- Cadastro de Professores:
POST /register: Criptografa a senha e cadastra os professores no sistema.

- Login de Professora:
POST /login: Autentica os professores registrada e retorna um token de sessão.

- Listar Laboratórios:
GET /labs: Exibe a lista de todos os laboratórios disponíveis para reserva.

- Agendar Laboratório:
POST /book: Permite que um professore reserve um laboratório para uma data e horário específicos.

- Listar Agendamentos:
GET /bookings: Exibe os agendamentos de um laboratório em uma data específica.

- Atualizar Agendamento:
PUT /bookings/:id: Atualiza os detalhes de um agendamento existente.

- Excluir Agendamento:
DELETE /bookings/:id: Remove um agendamento existente.

Diagrama de Rotas
Abaixo está um diagrama ilustrando as principais rotas da API:


Tecnologias Utilizadas
Node.js e ExpressJS para o backend.
MySQL ou PostgreSQL para o banco de dados.
BCrypt para criptografia de senhas.
