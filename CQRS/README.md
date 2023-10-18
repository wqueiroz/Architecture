# CQRS - Command Query Responsibility Segregation
> Segregação de responsabilidade de consulta de comando (CQRS) é um padrão de design usado na arquitetura de software que separa as operações de leitura e gravação de um sistema. A ideia-chave por trás do CQRS é dividir um sistema em duas partes distintas: uma que lida com comandos (operações de gravação) e outra que lida com consultas (operações de leitura). Essa separação permite melhor dimensionamento, capacidade de manutenção e flexibilidade do sistema.

Em um sistema baseado em CQRS, o modelo de comando e o modelo de consulta atendem a propósitos distintos e são projetados para lidar com diferentes tipos de operações.

## Modelo de Comando
O modelo de comando é responsável por lidar com as operações de gravação no sistema. Isso inclui criar, atualizar e excluir dados.
Os comandos são normalmente representados como objetos que encapsulam as informações necessárias para executar uma ação específica, como por exemplo o id de um produto, seu título e o preço. Esses comandos são processados por manipuladores de comando, que contêm a lógica de negócios para validar e executar a ação.

Em muitos casos, o modelo de comando também gera e publica eventos de domínio para comunicar o resultado da operação a outras partes do sistema.

## Modelo de Consulta
O modelo de consulta é responsável por tratar as operações de leitura no sistema. Isso inclui recuperar dados, filtrá-los e projetá-los conforme necessário. Os modelos de consulta são otimizados para recuperação de dados eficiente e podem usar diferentes tecnologias de armazenamento de dados, como bancos de dados relacionais ou bancos de dados NoSQL, dependendo do caso de uso.

Os manipuladores de consulta são responsáveis por executar as consultas e retornar os dados necessários ao cliente.

## Sincronização
Em um sistema CQRS, os modelos de comando e consulta são separados, o que significa que podem utilizar diferentes mecanismos de armazenamento de dados e nem sempre são consistentes entre si. Para garantir que o modelo de consulta seja atualizado quando forem feitas alterações no modelo de comando, a sincronização é necessária. Isso geralmente é alcançado por meio de consistência eventual, em que o sistema pode ser temporariamente inconsistente, mas eventualmente atinge um estado consistente. Uma abordagem comum para obter consistência eventual é usar eventos de domínio gerados pelo modelo de comando para atualizar o modelo de consulta de forma assíncrona.

## CQRS e Microsserviços
O CQRS é particularmente adequado para arquiteturas de microsserviços porque promove a separação de preocupações e permite o dimensionamento independente. Ao dividir um sistema em microsserviços menores e focados, cada um lidando com comandos ou consultas, você pode obter os seguintes benefícios:

* **Dimensionamento independente**: cada microsserviço pode ser dimensionado de forma independente, permitindo alocar recursos de forma eficiente com base nas necessidades específicas de cada serviço.
* **Flexibilidade**: separar os modelos de comando e consulta em diferentes microsserviços permite escolher a pilha de tecnologia mais adequada para cada operação, incluindo mecanismos de armazenamento de dados e linguagens de programação.
* **Resiliência**: como cada microsserviço é independente, é menos provável que a falha de um serviço afete todo o sistema. Isso permite uma melhor tolerância a falhas e um tratamento de erros mais robusto.
* **Implantação** e manutenção mais fáceis: microsserviços menores e focados são mais fáceis de implantar, manter e atualizar. Isso facilita um processo de desenvolvimento mais ágil e entrega mais rápida de novos recursos.
Melhor suporte para arquiteturas orientadas a eventos: o CQRS naturalmente complementa as arquiteturas orientadas a eventos, que são comuns em microsserviços. O uso de eventos de domínio para comunicação entre microsserviços pode ajudar a manter a consistência eventual e promover um baixo acoplamento.

## Benefícios do CQRS:
* **Escalabilidade**: Como as operações de leitura e gravação são separadas, você pode escalá-las de forma independente, otimizando recursos para cada parte do sistema.
* **Manutenibilidade**: a separação de preocupações leva a um código mais limpo e focado, facilitando a manutenção e a atualização.
* **Flexibilidade**: o CQRS permite usar diferentes modelos de dados e tecnologias de armazenamento de dados para operações de leitura e gravação, permitindo escolher a melhor abordagem para cada operação.
* **Desempenho aprimorado**: ao segregar comandos e consultas, você pode otimizar cada parte independentemente, o que pode melhorar o desempenho geral do sistema.
Melhor suporte para arquiteturas orientadas a eventos: CQRS é freqüentemente usado em combinação com Event Sourcing, permitindo que você armazene eventos conforme eles acontecem e reproduza-os para reconstruir o estado atual do sistema.

## Exemplos da vida real
* **Plataformas de comércio eletrônico**: o CQRS pode ser usado para separar o processamento de pedidos (gravação) das pesquisas e navegação (leitura) de produtos, permitindo melhor escalabilidade e desempenho.
* **Plataformas de mídia social**: separando a postagem de conteúdo (write) da recuperação de feeds do usuário e cronogramas (leitura) pode ajudar a gerenciar grandes quantidades de dados e melhorar a capacidade de resposta.

# Melhores práticas para implementar o CQRS
* **Comece simples**: não introduza o CQRS em um sistema, a menos que haja uma necessidade clara para isso. Comece com uma arquitetura simples e monolítica e refatore para CQRS quando os benefícios superarem a complexidade.
* **Selecione o nível correto de granularidade**: o CQRS deve ser aplicado no nível de um agregado no Domain-Driven Design (DDD), não no nível de entidades individuais ou de todo o sistema.
* **Modelos de comando e consulta separados**: crie modelos distintos para comandos e consultas para manter uma separação clara de preocupações.
Use consistência eventual: em muitos casos, os sistemas CQRS podem ser projetados para funcionar com consistência eventual, permitindo melhor desempenho e escalabilidade.
* **Combine com Event Sourcing**: CQRS funciona bem com Event Sourcing, que fornece uma trilha de auditoria e permite a fácil reconstrução do estado do sistema.
  
## Potenciais armadilhas a serem evitadas
* **Complicar demais o sistema**: aplicar o CQRS sem uma necessidade clara pode introduzir uma complexidade desnecessária.
* **Tratar o CQRS como uma solução de tamanho único**: o CQRS não é adequado para todas as aplicações ou todas as partes de um sistema. Deve ser usado de forma seletiva e ponderada.
* **Ignorando a curva de aprendizado**: Os desenvolvedores novos no CQRS podem precisar de tempo para se familiarizar com o padrão e suas implicações.
  
## Recursos e ferramentas para aprender CQRS
Livros
* “Implementando o Design Orientado a Domínio” por Vaughn Vernon
* “Padrões, Princípios e Práticas de Design Orientado a Domínio” por Scott Millett e Nick Tune

## Recursos online
* Artigo de Martin Fowler sobre CQRS: https://martinfowler.com/bliki/CQRS.html
* Guia da Microsoft para CQRS: https://docs.microsoft.com/en-us/azure/architecture/patterns/cqrs

## Estruturas e bibliotecas
* Axon Framework (Java): https://axoniq.io/product-overview/axon-framework
* NServiceBus (C#): https://docs.particular.net/nservicebus/
* Eventuate (Java, Scala): http://eventuate.io/

> Em resumo, o padrão CQRS divide um sistema em modelos de comando e consulta, permitindo melhor separação de interesses, escalabilidade e flexibilidade. A sincronização entre esses modelos é obtida por meio de consistência eventual, muitas vezes usando eventos de domínio. Quando aplicado a microsserviços, o CQRS promove dimensionamento independente, flexibilidade, resiliência e implantação mais fácil, tornando-o um padrão valioso para sistemas distribuídos modernos.
