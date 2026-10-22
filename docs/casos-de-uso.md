# Documento de Casos de Uso
## Sistema de Gerenciamento de Estoque

## 1. Visão Geral do Sistema

O Sistema de Gerenciamento de Estoque é uma aplicação web desenvolvida para controlar o fluxo de mercadorias de uma instituição. O sistema permitirá o gerenciamento de contas de usuários, fornecedores, categorias, unidades de medida e produtos, além do registro de entradas e saídas de mercadorias.

A aplicação contará com controle de acesso por perfil, atualização das quantidades disponíveis em estoque, alertas de estoque baixo e relatórios gerenciais para auxiliar na tomada de decisões.

Por ser uma aplicação web, o sistema poderá ser acessado por meio de um navegador, conforme as permissões de acesso e a infraestrutura de hospedagem adotada.

## 2. Atores do Sistema

### 2.1 Administrador

Responsável pelo gerenciamento das contas dos usuários, dos fornecedores, das categorias e das unidades de medida. Possui permissões para configurar informações administrativas do sistema.

### 2.2 Estoquista

Responsável pelo gerenciamento dos dados dos produtos, pelo registro das entradas e saídas de mercadorias e pelo acompanhamento dos alertas de estoque baixo.

### 2.3 Gerente

Responsável por consultar o histórico e a auditoria das movimentações, gerar relatórios financeiros do estoque e analisar os produtos com maior e menor movimentação de saída.

## 3. Especificação dos Casos de Uso

### UC01 — Autenticar no sistema com controle de acesso

**Atores principais:** Administrador, Estoquista e Gerente.

**Objetivo:** Permitir que os três perfis autorizados acessem o sistema mediante autenticação e utilizem somente as funcionalidades permitidas para seus respectivos perfis.

**História de usuário relacionada:** Funcionalidade de apoio à HU01, que estabelece a necessidade de garantir que apenas funcionários autorizados acessem o sistema.

**Pré-condições:**
- O usuário deve possuir uma conta cadastrada e ativa.
- O sistema deve estar disponível.

**Fluxo principal:**
1. O ator acessa a página de login.
2. O sistema solicita as credenciais de acesso.
3. O ator informa suas credenciais.
4. O sistema valida as informações fornecidas.
5. O sistema identifica o perfil associado à conta.
6. O sistema concede acesso às funcionalidades autorizadas para aquele perfil.

**Fluxos alternativos:**
- 4a. Se as credenciais forem inválidas, o sistema informa o erro e solicita uma nova tentativa.
- 4b. Se a conta estiver inativa, o sistema impede o acesso.

**Pós-condições:**
- O ator autenticado pode utilizar as funcionalidades autorizadas.
- Se a autenticação falhar, o acesso não é concedido.

### UC02 — Gerenciar contas de usuários

**Ator principal:** Administrador.

**História de usuário relacionada:** HU01.

**Objetivo:** Permitir o cadastro, a consulta, a alteração e a inativação das contas dos funcionários autorizados a utilizar o sistema.

**Pré-condições:**
- O administrador deve estar autenticado.
- O administrador deve possuir permissão para gerenciar contas.

**Fluxo principal:**
1. O administrador acessa a área de gerenciamento de usuários.
2. O sistema apresenta as contas cadastradas.
3. O administrador escolhe cadastrar, consultar, alterar ou inativar uma conta.
4. O administrador informa os dados necessários ou seleciona a conta que deseja modificar.
5. O sistema valida os dados fornecidos.
6. O sistema registra a operação solicitada.
7. O sistema apresenta uma confirmação.

**Fluxos alternativos:**
- 5a. Se os dados estiverem incompletos ou inválidos, o sistema solicita a correção.
- 5b. Se a conta selecionada não for encontrada, o sistema informa que o registro não está disponível.

**Pós-condições:**
- A conta é cadastrada, alterada ou inativada conforme a operação realizada.

### UC03 — Gerenciar fornecedores

**Ator principal:** Administrador.

**História de usuário relacionada:** HU02.

**Objetivo:** Permitir o cadastro e a manutenção dos dados dos fornecedores que abastecem a instituição.

**Pré-condições:**
- O administrador deve estar autenticado e autorizado.

**Fluxo principal:**
1. O administrador acessa a área de fornecedores.
2. O sistema apresenta os fornecedores cadastrados.
3. O administrador escolhe cadastrar, consultar, alterar ou inativar um fornecedor.
4. O administrador informa os dados necessários ou seleciona o registro que deseja modificar.
5. O sistema valida as informações.
6. O sistema registra a operação.
7. O sistema apresenta uma confirmação.

**Fluxos alternativos:**
- 5a. Se os dados obrigatórios estiverem ausentes ou inválidos, o sistema solicita a correção.
- 5b. Se o fornecedor selecionado não for encontrado, o sistema informa a ocorrência.

**Pós-condições:**
- Os dados do fornecedor ficam registrados ou atualizados conforme a operação realizada.

### UC04 — Gerenciar categorias e unidades de medida

**Ator principal:** Administrador.

**História de usuário relacionada:** HU03.

**Objetivo:** Permitir o cadastro e a manutenção das categorias e unidades de medida utilizadas na organização dos produtos.

**Pré-condições:**
- O administrador deve estar autenticado e autorizado.

**Fluxo principal:**
1. O administrador acessa a área de categorias e unidades de medida.
2. O sistema apresenta os registros existentes.
3. O administrador escolhe cadastrar, consultar, alterar ou inativar um registro.
4. O administrador informa os dados necessários.
5. O sistema valida as informações.
6. O sistema registra a operação.
7. O sistema apresenta uma confirmação.

**Fluxos alternativos:**
- 5a. Se os dados forem inválidos ou incompletos, o sistema solicita a correção.
- 5b. Se o registro selecionado não for encontrado, o sistema informa a ocorrência.

**Pós-condições:**
- As categorias e unidades de medida ficam disponíveis para a organização dos produtos.

### UC05 — Gerenciar dados do catálogo de produtos

**Ator principal:** Estoquista.

**História de usuário relacionada:** HU04.

**Objetivo:** Permitir o cadastro e a manutenção dos dados dos produtos controlados pelo sistema.

**Pré-condições:**
- O estoquista deve estar autenticado e autorizado.
- As categorias e unidades de medida necessárias devem estar cadastradas.

**Fluxo principal:**
1. O estoquista acessa o catálogo de produtos.
2. O sistema apresenta os produtos cadastrados.
3. O estoquista escolhe cadastrar, consultar, alterar ou inativar um produto.
4. O estoquista informa ou modifica os dados do produto.
5. O sistema valida as informações.
6. O sistema registra a operação.
7. O sistema apresenta uma confirmação.

**Fluxos alternativos:**
- 5a. Se houver dados obrigatórios ausentes ou inválidos, o sistema solicita a correção.
- 5b. Se a categoria ou unidade de medida selecionada não estiver disponível, o sistema informa a inconsistência.

**Pós-condições:**
- O catálogo de produtos fica atualizado conforme a operação realizada.

### UC06 — Registrar entrada de lote de mercadorias

**Ator principal:** Estoquista.

**História de usuário relacionada:** HU05.

**Objetivo:** Registrar a chegada de mercadorias ao estoque em decorrência de compras ou reposições.

**Pré-condições:**
- O estoquista deve estar autenticado e autorizado.
- O produto e o fornecedor envolvidos devem estar cadastrados.

**Fluxo principal:**
1. O estoquista acessa a funcionalidade de entrada de mercadorias.
2. O sistema apresenta o formulário de registro.
3. O estoquista seleciona o produto e o fornecedor.
4. O estoquista informa a quantidade recebida e os demais dados necessários do lote.
5. O sistema valida as informações.
6. O sistema registra a entrada do lote.
7. O sistema define o status inicial do lote.
8. O sistema apresenta uma confirmação.

**Fluxos alternativos:**
- 5a. Se os dados obrigatórios estiverem ausentes ou forem inválidos, o sistema solicita a correção.
- 5b. Se o produto ou fornecedor não estiver cadastrado, o sistema informa que o registro não pode ser concluído.

**Pós-condições:**
- A entrada do lote fica registrada.
- O lote pode ser acompanhado por meio do UC07.

### UC07 — Atualizar status do lote

**Ator principal:** Estoquista.

**História de usuário relacionada:** HU05.

**Objetivo:** Permitir o acompanhamento das etapas de processamento de um lote de mercadorias.

**Pré-condições:**
- O estoquista deve estar autenticado e autorizado.
- O lote deve estar previamente registrado.

**Fluxo principal:**
1. O estoquista acessa a lista de lotes.
2. O sistema apresenta os lotes e seus status atuais.
3. O estoquista seleciona um lote.
4. O sistema apresenta os dados do lote.
5. O estoquista solicita a atualização do status.
6. O sistema verifica se a transição solicitada é permitida.
7. O sistema atualiza o status do lote.
8. O sistema confirma a operação.

**Fluxos alternativos:**
- 6a. Se a transição não for permitida, o sistema informa que a alteração não pode ser realizada.
- 6b. Se o lote não for encontrado, o sistema informa que o registro não está disponível.

**Pós-condições:**
- O status do lote é atualizado quando a transição é válida.

**Ciclo de vida do lote:**

Pendente → Em Conferência → Armazenado → Arquivado.

### UC08 — Registrar saída de mercadorias por venda ou expedição

**Ator principal:** Estoquista.

**História de usuário relacionada:** HU06.

**Objetivo:** Registrar a retirada de produtos do estoque em razão de vendas ou expedições.

**Pré-condições:**
- O estoquista deve estar autenticado e autorizado.
- O produto deve estar cadastrado.

**Fluxo principal:**
1. O estoquista acessa a funcionalidade de saída de mercadorias.
2. O sistema apresenta o formulário de saída.
3. O estoquista seleciona o produto.
4. O estoquista informa a quantidade e o motivo da saída.
5. O sistema verifica a quantidade disponível em estoque.
6. O sistema valida a operação.
7. O sistema registra a saída e atualiza a quantidade disponível.
8. O sistema confirma a movimentação.

**Fluxos alternativos:**
- 5a. Se a quantidade solicitada for superior à disponível, o sistema impede a operação e informa a inconsistência.
- 6a. Se os dados forem inválidos, o sistema solicita a correção.

**Pós-condições:**
- A saída fica registrada no histórico de movimentações.
- A quantidade disponível é atualizada após uma operação válida.

### UC09 — Registrar baixa manual por quebra ou perda

**Ator principal:** Estoquista.

**História de usuário relacionada:** HU06, como extensão do controle de saídas.

**Objetivo:** Registrar a retirada de produtos do estoque em razão de quebra, perda ou outra ocorrência que justifique uma baixa manual.

**Pré-condições:**
- O estoquista deve estar autenticado e autorizado.
- O produto deve estar cadastrado.

**Fluxo principal:**
1. O estoquista acessa a funcionalidade de baixa manual.
2. O sistema apresenta o formulário de baixa.
3. O estoquista seleciona o produto afetado.
4. O estoquista informa a quantidade e o motivo da baixa.
5. O sistema verifica a quantidade disponível.
6. O sistema valida as informações.
7. O sistema registra a baixa e atualiza a quantidade disponível.
8. O sistema confirma a operação.

**Fluxos alternativos:**
- 5a. Se a quantidade informada for superior à disponível, o sistema impede a baixa e informa a inconsistência.
- 6a. Se os dados obrigatórios estiverem ausentes ou inválidos, o sistema solicita a correção.

**Pós-condições:**
- A baixa fica registrada no histórico.
- A quantidade disponível é atualizada após uma operação válida.

### UC10 — Monitorar alertas automáticos de estoque crítico

**Ator principal:** Estoquista.

**História de usuário relacionada:** HU07.

**Objetivo:** Identificar produtos cuja quantidade disponível esteja abaixo do limite mínimo definido.

**Pré-condições:**
- O estoquista deve estar autenticado e autorizado.
- Os produtos devem possuir um limite mínimo de estoque definido.

**Fluxo principal:**
1. O sistema consulta as quantidades disponíveis dos produtos.
2. O sistema compara as quantidades com os limites mínimos definidos.
3. O sistema identifica os produtos em condição de estoque crítico.
4. O sistema gera ou atualiza os alertas correspondentes.
5. O estoquista acessa a tela principal ou a área de alertas.
6. O sistema apresenta os produtos que precisam de reposição.

**Fluxos alternativos:**
- 2a. Se nenhum produto estiver em condição crítica, o sistema informa que não há alertas no momento.
- 2b. Se os dados necessários para a validação estiverem ausentes, o sistema sinaliza a inconsistência.

**Pós-condições:**
- Os alertas ficam disponíveis para consulta pelo estoquista.

### UC11 — Consultar histórico e auditoria das movimentações

**Ator principal:** Gerente.

**História de usuário relacionada:** HU08.

**Objetivo:** Permitir a consulta do histórico detalhado das movimentações diárias do estoque.

**Pré-condições:**
- O gerente deve estar autenticado e autorizado.

**Fluxo principal:**
1. O gerente acessa a área de histórico e auditoria.
2. O sistema apresenta as opções de consulta.
3. O gerente seleciona o período ou os filtros disponíveis.
4. O sistema consulta as movimentações registradas.
5. O sistema apresenta os registros encontrados, incluindo os dados disponíveis de cada movimentação.
6. O gerente analisa o histórico apresentado.

**Fluxos alternativos:**
- 4a. Se não houver movimentações para os critérios selecionados, o sistema informa que nenhum registro foi encontrado.
- 3a. Se os filtros forem inválidos, o sistema solicita a correção.

**Pós-condições:**
- O histórico correspondente aos critérios informados fica disponível para consulta.
- A consulta não altera os registros de movimentação.

### UC12 — Gerar cálculo financeiro do capital imobilizado em estoque

**Ator principal:** Gerente.

**História de usuário relacionada:** HU09.

**Objetivo:** Calcular e apresentar o valor financeiro atual dos produtos mantidos em estoque.

**Pré-condições:**
- O gerente deve estar autenticado e autorizado.
- Os produtos devem possuir quantidades e valores unitários válidos para o cálculo.

**Fluxo principal:**
1. O gerente acessa a área de relatórios financeiros.
2. O gerente solicita o cálculo do valor financeiro do estoque.
3. O sistema consulta os produtos e suas quantidades disponíveis.
4. O sistema obtém os valores unitários necessários.
5. O sistema calcula o valor financeiro de cada produto.
6. O sistema soma os valores calculados.
7. O sistema apresenta o valor total do estoque.

**Fluxos alternativos:**
- 3a. Se não houver produtos registrados, o sistema informa que não existem dados para o cálculo.
- 4a. Se algum produto não possuir valor financeiro válido, o sistema sinaliza a inconsistência.

**Pós-condições:**
- O resultado do cálculo fica disponível para consulta pelo gerente.

**Regra de cálculo:**

Valor financeiro do estoque = soma da quantidade disponível de cada produto multiplicada pelo respectivo valor unitário.

### UC13 — Gerar relatório de movimentação de saída dos produtos

**Ator principal:** Gerente.

**História de usuário relacionada:** HU10.

**Objetivo:** Identificar os produtos com maior e menor quantidade de saídas em determinado período.

**Pré-condições:**
- O gerente deve estar autenticado e autorizado.
- Devem existir dados de movimentação de saída para análise.

**Fluxo principal:**
1. O gerente acessa a área de relatórios gerenciais.
2. O gerente seleciona o relatório de movimentação de saída.
3. O gerente informa o período ou os critérios de consulta disponíveis.
4. O sistema consulta as movimentações de saída registradas.
5. O sistema calcula a quantidade de saídas por produto.
6. O sistema organiza os produtos conforme a movimentação identificada.
7. O sistema apresenta o relatório, destacando os produtos com maior e menor saída.

**Fluxos alternativos:**
- 4a. Se não houver movimentações no período selecionado, o sistema informa que não existem dados para gerar o relatório.
- 3a. Se os critérios informados forem inválidos, o sistema solicita a correção.

**Pós-condições:**
- O relatório fica disponível para consulta pelo gerente.

## 4. Rastreabilidade entre Histórias de Usuário e Casos de Uso

| História de usuário | Casos de uso relacionados |
|---|---|
| HU01 — Gerenciar contas de usuários | UC02 |
| HU02 — Gerenciar fornecedores | UC03 |
| HU03 — Cadastrar categorias e unidades de medida | UC04 |
| HU04 — Gerenciar dados dos produtos | UC05 |
| HU05 — Registrar entrada de mercadorias | UC06, UC07 |
| HU06 — Registrar saída de produtos | UC08, UC09 |
| HU07 — Visualizar alertas de estoque baixo | UC10 |
| HU08 — Consultar histórico e auditoria | UC11 |
| HU09 — Gerar relatório financeiro do estoque | UC12 |
| HU10 — Visualizar produtos com maior e menor saída | UC13 |

### Observação sobre a autenticação

O UC01 é uma funcionalidade transversal utilizada pelos três perfis do sistema. Como a HU01 descreve especificamente o gerenciamento de contas, o UC01 não foi associado diretamente a ela na tabela de rastreabilidade. A autenticação deve ser documentada como uma funcionalidade necessária ao controle de acesso. Caso o professor exija que todos os casos de uso estejam vinculados a uma história de usuário, a equipe deverá registrar essa necessidade em uma história específica ou ajustar a HU01 com a aprovação do grupo.

## 5. Regras Gerais do Sistema

1. O acesso às funcionalidades deve respeitar o perfil e as permissões de cada ator.
2. As saídas e baixas manuais não devem reduzir a quantidade disponível em estoque abaixo de zero.
3. O sistema deve comparar a quantidade disponível com o limite mínimo definido para identificar produtos em estoque crítico.
4. Os lotes devem seguir o ciclo de status: Pendente, Em Conferência, Armazenado e Arquivado.
5. Os cálculos financeiros devem utilizar quantidades e valores unitários válidos.
6. As movimentações devem permanecer registradas para consulta no histórico e na auditoria.

## 6. Considerações Finais

Os casos de uso apresentados descrevem as principais interações entre os atores e o Sistema de Gerenciamento de Estoque. Eles servem como base para o desenvolvimento do diagrama de casos de uso e para o planejamento das funcionalidades da aplicação web.

As regras específicas de validação, os campos obrigatórios, as permissões e as transições de status deverão ser confirmados pela equipe antes da implementação.