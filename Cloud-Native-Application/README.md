# Cloud-Native Application

## Pilares nativos da nuvem

Há várias maneiras de criar uma arquitetura nativa da nuvem, mas o objetivo é sempre aumentar a velocidade de entrega de software e a confiabilidade do serviço e desenvolver a propriedade compartilhada entre as partes interessadas.
Ainda assim, os fundamentos das arquiteturas nativas da nuvem são baseados em cinco pilares principais: 

* Microsserviços: quase todas as arquiteturas de nuvem são baseadas em microsserviços, mas o principal benefício que elas oferecem é a composição, que detalha um aplicativo em uma coleção de serviços menores e leves que podem ser facilmente compostos e conectados entre si por meio de interfaces de programação do aplicativo (APIs). Por exemplo, um aplicativo de e-commerce pode ser composto por um serviço específico para o carrinho de compras, outro para pagamento e outro que se comunica com o back-end sobre o gerenciamento de inventário. A composição também permite que as equipes troquem e recomponham componentes para atender a novos requisitos de negócios sem interromper outra parte do aplicativo. 

* **Contêineres e orquestração**: os contêineres são componentes executáveis leves e que contêm todos os elementos necessários, incluindo o código-fonte e as dependências do app, para executar o código em qualquer ambiente. Os contêineres oferecem portabilidade de cargas de trabalho que aceitam códigos "criar uma vez, executar em qualquer lugar", facilitando o desenvolvimento e a implantação. Elas também ajudam a reduzir a chance de atrito entre linguagens, bibliotecas e frameworks, já que podem ser implantadas de maneira independente. Essa portabilidade e flexibilidade tornam os contêineres ideais para a criação de arquiteturas de microsserviços.   
**A orquestração de contêineres** também é essencial à medida que o número de microsserviços aumenta para ajudar a gerenciar contêineres e executá-los sem problemas como um aplicativo. Uma plataforma de orquestração de contêineres, como o Kubernetes, fornece supervisão e controle de onde e como os contêineres são executados, repara quaisquer falhas e balanceia a carga entre os contêineres.

* **DevOps**: o desenvolvimento de aplicativos nativos da nuvem exige a mudança para uma metodologia de entrega ágil, como DevOps , em que os desenvolvedores e as equipes de operações de TI colaboram para automatizar processos de entrega de infraestrutura e software. O DevOps permite que as equipes de desenvolvimento e operações se comuniquem de maneira mais próxima e se unam em uma finalidade compartilhada, criando uma cultura e um ambiente em que é possível criar, testar e lançar aplicativos com mais rapidez. 

* **Integração contínua e entrega contínua (CI/CD)**: a automação pode consertar, escalonar e implantar sistemas muito mais rapidamente do que as pessoas. Os pipelines de CI/CD ajudam a automatizar a criação, teste e implantação de alterações de aplicativos sem a necessidade de programar inatividade ou aguardar uma janela de manutenção. A entrega contínua garante que as versões de software sejam mais confiáveis e menos arriscadas, permitindo que as equipes ofereçam novos serviços e recursos com mais rapidez e frequência.

## Benefícios nativos da nuvem

* **Inovação mais rápida**
> Serviços menores e com acoplamento flexível permitem que as equipes trabalhem e se desenvolvam de maneira autônoma. As abordagens nativas da nuvem aumentam a produtividade e a velocidade do desenvolvedor, facilitando a inovação. 
* **Versões confiáveis**
> Com arquiteturas nativas da nuvem, os desenvolvedores podem criar, testar e implantar rapidamente serviços novos e atuais. Isso permite lançar produtos e serviços com mais rapidez e reduz o risco de implantações. 
* **Escalonabilidade** 
> As arquiteturas nativas da nuvem empregam automação de infraestrutura, o que ajuda a eliminar o tempo de inatividade devido a um erro humano. É possível equilibrar a carga com base na demanda, permitindo otimizar o custo e o desempenho. 
* **Custos mais baixos**
> Um processo de entrega de software simplificado reduz os custos de entrega de novos recursos e atualizações. Os aplicativos nativos da nuvem também permitem compartilhar recursos e consumo sob demanda, reduzindo significativamente os custos operacionais. 
* **Maior disponibilidade**
> As arquiteturas nativas da nuvem oferecem alta disponibilidade e confiabilidade porque reduzem a complexidade operacional, simplificam as alterações de configuração e oferecem escalonamento automático e autocorreção. 
* **Portabilidade**
> Os aplicativos nativos da nuvem são projetados para serem executados em praticamente qualquer lugar, facilitando a migração deles de um ambiente a outro sem fazer alterações em todo o aplicativo.
* **Mais segurança**
> Os aplicativos nativos da nuvem ajudam a reduzir a área de superfície de ataque e facilitam a detecção e resposta a ataques ou novas vulnerabilidades. Eles também são muito mais fáceis de corrigir e atualizar à medida que seguem a implantação e o gerenciamento padronizados. 
* **Compliance aprimorado**
> É muito mais fácil e barato de implementar e demonstrar conformidade com os aplicativos nativos da nuvem, já que a maioria dos controles de segurança de dados é implementada no nível da plataforma. Os provedores de nuvem também mantêm compliance com frameworks de gerenciamento de riscos, facilitando o cumprimento dos padrões de conformidade com controles residuais. 

## Princípios de desenvolvimentos
Seja criando um novo aplicativo nativo da nuvem ou modernizando um aplicativo existente, os desenvolvedores aderem a um conjunto consistente de princípios:

* **Siga a abordagem arquitetônica de microsserviços**: divida os aplicativos em serviços de função única conhecidos como microsserviços. Os microsserviços são fracamente acoplados, mas permanecem independentes, permitindo a melhoria incremental, automatizada e contínua de um aplicativo sem causar tempo de inatividade.

* **Confie em contêineres para máxima flexibilidade e escalabilidade**: os contêineres empacotam software com todo o seu código e dependências em um só lugar, permitindo que o software seja executado em qualquer lugar. Isso permite máxima flexibilidade e portabilidade em um ambiente multicloud. Os contêineres também permitem aumento ou redução rápida com políticas de orquestração do Kubernetes definidas pelo usuário.

* **Adote métodos ágeis**: os métodos ágeis aceleram o processo de criação e melhoria. Os desenvolvedores podem iterar atualizações rapidamente com base no feedback do usuário, permitindo que a versão funcional do aplicativo corresponda o mais próximo possível às expectativas do usuário final.
