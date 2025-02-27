# FBD-TelaCrudd
Esta aplicação foi desenvolvida em Python, notebook do Jupyter e Panel.
Ela permite a leitura, inserção, edição e remoção de eventos e de doações
para lares temporários de um banco de dados. Essas ações ocorrem por meio do uso do 
PostgreSQL, sistema no qual o banco de dados é baseado

# Funcinalidades
## Eventos
Possui as colunas Id, Nome, Descrição, Data, Cidade, Bairro, Rua, Endereço. A manipulação desses atributos inclui:

* Consulta: Qualquer coluna pode ser usada para encontrar tuplas que as contenham.
* Inserção: Quando todos os campos obrigatórios estão preenchidos, as informações 
podem ser inseridas ao banco de dados.
* Edição: Ao preencher os campos de texto para consultar o banco de dados, pode-se usar a tabela ao lado para denominar os novos valores das tuplas encontradas na consulta.