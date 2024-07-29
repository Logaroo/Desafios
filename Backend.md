# Dev. Back-End

Sua tarefa é construir uma API e banco de dados para a aplicação CMS (Content Management System). A aplicação é um simples repositório para gerenciar postagens com seus respectivos titulos, autores, conteúdos e tags. Utilize um repositório Git (público, de preferência) para versionamento e disponibilização do código.

A aplicação pode ser construída utilizando [laravel](https://laravel.com) (10 ou **superior**), utilizando SGBD de sua preferência (MongoDB, Mysql, postgreSql, MSQL, SQLite).

A API deverá ser documentada utilizando o formato [API Blueprint](https://apiblueprint.org/), [Swagger](https://swagger.io/docs/specification/basic-structure/) ou algum gerador integrado ao código.

## O que será avaliado

Queremos avaliar sua capacidade de desenvolver e documentar um back-end para uma aplicação. Serão avaliados:

-   Código bem escrito e limpo;
-   Quais ferramentas foram usadas, como e porquê, além do seu conhecimento das mesmas;
-   Seu conhecimento em banco de dados, requisições HTTP, APIs REST, etc;
-   Sua capacidade de se comprometer com o que foi fornecido;
-   Sua capacidade de documentação da sua parte da aplicação.

## O mínimo necessário

-   Uma aplicação contendo uma API real simples, sem autenticação, que atenda os requisitos descritos abaixo, fazendo requisições à um banco de dados para persistência;
-   [README.md](http://README.md) contendo informações básicas do projeto e como executá-lo;
-   [API Blueprint](https://apiblueprint.org/) ou [Swagger](https://swagger.io/docs/specification/basic-structure/) da aplicação.
-   **Classes para Requests**;
-   **Classes para Response**;
-   **Testes**;
-   **Autenticação e autorização** (**OAuth, JWT ou outro**);
-   Migrations ou script para configuração do banco de dados utilizado;

## Bônus

Os seguintes itens **não são obrigatórios**, adicione um ou mais e darão mais valor ao seu trabalho (os em negrito são mais significativos para nós e serão considerados um diferencial)

-   Uso de ferramentas externas que facilitem o seu trabalho (todas precisam ser descritas no README.md);
-   Cuidados especiais com otimização, padrões, entre outros;
-   Conteinerização da aplicação;
-   **Trait para Requests**;
-   **Trait para Response**;
-   **Repository Patern**;
-   Contracts;
-   **Intarfaces**;
-   **Dependency Injection**;
-   **Pipelines de CI/CD (GitLab, CircleCI, TravisCI, etc);**
-   **Deploy em ambientes reais como AWS, Heroku, GCP, etc;**
-   Sugestões sobre o challenge embasadas em alguma argumentação.

# Requisitos

## 1: Deve haver uma rota para listar todas as postagens cadastradas

`GET /posts`

Resposta:

```js
[
    {
        "id": 1, // ou qualquer outro identificador
        "title": "Notion",
        "author": "Marcia Thiel",
        "content": "Sed soluta nemo et consectetur reprehenderit ea reprehenderit sit. Aut voluptate sit omnis qui repudiandae. Cum sit provident eligendi tenetur facere ut quo. Commodi voluptate ut aut deleniti.",
        "tags": [
            "organization",
            "planning",
            "collaboration",
            "writing",
            "calendar"
        ]
    },
    {
        "id": 2,
        "title": "json-server",
        "author": "Eldora Schinner",
        "content": "Laudantium illum modi tenetur possimus natus. Sed tempora molestiae fugiat id dolor rem ea aliquam. Ipsam quibusdam quam consequuntur. Quis aliquid non enim voluptatem nobis. Error nostrum assumenda ullam error eveniet. Ut molestiae sit non suscipit.\nQui et eveniet vel. Tenetur nobis alias dicta est aut quas itaque non. Omnis iusto architecto commodi molestiae est sit vel modi. Necessitatibus voluptate accusamus.",
        "tags": [
            "api",
            "json",
            "schema",
            "node",
            "github",
            "rest"
        ]
    },
    {
        "id": 3,
        "title": "fastify",
        "author": "Delpha Balistreri",
        "content": "Eos corrupti qui omnis error repellendus commodi praesentium necessitatibus alias. Omnis omnis in. Labore aut ea minus cumque molestias aut autem ullam. Consectetur et labore odio quae eos eligendi sit. Quam placeat repellendus.\n Odio nisi dolores dolorem ea. Qui dicta nulla eos quidem iusto. Voluptatibus qui est accusamus sint perferendis est quae recusandae. Qui repudiandae cupiditate fugiat est.",
        "tags": [
            "web",
            "framework",
            "node",
            "http2",
            "https",
            "localhost"
        ]
    }
]

```

## 2: Deve ser possível filtrar postagens utilizando uma busca por tag

`GET /posts?tag=node` (_node_ é a tag sendo buscada neste exemplo)

Resposta:

```js
[
    {
        "id": 2,
        "title": "json-server",
        "author": "Eldora Schinner",
        "content": "Laudantium illum modi tenetur possimus natus. Sed tempora molestiae fugiat id dolor rem ea aliquam. Ipsam quibusdam quam consequuntur. Quis aliquid non enim voluptatem nobis. Error nostrum assumenda ullam error eveniet. Ut molestiae sit non suscipit.\nQui et eveniet vel. Tenetur nobis alias dicta est aut quas itaque non. Omnis iusto architecto commodi molestiae est sit vel modi. Necessitatibus voluptate accusamus.",
        "tags": [
            "api",
            "json",
            "schema",
            "node",
            "github",
            "rest"
        ]
    },
    {
        "id": 3,
        "title": "fastify",
        "author": "Delpha Balistreri",
        "content": "Eos corrupti qui omnis error repellendus commodi praesentium necessitatibus alias. Omnis omnis in. Labore aut ea minus cumque molestias aut autem ullam. Consectetur et labore odio quae eos eligendi sit. Quam placeat repellendus.\n Odio nisi dolores dolorem ea. Qui dicta nulla eos quidem iusto. Voluptatibus qui est accusamus sint perferendis est quae recusandae. Qui repudiandae cupiditate fugiat est.",
        "tags": [
            "web",
            "framework",
            "node",
            "http2",
            "https",
            "localhost"
        ]
    }
]

```

## 3: Deve haver uma rota para cadastrar uma nova postagem

O corpo da requisição deve conter as informações da postagem a ser cadastrada, sem o ID (gerado automaticamente pelo servidor). A resposta, em caso de sucesso, deve ser o mesmo objeto, com seu novo ID gerado.

`POST /posts Content-Type: application/json`

```js
{
    "title": "hotel",
    "authot": "Jett Hilpert",
    "content": "Local app manager. Start apps within your browser, developer tool with local .localhost domain and https out of the box.",
    "tags":["node", "organizing", "webapps", "domain", "developer", "https", "proxy"]
}

```

Resposta:

`Status: 201 Created`

`Content-Type: application/json`

```js
{
    "title": "hotel",
    "authot": "Jett Hilpert",
    "content": "Local app manager. Start apps within your browser, developer tool with local .localhost domain and https out of the box.",
    "tags":["node", "organizing", "webapps", "domain", "developer", "https", "proxy"],
    "id":5 // ou qualquer outro identificador
}

```
## 4: Deve haver uma rota para editar uma nova postagem

O corpo da requisição deve conter as informações editadas da postagem, sem o ID (informado na URL da requisição). Deve ser possível editar os valores individualmente (`title`, `authot`, `content` ou `tags`), ou todos os valores de uma vez só.  A resposta, em caso de sucesso, deve ser o mesmo objeto, com os valores alterados.

`PUT /posts/{id} Content-Type: application/json`

```js
{
    "title": "hotel",
    "authot": "Taylor Haag",
    "content": "Local app manager. Start apps within your browser, developer tool with local .localhost domain and https out of the box.",
    "tags":["organizing", "webapps", "domain", "developer", "proxy"]
}

```

Resposta:

`Status: 200 Success`

`Content-Type: application/json`

```js
{
    "title": "hotel",
    "authot": "Taylor Haag",
    "content": "Local app manager. Start apps within your browser, developer tool with local .localhost domain and https out of the box.",
    "tags":["organizing", "webapps", "domain", "developer", "proxy"],
    "id":5 // ou qualquer outro identificador
}

```

## 5: O usuário deve poder remover uma postagem por ID

`DELETE /posts/{id}`

Resposta:

`Status: 204 No Content`

## Critérios de Aceitação

-   A API deve ser real e escrita por você. Não serão aceitas APIs escritas de outros autores ou ferramentas que criam APIs automaticamente (Loopback, json-server, etc), ou código visivelmente gerado por I.A.;
-   Todos os requisitos acima devem ser cumpridos, seguindo o padrão de rotas estabelecido;
-   Deve haver um documento de API Blueprint, OpenAPI (antigo Swagger) ou algum gerador baseado em código (Scribe ou outro) descrevendo sua API;
-   Se você julgar necessário, adequado ou quiser deixar a aplicação mais completa (bônus!) você pode adicionar outras rotas, métodos, meios de autenticação com usuários, etc.
