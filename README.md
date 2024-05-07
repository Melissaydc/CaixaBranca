# Teste de Caixa Branca

## Principais erros
- A variável nome não foi declarada antes de ser usada para armazenar o resultado da consulta.
- O código está vulnerável à injeção de SQL, pois os valores de login e senha são concatenados diretamente na consulta SQL. Isso pode ser resolvido usando consultas preparadas.
- O código tem blocos try-catch vazios, o que é uma má prática. As exceções devem ser registradas ou tratadas de alguma forma.
- A conexão com o banco de dados não está sendo fechada, o que pode levar a vazamentos de recursos.
- As credenciais do banco de dados estão hardcoded no código, o que é uma má prática de segurança. Elas devem ser armazenadas de forma segura e não no código-fonte.
- Não há verificação de null antes de tentar criar um Statement a partir da conexão. Se conectaBD() retornar null, isso resultará em uma exceção NullPointer.

## Perguntas
- A documentação foi descrita no código?
<br>Não, o código não possui comentários explicativos ou documentação, exceto por um comentário “//fim da class” no final.

- As variáveis e constantes possuem boa nomenclatura?
<br>As variáveis poderiam ter nomes mais descritivos para indicar claramente seu propósito.

- Existem legibilidade e organização no código?
<br>O código não está bem organizado. A indentação é inconsistente, tornando o código difícil de ler.

- Todos os nullpointers foram tratados?
<br>Não há tratamento explícito de null pointers. A conexão com o banco de dados pode retornar null, mas isso não é verificado antes de tentar criar um Statement.

- A arquitetura utilizada foi devidamente respeitada?
<br>Não é possível avaliar completamente a arquitetura com apenas este trecho de código, mas parece que as boas práticas não estão sendo seguidas (por exemplo, a senha está hard-coded).

- As conexões utilizadas foram fechadas?
<br>O código não mostra que as conexões com o banco de dados estão sendo fechadas.
