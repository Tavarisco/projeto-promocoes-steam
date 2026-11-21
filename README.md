# projeto-promocoes-steam

# projeto-promocoes-steam

## Sobre o projeto
Este projeto tem como objetivo colocar em prática alguns dos conhecimentos da faculdade e também de estudos sobre Python e Análise de dados com Pandas.
O projeto em si será criar uma lista com alguns títulos da Steam e tentar utilizar ML para prever promoções.

## Tecnologias
- Python
- Pandas
- Google Colab

## Status
Em andamento: montando a base de jogos.

## Diário de desenvolvimento

### 19/11/2026
Criação do projeto, da lista de jogos e das funções para inserir os dados.

### 21/11/2026
Primeiras tentativas de inserir novos dados dos jogos depois de carregar o arquivo CSV. Ocorreram alguns erros, pois os dados agora estavam em um DataFrame e a função inserir_dados_jogo() usava append(), que funciona em listas, mas não nas colunas de um DataFrame. Isso acabou me deixando confuso até então descobrir o que tinha acontecido. Pesquisando sobre, encontrei a função to_dict(), que transforma o DataFrame em dicionário, mas mesmo usando ainda assim não havia resolvido completamente o problema. Primeiro, porque eu usei o to_dict() em cada append(), e o dicionário era criado apenas na linha em que foi digitado. Depois, porque o to_dict() sem nada transformava cada coluna em outro dicionário, e não em uma lista. Então, pesquisando mais um pouco, achei um parâmetro que resolvia isso, to_dict(orient='list'), que resolveu esse problema, e a partir daí foi possível adicionar novos valores à lista de jogos. Depois disso, percebi que o nome e a data de lançamento do Sid Meier's Civilization VI tinham um \t no final, que é um TAB invisível que entrou junto quando colei o texto. Primeiro tentei corrigir o nome filtrando a linha, mas usei == em vez de =, e como o filtro pegava a linha inteira, todos os valores dela viraram False. Recuperei os dados e descobri o .loc, que permite apontar para a linha e a coluna ao mesmo tempo, e com ele corrigi o nome. Também tive problema com o apóstrofo do nome, que atrapalhava as aspas simples do Python, e resolvi usando aspas duplas. Para a data, usei o str.strip(), que tira espaços e TABs das pontas de todos os valores de uma coluna de uma vez.
