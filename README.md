<img src="https://github.com/castelom/cinefilo/blob/master/img/Cinefilo_logo.PNG" alt="cinefilo logo" title="cinefilo" align="right" height="60" />
# Cinéfilo  
Exemplo de aplicação microserviço com .NetCore.

## Sobre Este Projeto
Este projeto tem como principal objetivo servir como um guia para desenvolvedores .Net. Esta documentação servirá como um tutorial apresentando as principais decisões e implementações do projeto, assim como, explicando e discutindo as tecnologias e padrões utilizadas.

## Ideia Geral
O Cinéfilo é uma aplicação web baseada em microserviços que visa auxiliar os amantes do cinema, mostrando sessões, filmes, preço e promoções dos principais cinemas da cidade.

*******
## Sumário
1. [Arquitetura](#architecture)
2. 
*******
<div id='architecture'/>

## Arquitetura
A arquitetura proposta é baseada em microserviços com multiplos microserviços autonomos com diferentes abordagens de implementação e padrões utilizados (CRUD simples vs. DDD/CQRS patterns). A comunicação entre o cliente e os diferentes microserviços é feito através do protocolo HTTP passando por um BFF (Back-end for Front-end)  gateway suportando também comunicação assíncrona através de serviço de mensageria. A figura abaixo apresenta a arquitetura inicial do projeto.

<img src="https://github.com/castelom/cinefilo/blob/master/img/Cin%C3%A9filo%20Initial%20Architecture.png" alt="cinefilo architecture" title="cinefilo-architecture" align="center" height="60" />

<div id='technology'/>

## Tecnologias Utilizadas
Este projeto usa as seguintes tecnologias:

| Tecnologia | Versão |
| ------------- | ------------- |
| .Net | 7 |
| EntityFramework | 8.0.1 |
| MySql | 8.1.0 |

