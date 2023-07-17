# REST API Best Practices

<details>
  <summary>Introdução</summary>
</br>

  **Representational State Transfer**, abreviado como <b>REST</b>, não é uma tecnologia, uma biblioteca, e nem tampouco uma arquitetura, mas sim um modelo a ser utilizado para se projetar arquiteturas de software distribuído, baseadas em comunicação via rede.
<b>REST</b> é um dos modelos de arquitetura que foi descrito por Roy Fielding, um dos principais criadores do protocolo HTTP, em sua tese de doutorado e que foi adotado como o modelo a ser utilizado na evolução da arquitetura do protocolo HTTP.
Muitos desenvolvedores perceberam que também poderiam utilizar o modelo <b>REST</b> para a implementação de Web Services, com o objetivo de se integrar aplicações pela Web, e passaram a utilizá-lo como uma alternativa ao SOAP.
<b>REST</b> na verdade pode ser considerado como um conjunto de princípios, que quando aplicados de maneira correta em uma aplicação, a beneficia com a arquitetura e padrões da própria Web.

## REST e RESTful
Uma API pode ser considerada RESTful quando ela utiliza em sua implementação o conceito arquitetural <b>REST</b>.
<b>REST</b> é algo abstrato, como um modelo arquitetural, enquanto que <b>RESTful</b> é algo mais concreto, como a implementação deste modelo em alguma API. Então, para criar uma API <b>RESTful</b> é preciso conhecer a arquitetura <b>REST</b> e também aplicá-la corretamente.
<b>REST</b> requer que os cinco princípios fundamentais definidos por Fielding sejam rigidamente seguidos (o sexto não é fundamental para caracterizar uma aplicação como <b>REST</b>, mas no contexto atual de onde temos uma adoção cada vez maior de microsserviços tem sido primordial).

## Boas práticas gerais

* Dê a todas as coisas um Identificador</br>
Utilizamos "coisas" ao invés do termo formalmente correto "recurso" porque esse é um principio simples que não deveria ser escondido por trás da terminologia. 
Se você pensar sobre os sistemas que as pessoas constroem, há usualmente um conjunto de abstrações chave que merecem ser identificadas. 
Tudo o que deveria ser identificado deveria obviamente ter um ID. Na Web, há um conceito unificado para IDs: "A URI". URIs compõe um namespace global,e utilizando URIs para identificar seus recursos chave significa ter um ID único e global

* Vincule as coisas</br>
Use URIs para identificar tudo o que precisar ser identificado, especifique todos os recursos de "alto nível" que seu aplicativo oferece, se eles representam itens individuais, conjuntos de itens, objetos virtuais e físicos, ou resultados de computação.
o	Utilize métodos padronizados
Para que clientes possam interagir com seus recursos, eles devem implementar o protocolo de aplicação padrão (HTTP) corretamente, isto é, utilizar os métodos padrão: GET, PUT, POST e DELETE.

* Recursos com múltiplas representações</br>
Ofereça diversos formatos dos recursos para diferentes necessidades.

* Comunique sem estado (STATELESS)</br>
Requisições feitas por um cliente a um serviço REST devem conter todas as informações necessárias para que o servidor as interprete e as execute corretamente. Clientes não devem depender de dados previamente armazenados no servidor para processar uma requisição. Qualquer informação de estado deve ser mantida pelo cliente e não pelo servidor. Isso reduz a necessidade de grandes quantidades de recursos físicos, como memória e disco, e também melhora a escalabilidade de um serviço REST.</br>
É justamente por essa característica que a Web consegue ter uma escalabilidade praticamente infinita, pois ela não precisa manter as informações de estado de cada um dos clientes.</br>
Esse é um dos princípios mais difíceis de ser aplicado em um serviço REST, pois é muito comum que aplicações mantenham estado entre requisições de clientes. Um exemplo dessa situação acontece quando precisamos armazenar os dados dos usuários que estão autenticados na aplicação.


</details>

## Mantenha a consistência de padrões nas nomenclaturas
Os princípios do REST diz que todo recurso deve possuir uma identificação única. Essa identificação serve para que a aplicação consiga diferenciar qual dos recursos deve ser manipulado em uma determinada solicitação.
A identificação do recurso deve ser feita utilizando-se o conceito de URI (Uniform Resource Identifier), que é um dos padrões utilizados pela Web. 
Alguns exemplos de URIs:
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}[?{parâmetro}&{parâmetro}]
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}/{id}
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}/{id}/{id}
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}/{id}/{sub-recurso}
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}/{id}/{sub-recurso}[?{parâmetro}&{parâmetro}]
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}/{id}/{sub-recurso}/{id-subrecurso}

