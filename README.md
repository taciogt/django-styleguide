# Django Styleguide
Style guide and best practices for a django project and others mvc web applications.

Guia de arquitetura e boas práticas para um projeto django e outras aplicações web no formato MVC


## Introdução
Este é um repositório criado para ser um modelo de arquitetura para uma aplicação web MVC. Será apresentado um conjunto de estruturas e boas práticas que se considera importantes para que um projeto possua as seguintes características:

- Padronização: Não importa o número de contribuidores do projeto, deve parecer que o código foi escrito por apenas um.
- Fácil de ser testado: Deve ser simples e pouco verboso para criar testes que cubram todos os cenários necessários.
- Escalável: À medida que o sistema e o uso feito dele crescem, simplesmente aumentar o número de instâncias que executam a aplicação pode não ser suficiente para atender a demanda. Outras abordagens devem ser possíveis de serem escolhidas sem grandes mudanças na aplicação (como a extração de um componente para um microsserviço externo).
- Simples para dar manutenção: Dar manutenção (ou criar novas funcionalidades) no sistema deve ser tão simples que um novo desenvolvedor não demore muito tempo para se familiarizar com a estrutura do sistema e encontrar a causa do bug ou o local para adicionar a melhoria.

## Diretrizes gerais da arquitetura proposta
 
Esta é uma aplicação web fictícia criada para servir de exemplo para as boas práticas aqui apresentadas. Com alguma adaptação, as diretrizes aqui apresentadas se aplicam a qualquer aplicação web que siga o formato MVC. A arquitetura apresentada aqui se baseia no modelo ou estilo de arquitetura conhecida em alguns meios como "arquitetura de microsserviços". A inspiração tem o intuito de projetar a aplicação web através de componentes independentemente substituíveis ou atualizáveis. 

Para fins de simplicidade, esses componentes serão criados todos na mesma aplicação, o que os diferencia da definição formal de microsserviço. Mas eles devem possuir caracteríscas que torne fácil sua futura extração para uma aplicação externa, que sirva como um microsserviço. Essas características são as seguintes: 

- Baixo acoplamento: Os microsserviços que compõe a aplicação devem ser uma interface de comunicação entre si o mais simples possível. O ideal é que qualquer um desses serviços possa ser extraído isoladamente para ser executado em uma aplicação independente.
- Alta coesão: Cada microsserviço deve possuir um conjunto de responsabilidades bem definido (e idealmente não muito extenso).