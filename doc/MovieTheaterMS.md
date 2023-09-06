<img src="https://github.com/castelom/cinefilo/blob/master/img/Cinefilo_logo.PNG" alt="cinefilo logo" title="cinefilo" align="right" height="60" />

# MovieTheater Microservice

Esse microserviço tem como objetivo fornecer informações de sessões, horários, preço e promoções de cinemas da cidade de Fortaleza-CE Brasil. As informações salvas nesse sistema não são reais e são usadas apenas para representar um banco de dados de uma aplicação real.

## Por onde começar?
A única certeza que temos na vida, tirando a morte, é que a sua aplicação necessitará de uma estrutura para persistir os dados. Seja essa estrutura um banco de dados, um stream ou até mesmo um documento txt, provavelmente ela existirá e possuirá uma importância crucial no seu projeto. Portanto, sabendo desta certeza, quase absoluta, que cerca todas as aplicações reais, acredito que um bom passo inicial seja a comunicação com o banco de dados.

### O que é um banco de dados?
O banco de dados nada mais é que um sistema de computador que organiza e armazena dados de forma estruturada. Podem ser classificados em relacionais e não relacionais, não apresentarei essas definições mais deixarei links para quem desejar se aprofundar mais. Os bancos de dados nos quais já trabalhei estão na lista abaixo:

1. SQLServer.
2. PostgresSQL.
3. MySQL.
4. MongoDB (Não relacional)

O Banco de dados que usaremos nesse projeto será o MySQL. O motivo da escolha desse banco é simplemente devido a memória afetiva. O primeiro projeto que fiz com integração com banco de dados na vida foi usando o MySQL, na época lembro que minha escolha inicial foi o SQLServer, mas meu antigo computador, que Deus o tenha, travava muito quando o Database Management System (DBMS) do SQLServer era executado. Então optei pelo o MySQL server que possuia um DBMS um pouco mais leve e em termos práticos não mudava muita coisa.

### Object Relacional Mapping (ORM)
Não é segredo para ninguém que as informações em um banco de dados são salvas na forma de registros em tabelas, contudo, essas informações são representadas como objetos na nossa aplicação.
Desde modo, sabemos que é necessário converter os dados salvos nas tabelas em objetos da nossa aplicação e vice-versa. A técnica de ORM permite o mapeamento dos objetos com os dados que eles representam.
Existe vários frameworks que utilizam essa técnica e ajudam os desenvolvedores com o acesso ao banco de dados:

1. EntityFramework
2. Hibernate
3. NHibernate
4. Dapper (Considero como um ORM, mas essa afirmação é um pouquinho polêmica)

Os frameworks de ORM hoje em dia fazem muito mais do que apenas mapear objetos, algumas funcionalidades comums são:

1. Facilitar a conexão com o banco de dados.
2. Prover métodos para CRUD (Create, Read, Update, Delete) abstraindo o SQL.
3. Prover métodos para consultas abstraindo o SQL.

O ORM usado nesse projeto será o EntityFramework. Na minha visão, este ORM é o mais popular quando falamos de Aplicações .NET.

<div id='DER'/>

## Diagrama Entidade Relacionamento (DER)

O Diagrama Entidade Relacionamento (DER) é um modelo conceitual usado para descrever objetos de domínio de um sistema e sus relacionamentos, podemos utilizar o DER para ter uma visão inicial e abstrata da estrutura do banco de dados.
A figura abaixo apresenta o DER utilizado:

A modelagem poderia ser bem melhor, mas o objetivo dessa aplicação não é fazer uma modelagem complexa. Poderíamos incluir também muitas outras informações sobre os filmes, mas a ideia é utilizar um outro serviço para pegar os demais dados de filmes.

## Arquitetura do MovieTheater Microservice (MT-MS)

Para esse microserviço utilizaremos o padrão arquitetural Command Query Responsibility Segregation (CQRS). Este padrão arquitetural visa dividir operações de leitura e escrita em um database.
Vamos tentar explicar um pouquinho o motivo para utilizar o CQRS. Para isso vamos fazer um exercício usando nossa imaginação 🌈.

Imagine uma arquitetura tradicional como a figura abaixo:

Colocar figura

Neste tipo de arquitetura é bastante comum que o mesmo modelo de dados seja usado para operações de leitura e escrita no banco. Quando falamos de um CRUD simples essa arquitetura tradicional funciona muito bem.
Mas, imagine agora uma aplicação um pouco mais complexa. Vamos dizer que nossa aplicação possui diferente queries retornando DTOS com formatos diferentes, dependendo do número de queries fazer o mapeamento desses DTOs pode ser trabalhoso.
Validações e regras de negócios específicas para algumas situações de escrita é outro cenário comum em aplicações mais complexas, neste caso, nosso data model pode se tronar complexo e grande, possuindo diversas regras de validação que serão usadas aos poucos dependendo da operação.

Então, a pergunta que não quer calar: A aplicação MovieTheater-MS é complexa o bastante para justificar o uso do CQRS? Posso responder com toda a certeza que NÃO. Contudo, baseado nas aplicações que venho vendo e trabalhando nos últimos anos, acredito que é uma arquitetura que vem sendo muito utilizada
por isso achei legal colocar nesse MS.

##Framework MediatR
 MediatR é um framework que provê o padrão de projeto Mediator para sua aplicação. 

##Bibliografia
Pessoal, para quem quiser aprender um pouco mais afundo os assuntos discutidos nesse doc, estou recomendando os links abaixo:
<a href="https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs">
   CQRS
</a>
<a href="https://www.treinaweb.com.br/blog/mediator-pattern-com-mediatr-no-asp-net-core">
   MediatR
</a>
 