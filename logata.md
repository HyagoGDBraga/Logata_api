# Logata

API REST de catálogo de produtos para pequenos comércios, desenvolvida na disciplina **Planejar e construir esteiras de automação de software** (UNIFACISA).

> 🚧 Projeto em construção. Este README será atualizado conforme a aplicação e as pipelines de CI/CD evoluírem.

## Sobre o projeto

Pequenos comércios costumam controlar seus produtos em planilhas ou cadernos, o que causa duplicidade de cadastros, preços desatualizados e dificuldade para buscar itens por categoria.

A **Logata** centraliza o cadastro de produtos organizados por categorias. Com ela é possível cadastrar categorias e produtos, listar e filtrar itens por categoria e faixa de preço, consultar os produtos de uma categoria e atualizar os dados de cada produto.

## Tecnologias

| Camada | Tecnologia |
|---|---|
| Backend | Python + FastAPI |
| Banco de dados relacional | PostgreSQL |
| Versionamento e CI/CD | GitLab |

## Modelo de dados inicial

| Tabela | Campos principais | Relação |
|---|---|---|
| `categorias` | `id` (PK), `nome`, `descricao` | 1 categoria possui N produtos |
| `produtos` | `id` (PK), `nome`, `descricao`, `preco`, `estoque`, `categoria_id` (FK) | Cada produto pertence a 1 categoria |

## Rotas planejadas

| # | Método | Rota | Descrição | Responsável |
|---|--------|------|-----------|-------------|
| 1 | POST | `/categorias` | Cadastra uma nova categoria | Hyago |
| 2 | POST | `/produtos` | Cadastra um produto vinculado a uma categoria | Ramon |
| 3 | GET | `/produtos` | Lista produtos, com filtros opcionais por categoria e faixa de preço | Márcio |
| 4 | GET | `/categorias/{id}/produtos` | Lista os produtos de uma categoria | Jonas |
| 5 | PUT | `/produtos/{id}` | Atualiza os dados de um produto | Sairo |

## Equipe

| Nome | E-mail |
|---|---|
| Hyago Gabriel Diniz Braga | hyago.gabriel2017@gmail.com |
| Ramon Gonçalves Cabral | ramongc118@gmail.com |
| Márcio Vitor de Souza Nascimento | vitormert@gmail.com |
| Jonas Cavalcante Mendes | jcavalcante2704@gmail.com |
| Sairo José Costa Soares Filho | sairo.filho@maisunifacisa.com.br |

## Como executar

> Em construção. As instruções de instalação, configuração do banco e execução da API serão adicionadas nas próximas etapas.

Previsão do passo a passo:

1. Clonar o repositório.
2. Criar e ativar um ambiente virtual Python.
3. Instalar as dependências (`pip install -r requirements.txt`).
4. Configurar as variáveis de ambiente de conexão com o PostgreSQL.
5. Iniciar a API (`uvicorn app.main:app --reload`).
6. Acessar a documentação interativa em `http://localhost:8000/docs`.

## Contribuição

- Ninguém faz push direto em `main`: tudo entra por merge request.
- Cada integrante trabalha em sua própria branch (`feature/<nome-da-tarefa>`).
- Mensagens de commit curtas e no imperativo (por exemplo, `adiciona rota de cadastro de categoria`).