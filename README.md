<img src="https://github.com/castelom/cinefilo/blob/master/img/Cinefilo_logo.PNG" alt="cinefilo logo" title="cinefilo" align="right" height="60" />

# Cinéfilo 

Exemplo de aplicação microserviço com .NetCore.

## Sobre Este Projeto
Este projeto tem como principal objetivo servir como um guia para desenvolvedores .Net. Esta documentação servirá como um tutorial apresentando as principais decisões e implementações do projeto, assim como, explicando e discutindo as tecnologias e padrões utilizadas. O objetivo do criador desse projeto é auxiliar desenvolvedores .Net menos experientes na criação de portfólios e resolução de desafios para vagas de emprego. 

## Ideia Geral
O Cinéfilo é uma aplicação web baseada em microserviços que visa auxiliar os amantes do cinema, mostrando sessões, filmes, preço e promoções dos principais cinemas da cidade.

## Para quem é esse projeto
Esse projeto é direcionado a desenvolvedores .Net iniciantes e deve ser usado como um guia básico. Caso você seja um desenvolvedor mais experiente, este projeto pode ser usado como tutorial para alavancar membros menos experientes do seu time.  

## Pré-Requisitos
1. Conhecimento básico em .NET
2. Conhecimento básico em banco de dados relacional (SQL) 

## Considerações
Como os requisitos do projeto não são bem definidos e a aplicação tem carater eduacional, este projeto e documentação estará em constante mudança. A branch <a href="https://github.com/castelom/cinefilo/tree/master">
   Master
</a> contém o código mais recente. Qualquer outra branch é considerada temporária e pode ser excluída a qualquer momento. Cada microserviço possue sua própria documentação que pode ser consultada em:

| Microserviço | Status | Documentação |
| ------------- | ------------- | ------------- |
| MovieTheater-MS | In Progress | ---|
| Identity-MS | Not Started | ---|
| Movie-MS | Not Started | ---|
| Gateway| Not Started | ---|

*******
## Sumário
1. [Arquitetura](#architecture)
2. [Tecnologias](#technology)
3. [Por onde começar?](#begin)
*******
<div id='architecture'/>

## Arquitetura
A arquitetura proposta é baseada em microserviços com multiplos microserviços autonomos com diferentes abordagens de implementação e padrões utilizados (CRUD simples vs. DDD/CQRS patterns). A comunicação entre o cliente e os diferentes microserviços é feito através do protocolo HTTP passando por um BFF (Back-end for Front-end)  gateway. O projeto  suporta também comunicação assíncrona através de serviço de mensageria. A figura abaixo apresenta a arquitetura inicial do projeto.

<img src="https://github.com/castelom/cinefilo/blob/master/img/Cin%C3%A9filo%20Initial%20Architecture.png" alt="cinefilo architecture" title="cinefilo-architecture" align="center"/>

<div id='technology'/>

## Tecnologias Utilizadas
Este projeto usa as seguintes tecnologias:

| Tecnologia | Versão |
| ------------- | ------------- |
| .Net | 7 |
| EntityFramework | 8.0.1 |
| MySql | 8.1.0 |

<div id='begin'/>

## Por onde começar?
A única certeza que temos na vida, tirando a morte, é que a sua aplicação necessitará de uma estrutura para persistir os dados. Seja essa estrutura um banco de dados, um stream ou até mesmo um documento txt, provavelmente ela existirá e possuirá uma importância crucial no seu projeto. Portanto, sabendo desta certeza, quase absoluta, que cerca todas as aplicações reais, acredito que um bom passo inicial seja a comunicação com o banco de dados.

### O que é um banco de dados?
O banco de dados nada mais é que um sistema de computador que organiza e armazena dados de forma estruturada. Podem ser classificados em relacionais e não relacionais, não apresentarei essas definições mais deixarei links para quem desejar se aprofundar mais. Os bancos de dados nos quais já trabalhei estão na lista abaixo:

1. SQLServer.
2. PostgresSQL.
3. MySQL.
4. MongoDB (Não relacional)

O Banco de dados que usaremos nesse projeto será o MySQL. O motivo da escolhida desse banco é simplemente devido a memória afetiva. O primeiro projeto que fiz com integração com banco de dados na vida foi usando o MySQL, na época lembro que minha escolha inicial foi o SQLServer, mas meu antigo computador, que Deus o tenha, travava muito quando o Database Management System (DBMS) do SQLServer era executado. Então optei pelo o MySQL server que possuia um DBMS um pouco mais leve e em termos práticos não mudava muita coisa.

### Object Relacional Mapping (ORM)
