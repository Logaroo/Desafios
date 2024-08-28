# Dev. Front-End

Sua tarefa é construir um aplicativo para a aplicação BlogPosts. A aplicação é um simples crud de posts de blog, com seus títulos e suas descrições. Utilize um repositório Git (público, de preferência) para versionamento e disponibilização do código.

O aplicativo deve ser construído em React Native, utilizando [este style guide](https://www.behance.net/gallery/84764869/UI-and-UX-Style-Guide) e seguindo os wireframes apresentados abaixo.

## O que será avaliado

Queremos avaliar sua capacidade de desenvolver e documentar a aplicação. Serão avaliados:

-   Código bem escrito e limpo;
-   Quais ferramentas foram usadas, como e porquê;
-   Seu conhecimento na construção de componentes reutilizáveis, consumo de APIs REST;
-   Sua capacidade de se comprometer com o que foi fornecido (wireframe, styleguide);
-   Sua capacidade de documentação da sua parte da aplicação.

## O mínimo necessário

- As telas seguindo os wireframes a seguir e utilizando a API disponibilizada ao fim deste documento;
- O aplicativo deve ser construído usando Typescript e Styled Component;
- README.md contendo informações básicas do projeto e como executá-lo.

## Bônus

Os seguintes itens não são obrigatórios, mas darão mais valor ao seu trabalho (os em negrito são mais significativos para nós e serão considerados um diferencial):

-   Uso de ferramentas ou bibliotecas externas que facilitem o seu trabalho;
-   Cuidados especiais com otimização, padrões, entre outros;
-   **React Hooks**;
-   **React i18next**;
-   **Gerenciamento de estado com Redux ou Context API**;
-   **Testes**;
-   **Documentação dos componentes utilizando ferramentas como Storybook**;
-   Sugestões sobre o desafio embasadas em alguma argumentação.

# User Stories e wireframes

## 1: O(A) usuário(a) deve poder ver a lista de todos os posts cadastrados e adicionar um novo post

Listar posts:

`GET /posts`

Adicionar novo post:

`POST /posts Content-Type: application/json`

```json
{
    "title": "foo",
    "body": "bar",
    "userId": 1
}
```

![Crud - Adicionar](https://cdn.discordapp.com/attachments/700348106419470369/747478882550153346/unknown.png)


## 2: O(A) usuário(a) deve poder clicar em remover um post e o post ser removido da listagem

Remover um post:

`DELETE /posts/{id}`

![Crud - Remover](https://cdn.discordapp.com/attachments/700348106419470369/747479006814929126/unknown.png)

## 3: O(A) usuário(a) deve poder utilizar o input de busca para realizar uma busca por um post

Buscar pelo `title` de um post:

`GET /posts?title=qui%20est%20esse`

===============================================================================================

## Critérios de Aceitação

-   O aplicativo deve ser codificado seguindo:
    - Os fluxos definidos no wireframe acima (listar, adicionar, remover e buscar);
    - A estilização dos componentes necessários, tipografia, e espaçamentos de acordo com a Style Guide: [UI and UX Style Guide](https://www.behance.net/gallery/84764869/UI-and-UX-Style-Guide);
    - A API disponibilizada logo abaixo.

# API

A base url a ser utilizada será esta: `https://jsonplaceholder.typicode.com`.

Por exemplo, para listar os posts deve ser feita uma requisição para: `https://jsonplaceholder.typicode.com/posts`.

E assim por diante seguindo os endpoints demonstrados no wireframe acima.

## Importante

Esta é uma fake api, se for adicionado um post, por exemplo, o post não é persistido no servidor, mas é retornado uma `response` para que o post seja adicionado na listagem. O mesmo deve ser lembrado para remoção.

Bom trabalho!
