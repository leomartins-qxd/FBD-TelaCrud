# FBD-TelaCrudd
Esta aplicação foi desenvolvida em Python, notebook do Jupyter e Panel.
Ela permite a leitura, inserção, edição e remoção de eventos e de doações
para lares temporários de um banco de dados. Essas ações ocorrem por meio do uso do 
PostgreSQL, sistema no qual o banco de dados é baseado

# Funcinalidades
## Tabelas
### Evento
Possui as colunas Id, Nome, Descrição, Data, Cidade, Bairro, Rua e Endereço.

### Doação
Possui as colunas Id, IdLarTemporário, IdVoluntário, Tipo, Quantidade, Valor e Descrição.

## Ações

A manipulação de ambas as tabelas inclui:

* Consulta: Qualquer coluna pode ser usada para encontrar tuplas que as contenham.
* Inserção: Quando todos os campos obrigatórios estão preenchidos, as informações 
podem ser inseridas ao banco de dados.
* Edição: Ao preencher os campos de texto para consultar o banco de dados, pode-se usar a tabela ao lado para denominar os novos valores das tuplas encontradas na consulta.
* Remoção: Preenchendo os campos de texto, é possível deletar todas as tuplas encontradas com as propriedades digitadas. Entretanto, é recomendável primeiro utilizar a consulta para confirmar quais tuplas serão eliminadas.

Vale ressaltar que a remoção de um evento também implicará na remoção de tuplas da tabela eventoparticipantes que referenciam este evento.

## Bibliotecas Utilizadas
* Pandas
* Psycopg2
* SQLAlchemy
* Panel

## Pré-requisitos
* Python (No mínimo versão 3.9, porém recomendado versão 3.13, que é a versão utilizada neste projeto).
* PostgreSQL instalado e configurado.
* A presença das tabelas "evento", "doacao" e "eventoparticipantes" no banco de dados.
* Todas as bibliotecas citadas anteriormente precisam estar instaladas.

#### Para visualizar no VSCode, são necessárias as extensões relacionadas ao Jupyter:
* Jupyter
* Jupyter Cell Tags
* Jupyter Keymap
* Jupyer Slide Show

## Configurando o banco de dados

Certifique-se de alterar as variáveis "con" e "con2" para corresponderem com as configurações do seu banco de dados. Onde está "usuario", "senha" e "nome_do_banco" deve ser substituído por suas configurações:

con = pg.connect(host = 'localhost', dbname = 'nome_do_banco', user = 'usuario', password = 'senha')

con2 = 'postgresql://usuario:senha@localhost/nome_do_banco'

## Modo de execução
* Para visualizar a página completa no navegador, utilize o comando 
``panel serve .\NOVO-CRUD.ipynb`` no terminal na pasta do projeto. Ao executar, o terminal irá mostrar a seguinte mensagem: "Bokeh app running at: *link*". No lugar onde link está escrito é onde está o endereço que a página do Panel está sendo executada, então basta copiá-la e acessar pelo navegador.

* Para executar no VSCode, basta abrir o arquivo Novo-CRUD.ipynb e clicar em "Run All" no canto superior da página. (NÃO é recomendável visualizar o projeto pelo VSCode, já que ele possui muito pouco espaço e isso impossibilita a visualização completa da tela do Panel)

## Lógica do código
* Conexão ao banco de dados feita utilizando o Psycopg2 e o SQLAlchemy.
* Pandas é usado para armazenar a query da consulta.
* Criação de widgets de caixa de texto e botões por meio do Panel.
* Os cadastros, edições e remoções são feitos utilizando o Psycopg2 e as consultas utilizando o Pandas.
* Além disso, são usadas funções secundárias para ajudar no tratamento de tipos para o envio de informações ao banco de dados.
* Para a visualização do projeto, são criadas fileiras e colunas de widgets do Panel

## Conclusão
O funcionamento de um banco de dados não se limita somente à sua criação, porque sua manutenção por meio de sistemas CRUD também é essencial para o funcionamento
de um sistemas. Essa manutenção envolve diversas bibliotecas e necessita de atenção em diversos detalhes para evitar a inserção de informações indevidas ao sistema.