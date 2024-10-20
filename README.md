# geysiane-ap1_est-gio

Sistema de Agendamento de Laboratórios
Este projeto é uma aplicação web que permite a professores agendar laboratórios para suas atividades, gerenciar reservas e consultar a disponibilidade de laboratórios.

Funcionalidades Principais
Cadastro de Professoras: Permite que professoras se cadastrem no sistema.
Login de Professoras: Autenticação segura de professoras cadastradas.
Listagem de Laboratórios: Exibe todos os laboratórios disponíveis para reserva.
Agendamento de Laboratórios: Professoras podem reservar laboratórios para datas e horários específicos.
Consulta de Agendamentos: Visualização dos agendamentos de laboratórios em datas específicas.
Atualização de Agendamento: Permite editar detalhes de um agendamento existente.
Exclusão de Agendamento: Permite remover agendamentos do sistema.
Definição do Banco de Dados
O banco de dados do sistema é estruturado da seguinte forma:

Entidades
users (Professoras)

id: Identificador único (PK)
name: Nome da professora (STRING)
email: Email da professora (STRING)
password: Senha criptografada (STRING)
labs (Laboratórios)

id: Identificador único (PK)
name: Nome do laboratório (STRING)
bookings (Agendamentos)

id: Identificador único (PK)
user_id: Chave estrangeira referenciando a tabela de professoras (FK)
lab_id: Chave estrangeira referenciando a tabela de laboratórios (FK)
date: Data do agendamento (STRING ou formato de data)
time: Horário do agendamento (STRING)
Relacionamentos
users possui uma relação de um-para-muitos com bookings (uma professora pode fazer vários agendamentos).
labs possui uma relação de um-para-muitos com bookings (um laboratório pode ser reservado várias vezes).
Rotas da API (CRUD Funcional)
A aplicação utiliza ExpressJS para implementar as seguintes rotas:

Cadastro de Professora:
POST /register: Criptografa a senha e cadastra a professora no sistema.

Login de Professora:
POST /login: Autentica a professora registrada e retorna um token de sessão.

Listar Laboratórios:
GET /labs: Exibe a lista de todos os laboratórios disponíveis para reserva.

Agendar Laboratório:
POST /book: Permite que uma professora reserve um laboratório para uma data e horário específicos.

Listar Agendamentos:
GET /bookings: Exibe os agendamentos de um laboratório em uma data específica.

Atualizar Agendamento:
PUT /bookings/:id: Atualiza os detalhes de um agendamento existente.

Excluir Agendamento:
DELETE /bookings/:id: Remove um agendamento existente.

Diagrama de Rotas
Abaixo está um diagrama ilustrando as principais rotas da API:


Tecnologias Utilizadas
Node.js e ExpressJS para o backend.
MySQL ou PostgreSQL para o banco de dados.
BCrypt para criptografia de senhas.
