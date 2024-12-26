## Motivação
Esse artigo foi escrito com o intuito principal de compartilhar conhecimento e, principalmente, ensinar quem está começando agora. Visto que, este é um artigo de estudante para estudantes, apesar de eu já estudar programação há alguns anos.

Com o avanço da tecnologia e da internet do século passado para o período contemporâneo, fomos obrigados a desenvolver ferramentas que nos permitissem criar aplicações com mais facilidade sem ter a necessidade da robustez.

## Introdução
Já ouviu falar no termo *REST API*? Bem, REST API nada mais é do que uma API que segues os pilares essenciais do design da arquitetura REST. E o que é REST? REST é um sigla para *representational state transfer* que traduzindo fica *transferência de estado representacional*, que são basicamente um conjunto de regras e protocolos que devem ser considerados para o desenvolvimento de uma REST API.

### Noções básicos
Antes de iniciar as explicações, precisamos primeiro entender alguns conceitos e ideias pra somente depois partir pra explicações mais detalhadas e técnicas, pode ser? Então vamos lá.

#### URI
URI é uma sigla para *Uniform Resource Identifier* ou *Identificador Uniforme de Recursos* que é simplesmente uma sintaxe que atribui a cada documento web (HTML) um endereço único.

##### Estrutura
Sua estrutura é muito simples e é composta de 2 elementos:
1. ***URL (Uniform Resource Locator)***
Localizador de recurso
2. ***URN (Uniform Resource Name)***
Nome do recurso

`https://www.google.com/imghp?hl=pt-BR&authuser=0&ogbl`

- URL: "https://www.google.com/imghp"
- URN: "?hl=pt-BR&authuser=0&ogbl"

#### HTTP
HTTP é uma sigla para *HyperText Transfer Protocol* ou *Protocolo de Transferência de Hipertexto*. Esse eu sei que você já viu ou ouviu falar em algum lugar. Talvez você tenha visto naqueles links de compartilhamento ou até mesmo quando você vai digitar o site no seu navegador, certo? Então, o HTTP é um protocolo usado para a transmissão (envio) de documentos de hipermídia, como é o caso do HTML.
#### HTML
HTML é uma sigla para *HyperText Markup Language* ou *Linguagem de marcação de hipertexto*. Acredito que você também certamente ouviu falar! O HTML nada mais é do que um documento que é a página web, simplesmente. Em outras palavras, o HTML é o documento de construção de páginas da web.

## O que é uma API?
Bem, de forma resumida, uma API nada mais é do que uma ferramenta que segue um conjunto de protocolos e viabiliza integrações através de uma interface que permite essa integração. Mas o que exatamente significa a palavra? "API" é um acrônimo para *Application Programming Interface* e sua tradução literal é *Interface de Programação de Aplicação*. Além disso, uma API comumente oferece um conjunto de interfaces 
### Quais suas finalidades?
Uma das suas principais finalidades é viabilizar a **comunicação entre serviços** e esse processo acontece através do esquema de requisições e respostas. Ou seja, uma das principais funções da API é permitir que duas extremidades, ou melhor, dois serviços realizem uma **troca ou envio de informações** e esse processo acontece justamente por meio de requisições e respostas ou ***requests*** e ***responses***. E esse tipo de API é conhecida como **Web API**

![Representação simples de requisições e respostas](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/o-que-e-rest-api/imgs/request-and-response.png)

Além disso, outra finalidade finalidade que uma API pode ter é de desenvolvimento, ou seja, a API fornece interfaces para o programador desenvolvedor aplicações. Um bom exemplo é o ***HTML DOM API***, que fornece ao programador as interfaces necessários para a manipulações de elementos no documento HTML ou o # ***Web Storage API***, que permite que o programador armazene dados com o navegador através do esquema de chave-valor.

## Arquitetura Web
O estudioso *Roy Fielding*, preocupado com a escalabilidade da web, reconheceu que esta é governada por um conjunto de **restrições-chave**. Dito isso, ele e outros estudiosos propuseram uma abordagem pragmática: satisfazer uniformemente todas as suas restrições. Para isso, eles agruparam 6 categorias. Que são:
1. **Client-server**;
2. **Uniform interface**;
3. **Layered system**;
4. **Cache**;
5. **Stateless**;
6. **Code-on-demand**

### Client-server
> "A separação de preocupações é o tema central das restrições cliente-servidor da Web - **(Mark Massé, 2012, p. 21)**

De forma simplificada, a web como conhecemos é dividida da seguinte maneira: ***clientes*** e ***servidores***. De um lado temos o **usuário ou programador** (cliente) e do outro o **fornecedor de recursos** (servidor).
Essa comunicação entre cliente e servidor acontece por meio de **requisições e respostas**.
O cliente faz a requisição, o servidor recebe essa requisição e trabalha em cima dela, podendo atuar como um intermediador de um banco de dados, por exemplo, ou também simplesmente devolvendo informações relevantes.

![Representação de requisições e respostas com um servidor intermediando o cliente e o DB](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/o-que-e-rest-api/imgs/response-and-request-db.png)

A graça disso tudo tá em simplesmente não saber o que acontece lá do outro lado quando a informação chega, o que importa mesmo é a resposta.

### Uniform interface
As interações nos componentes da internet dependem da ***uniformidade de suas interfaces*** e se algum de seus componentes se desviar dos padrões, o sistema de comunicação certamente falhará. Portanto, estes componente interoperam dentro de 4 restrições que foram identificadas por Fielding:
1. ***Identificação de recursos***;
2. ***Manipulação de recursos por meio de representações***;
3. ***Mensagens auto descritivas***;
4. ***HATEOAS (Hypermedia as the engine of application state)***

#### Identificação de recursos
Cada item na internet é um recurso e pode ser **endereçado com uma URI**, ou seja, **recursos individuais são e devem ser identificados usando URIs**. Então, os recursos precisam ser ***separados de forma conceitual***.
#### Manipulação de recursos por meio de representações
Os clientes manipulam as representações de recursos, permitindo várias **maneiras de interações**. Por exemplo, na resposta de uma requisição de de uma API, sua resposta pode retornar um *JSON* ou *XML*.
#### Mensagens auto descritivas
O **estado desejado do recurso** pode ser representado **dentro da mensagem de solicitação** ou da **resposta do servidor**. Além disso, é importante que uma mensagem HTTP forneça um cabeçalho (*header*) com metadados (*metadatas*) com informações de estado do recurso, formato, tamanho da mensagem, sua mensagem em si e afins. Segue um exemplo abaixo:
```
GET /index.html HTTP/1.1

Host: www.exemplo.com

User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3

Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8

Accept-Language: pt-BR,pt;q=0.8,en-US;q=0.6,en;q=0.4

Referer: http://www.google.com

Cookie: PHPSESSID=1234567890
```
#### HATEOAS
A sigla indica *Hypermedia as the engine of application state* ou *Hipermídia como motor do estado da aplicação*. A representação de estado de um recurso inclui links para recursos relacionados permitindo que os clientes **descubram** dinamicamente como navegar e interagir com recursos disponíveis.

Exemplo:
`example.com/date/yyyy/mm/dd`
É intuitivo que o usuário deve colocar o ano, mês e o dia pra acessar diretórios e, consequentemente, acessar outros diretórios também de forma intuitiva.

### Sistema em camadas
As restrições do sistema em camadas permitem que **intermediários de redes** sejam implantados de forma visível através de uma interface e o seu propósito é justamente interceptar a **comunicação cliente-servidor**. Por exemplo: *proxies*, *gateways*, *balanceadores de carga*, *firewalls* e afins.

![Representação simples de requisições e respostas](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/o-que-e-rest-api/imgs/system-layered.png)

#### Cache
As restrições de cachê define a "**cacheabilidade**" dos dados de cada resposta, isso é, é determinado o **custo daquela mensagem**. Sendo assim, é importante ter em mente noções de *latência*, *disponibilidade* e *confiabilidade*.

#### Stateless
A restrição sem estado define que o servidor web não é **necessário memorizar o estado da aplicação** dos seus clientes, logo, cada cliente deve incluir o contexto da informação a cada interação com um servidor web.

#### Code-on-demand
Code-on-demand ou código sob demanda é a **transferência temporária de programas executáveis** - *scripts* ou *plug-ins* - para os clientes. Esse processo permite um acoplamento tecnológico entre servidores web e seus clientes. Um exemplo de plug-in que segue esse modelo de transferência de programas executáveis é o *Adobe Flash*.

![Logo do Adobe Flash](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/o-que-e-rest-api/imgs/adobe-flash-logo.jpg)

### Tá... E o que é REST API?
Bem, *REST API* nada mais é do que uma *API* que o **estilo de arquitetura REST**. Ter uma REST API no seu projeto ou serviço faz dela ***RESTful***. Logo, é correto dizer que esse serviço possui uma série de recursos interligados de forma organizada a seguir um modelo de disposição de elementos.

> "APIs REST bem projetadas podem atrair desenvolvedores de clientes para usar serviços web. No mercado aberto de hoje, onde serviços web rivais estão competindo por atenção, um design de API REST esteticamente agradável é um recurso essencial" - **(Mark Massé, 2012, p. 24)**

### Analisando as entranhas de requisições e respostas
#### Verbos/métodos
Requisições que definem ***padrões de comunicação*** entre um servidor e um cliente.
- **GET**: solicita recurso(s);
- **POST**: adiciona recurso(s);
- **PUT**: atualiza determinado(s) recurso(s);
- **DELETE**: remove recurso(s)

#### Códigos de status
- **200 Ok**: requisição bem sucedida;
- **201 Created**: novo(s) recurso(s) criado(s) com sucesso;
- **204 No Content**: recurso(s) atualizado(s) com sucesso;
- **400 Bad Request**: a requisição foi mal elaborada;
- **401 Unauthorized**: login inválido pois contém credenciais inválidas;
- **403 Forbidden**: recurso não autorizado;
- **404 Not Found**: recurso(s) não encontrado(s);
- **405 Method Not Allowed**: o servidor não oferece resposta para esse tipo de método;
- **500 Internal Server Error**: erro interno do servidor - como um bug ou um erro no código, por exemplo;
- **503 Service Unavailable**: o servidor teve muitas requisições e está fora de ar temporariamente - não necessariamente precisa ser um ataque de negação de serviço (DDoS)

## Referências
1. [Significados | Interface: o que é e significado (sistema ou software)](https://www.significados.com.br/interface/)
2. [Alura | API: entenda o que é, para quê serve e qual a sua importância | Alura](https://www.alura.com.br/artigos/api)
3. [MDN | JSON - JavaScript ](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/JSON)
4. [TreinaWeb | O que é HATEOAS?](https://www.treinaweb.com.br/blog/o-que-e-hateoas/)
5. [Lunnary | O que é: HTTP Request Header (Cabeçalho de Requisição HTTP)](https://lunnary.com.br/glossario/o-que-e-http-request-header-cabecalho-de-requisicao-http/)
6. [Devmedia | HTTP: Headers](https://www.devmedia.com.br/http-headers/41219)
7. [Devmedia | HTTP: Verbos](https://www.devmedia.com.br/http-verbos/41224)
8. [MDN | Métodos de requisição HTTP - HTTP](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Methods)
9. [Bright | Getting Started With HTTP Verbs](https://faun.pub/getting-started-with-http-verbs-a4050ec4d6ef)
10. [Hostinger | Erro 403 Forbidden: O Que Significa e Como Corrigir](https://www.hostinger.com.br/tutoriais/o-que-significa-erro-403)
11. [MDN | 405 Method Not Allowed - HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/405)
12. [MDN | 500 Internal Server Error - HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/500)
13. [Hostinger | HTTP Erro 500: Aprenda a Corrigir o Erro Interno do Servidor](https://www.hostinger.com.br/tutoriais/como-corrigir-o-erro-interno-500-servidor-no-wordpress#O_que_e_o_Erro_500)
14. [Kinsta | O que é um Endpoint de API?](https://kinsta.com/pt/base-de-conhecimento/endpoint-api/)
15. [Stack Overflow | Qual a diferença entre endpoint e API?](https://pt.stackoverflow.com/questions/86399/qual-a-diferen%C3%A7a-entre-endpoint-e-api)
16. [TechTudo | O que é API e para que serve? Cinco perguntas e respostas](https://www.techtudo.com.br/listas/2020/06/o-que-e-api-e-para-que-serve-cinco-perguntas-e-respostas.ghtml)
17. [MDN | The HTML DOM API - Web APIs](https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API)
18. [MDN | API de Armazenamento na Web - APIs da Web](https://developer.mozilla.org/pt-BR/docs/Web/API/Web_Storage_API)
19. [MDN | HTTP](https://developer.mozilla.org/pt-BR/docs/Web/HTTP)
20. [MDN | HTML: HyperText Markup Language](https://developer.mozilla.org/en-US/docs/Web/HTML)
21. [Red Hat | O que é uma API REST?](https://www.redhat.com/pt-br/topics/api/what-is-a-rest-api)
22. [Controle.net | Cliente-Servidor, uma estrutura lógica para a computação centralizada](https://www.controle.net/faq/cliente-servidor-uma-estrutura-para-a-computacao-centralizada)
23. [Stack Overflow | REST - What exactly is meant by Uniform Interface?](https://stackoverflow.com/questions/25172600/rest-what-exactly-is-meant-by-uniform-interface)
24. [GeeksforGeeks | REST API Architectural Constraints](https://www.geeksforgeeks.org/rest-api-architectural-constraints/)
25. [Oracle | REST API Guide](https://docs.oracle.com/en/cloud/saas/warehouse-management/22c/owmre/optional-trailing-slashes.html)
26. [Stack Overflow | REST - What exactly is meant by Uniform Interface?](https://stackoverflow.com/questions/25172600/rest-what-exactly-is-meant-by-uniform-interface)
27. Oluwatosin, H. S. (2014). Client-server model. IOSR Journal of Computer Engineering, 16(1), 67-71.
28. Mark Massé. REST API Design Rulebook. United States of America: O’Reilly Media, 2012. 114 p.
29. Leonard Richardson, Mike Amundsen. RESTful Web APIs. United States of America: O’Reilly Media, 2012. 404 p.
