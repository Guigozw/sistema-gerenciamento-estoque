# Sistema de Gerenciamento de Estoque (WMS)

![Status](https://img.shields.io/badge/Status-Em_Desenvolvimento-yellow)
![Linguagens](https://img.shields.io/badge/Linguagens-Python%20%7C%20C%20%7C%20JavaScript-blue)
![Curso](https://img.shields.io/badge/Curso-ADS%20IFPI-green)

## Sobre o projeto

O Sistema de Gerenciamento de Estoque é um projeto acadêmico em desenvolvimento para o curso de Análise e Desenvolvimento de Sistemas (ADS) do Instituto Federal do Piauí (IFPI) - Campus Picos.

O objetivo principal é desenvolver uma solução eficiente para facilitar o controle de produtos, permitindo a organização de dados, o acompanhamento de quantidades disponíveis em tempo real e o registro detalhado de todas as movimentações de entrada e saída.

## Objetivos

- Facilitar o cadastro, edição e consulta detalhada de produtos.
- Controlar as quantidades disponíveis no estoque com precisão.
- Registrar o histórico de movimentações (entradas e saídas).
- Reduzir falhas e inconsistências do controle manual.
- Organizar as informações de maneira estruturada e de fácil acesso.

## Funcionalidades previstas

- [ ] Cadastro de novos produtos (código, nome, categoria, preço, quantidade).
- [ ] Consulta e listagem de produtos com filtros de busca.
- [ ] Atualização e exclusão de cadastros (CRUD completo).
- [ ] Registro de movimentação de entrada (abastecimento/compras).
- [ ] Registro de movimentação de saída (vendas/baixas).
- [ ] Consulta rápida da quantidade disponível em estoque e alertas de estoque baixo.

## Estrutura do Sistema

A arquitetura do projeto segue um modelo modular (separando interface, regras de negócio e dados) para facilitar o desenvolvimento em equipe e a manutenção do código. Abaixo está a organização de diretórios prevista:

    sistema-gerenciamento-estoque/
    ├── docs/                # Documentação do projeto (diagramas UML, requisitos)
    ├── src/                 # Código-fonte principal
    │   ├── controllers/     # Regras de negócio (lógica de entradas e saídas)
    │   ├── models/          # Entidades do sistema (Produto, Movimentacao, Categoria)
    │   ├── views/           # Interface do usuário (Telas do terminal ou GUI)
    │   ├── database/        # Conexão com o banco de dados e scripts de criação
    │   └── main             # Arquivo principal de inicialização do sistema
    ├── tests/               # Testes das funcionalidades
    ├── README.md            # Documentação inicial do repositório
    └── .gitignore           # Arquivos e pastas a serem ignorados pelo Git

## Tecnologias utilizadas

- Linguagens de programação: Python e Javascript
- Banco de dados: SQLite / MySQL (a definir a implementação exata)
- Controle de versão: Git e GitHub

## Equipe de desenvolvimento

- Alípio Joaquim da Rocha Barbosa
- Guilherme
- Igor Henrique Sousa Luz
- Kauã Gonçalves Fialho Oliveira
- Matheus Lelis

## Como executar

(As instruções para instalação de dependências, configuração do banco de dados e execução do projeto serão adicionadas após a implementação inicial do sistema).

## Licença

Projeto acadêmico. A definição de uma licença open-source (ex: MIT) será realizada posteriormente.
