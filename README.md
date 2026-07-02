# Sistema de Controle de Loja e Modelagem de Dados — MySQL

## 📌 Visão Geral do Projeto
Este projeto consiste no desenvolvimento e estruturação do banco de dados relacional **`sistema_loja`**. O objetivo é gerenciar as operações comerciais de uma loja, cobrindo o cadastro de clientes, colaboradores, portfólio de produtos e o fluxo completo de registros de vendas com total integridade referencial.

## 🗄️ Estrutura e Modelagem do Banco de Dados
O banco foi modelado com chaves primárias (`PRIMARY KEY`) e chaves estrangeiras (`FOREIGN KEY`), garantindo relacionamentos consistentes. A estrutura é composta pelas seguintes tabelas e colunas:

* **`clientes`**: Armazena dados cadastrais dos compradores (`cliente_id`, `nome`, `sexo`, `cidade`, `endereco`, `cpf`, `nascimento`).
* **`funcionarios`**: Registro do time de colaboradores (`func_id`, `nome`, `sexo`, `setor`, `cidade`, `endereco`, `cpf`, `nascimento`).
* **`produtos`**: Itens disponíveis para venda (`produto_id`, `nome`, `preco_unidade`).
* **`vendas`**: Cabeçalho dos pedidos realizados (`venda_id`, `func_id`, `cliente_id`, `dia`).
* **`itens_venda`**: Detalhamento físico de produtos por pedido (`item_id`, `produto_id`, `venda_id`, `quantidade`, `preco_unitario`).

## 👁️ Objetos de Banco de Dados Implementados (Views)
Para otimizar a extração de indicadores frequentes e simplificar relatórios, foi desenvolvida a seguinte View:
* **`vw_maior_iv`**: Objeto focado em calcular o valor máximo gerado por item vendido utilizando a lógica analítica `max(quantidade * preco_unitario)`.

## 📊 Inteligência de Negócio e Análises Práticas
A modelagem permite que o banco de dados responda rapidamente a perguntas estratégicas de negócio, tais como:
* **Ranking de Itens:** Identificação do faturamento total gerado por produto e volume de unidades vendidas através do relacionamento entre as tabelas de itens e produtos.
* **Desempenho da Equipe:** Monitoramento do total de pedidos e volume de vendas por funcionário de forma temporal (filtros por dia).
* **Comportamento do Consumidor:** Análise de histórico de compras cruzando os dados cadastrais dos clientes com os registros da tabela de vendas.

## 🛠️ Tecnologias Utilizadas
* **SGBD:** MySQL Server.
* **Interface:** MySQL Workbench (para modelagem e execução de scripts).
* **Linguagem SQL:** DDL (Estruturação) e DML (Consultas Analíticas).

## 🧠 Etapas do Desenvolvimento
1. **Modelagem Relacional:** Mapeamento de entidades para garantir que uma venda se relacione corretamente com clientes, produtos e funcionários através de Foreign Keys.
2. **Implementação de Constraints:** Configuração de índices e chaves para performance de busca.
3. **Abstração com Views:** Criação de camadas de leitura (`vw_maior_iv`) para facilitar o consumo dos dados por ferramentas de BI.

## ✉️ Contato
Desenvolvido por **Lucas Vinícius Martins Beato**
* **LinkedIn:** [linkedin.com/in/lucas-vinicius-martins-beato](https://www.linkedin.com/in/lucas-vinicius-martins-beato)
* **E-mail:** lvmbeato@gmail.com
