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

## Princípios do REST 
*	<b>Client-Server</b> - Separar as responsabilidade do frontend do backend. Esse é um conceito bem comum. Separar o front do back há ganhos significativos em testes, escalabilidade com reflexos até na organização dos times dentro da empresa.
*	<b>Stateless</b> - O servidor não mantém estado. Cada solicitação do client deve conter informações necessárias para o server entender a solicitação. O estado da sessão é mantido inteiramente no client.
*	<b>Cacheable</b> - A resposta de uma solicitação deve implicitamente ou explicitamente informar se o dado pode ser mantido em cache ou não.
O cache deve ser mantido e gerenciado pelo Client.
* <b>Uniform interface</b> - Este principio é definido por quatro restrições: 
  *	Identificar os recursos (URI)
  *	Manipular recursos através de representações (Verbos HTTP).
  *	Mensagens auto-descritivas, cada requisição deve conter informações suficientes para o server processar a informação.
  *	HATEOAS - Hypermedia As The Engine Of Application State. 

## Medindo a Maturidade de sua API - Richardson Maturity Model
Fontes: https://martinfowler.com/articles/richardsonMaturityModel.html

### O que é esse modelo?
É um modelo criado por Leonard Richardson que quebra os elementos de uma API REST em 3 níveis. Sendo assim para você atingir o REST "real" você teria que alcançar o nível 3.

### Devemos tentar alcançar o nível mais alto de maturidade sempre?
Você deve fazer o que faz sentido para sua aplicação. 

Uma breve explicação de cada nível.

* Nível 0: HTTP
Você usa HTTP como forma de comunicação sem qualquer critério para a utilização de verbos, ou de rotas.

* Nível 1: HTTP + Recursos
Sua API está exposta (roteada) seguindo o modelo de recursos. Como /users/ para listar todos os usuários e /users/123/ para obter um usuário especifico.

* Nível 2: HTTP + Recursos + Verbos
Os verbos HTTP são usados de forma semântica na sua API. GET para leitura, POST para inserir, PUT para substituir um registro, DELETE para excluir...

* Nível 3: HTTP + Recursos + Verbos + HATEOAS
A sua API deve retornar uma lista de recursos (rotas) com tudo o que é possível fazer a partir da chamada original.

>GET /products/123 </br>
>{                 </br>
>  "id": 123,</br>
>  "name": "Orange"</br>
>  "links": [  </br>
>       {"rel": "Suppliers", "href": "/suppliers/?product=123"} </br>
>  ] </br>
>} </br>

</details>

## Mantenha a consistência de padrões nas nomenclaturas
Os princípios do REST diz que todo recurso deve possuir uma identificação única. Essa identificação serve para que a aplicação consiga diferenciar qual dos recursos deve ser manipulado em uma determinada solicitação.
A identificação do recurso deve ser feita utilizando-se o conceito de URI (Uniform Resource Identifier), que é um dos padrões utilizados pela Web. 
Alguns exemplos de URIs:
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso} </br>
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}[?{parâmetro}&{parâmetro}] </br>
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}/{id} </br>
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}/{id}/{id} </br>
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}/{id}/{sub-recurso} </br>
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}/{id}/{sub-recurso}[?{parâmetro}&{parâmetro}] </br>
>https://{servidor-rest.com.br}/{app-contexto}/{versão-api}/{recurso}/{id}/{sub-recurso}/{id-subrecurso} </br>

