
QUESTÃO-1

Sistema de Cadastro de Livros – PHP + SQLite

Projeto desenvolvido por Allysson Silva Pereira – Matrícula: 201708296824

 Sobre o Projeto

Este sistema tem como objetivo gerenciar livros utilizando PHP e SQLite.
A aplicação permite:

 Cadastrar livros (título, autor e ano)

 Listar livros cadastrados

 Excluir livros pelo ID

 Utilizar um banco de dados SQLite simples, rápido e sem necessidade de servidor dedicado

A interface é construída em HTML/CSS e o backend usa PHP para comunicação com o banco.

 Estrutura do Projeto
/
├── index.php           # Página principal: cadastro e listagem
├── add_book.php        # Script para inserir livros no banco
├── delete_book.php     # Script para excluir livros
├── database.php        # Arquivo de conexão SQLite
└── banco.db           # Banco de dados SQLite (criado automaticamente)

 Tecnologias Utilizadas

PHP 

SQLite3

HTML + CSS

XAMPP 

 Funcionamento do index.php

O arquivo index.php é responsável por:

 Carregar o banco de dados
require 'database.php'; 
$lista = $db->query("SELECT * FROM livros ORDER BY id DESC");

 Exibir o formulário de cadastro

Campos:

Título

Autor

Ano

O envio é feito para add_book.php.

 Listar todos os livros do banco

A consulta retorna cada livro e monta uma tabela com:

Título

Autor

Ano

Botão de exclusão (link para delete_book.php?id=)

 Inserindo Livros

O arquivo add_book.php deve receber os dados via POST e inseri-los no banco:

<form action="add_book.php" method="POST">

 Excluindo Livros

Cada item listado possui um link:

delete_book.php?id=ID_DO_LIVRO


O script exclui o registro correspondente no banco.

 Como Executar o Projeto
1️ Instale o XAMPP

Certifique-se de que o Apache está funcionando.

2️ Coloque os arquivos na pasta:
C:\xampp\htdocs

3️ No navegador, abra:
http://localhost/QUESTAO-1/index.php

4️ O banco SQLite será criado automaticamente ao rodar database.php




QUESTÃO-2


Sistema de Gerenciamento de Tarefas – PHP + SQLite

Projeto desenvolvido por Allysson Silva Pereira – Matrícula: 201708296824

 Sobre o Projeto

Este sistema tem como objetivo gerenciar tarefas simples utilizando PHP e SQLite, oferecendo uma interface prática e intuitiva.
A aplicação permite:

 Adicionar tarefas

 Definir data de vencimento

 Marcar como concluída 

 Filtrar tarefas por:

Todas

Concluídas

Não concluídas

 Excluir tarefas

O banco de dados SQLite armazena cada tarefa com:
ID, descrição, data de vencimento, status concluída (0/1).

 Estrutura do Projeto
/
├── index.php              # Página principal com listagem, filtros e formulário
├── add_tarefa.php         # Script para salvar nova tarefa
├── update_tarefa.php      # Atualiza status concluída/não concluída
├── delete_tarefa.php      # Exclui uma tarefa pelo ID
├── database.php           # Conexão com o banco SQLite
└── tarefas.db             # Banco SQLite (criado automaticamente)

 Tecnologias Utilizadas

PHP 

SQLite3

HTML + CSS

Servidor XAMPP 

 Funcionamento do index.php
 1. Conexão com o banco
require 'database.php';
$db = getDB();

 2. Filtro por status

O sistema verifica o filtro enviado via GET e muda a consulta:

?filtro=1 → tarefas concluídas

?filtro=0 → tarefas não concluídas

vazio → todas

 3. Formulário para adicionar tarefas

Campos:

Descrição

Data de vencimento

Envio para add_tarefa.php.

 4. Listagem com tabela

Cada linha mostra:

Checkbox para marcar/desmarcar conclusão

Descrição (riscada se concluída)

Data

Botão "Excluir"

Ao clicar no checkbox, o sistema chama automaticamente:

update_tarefa.php?id=ID&status=0 ou 1

 Adicionando Tarefas

O formulário envia via POST:

add_tarefa.php


Esse script insere a tarefa no banco SQLite.

 Atualizar Status (Concluída / Não Concluída)

O checkbox chama automaticamente:

update_tarefa.php?id=2&status=1


O script altera o campo concluida.

 Excluindo Tarefas

Cada item possui o link:

delete_tarefa.php?id=ID


Se confirmado, a tarefa é excluída.

 Como Executar o Projeto
 Instalar o XAMPP

Ative o Apache.

 Colocar os arquivos na pasta:
C:\xampp\htdocs\

 Acessar pelo navegador:
http://localhost/QUESTAO-2/index.php

 O banco será criado automaticamente ao carregar database.php.












