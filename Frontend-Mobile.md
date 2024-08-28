# Dev. Front-End/Mobile

Sua tarefa é construir um aplicativo para a aplicação BlogPosts. A aplicação é um simples crud de posts de blog, com seus títulos e suas descrições. Utilize um repositório Git (público, de preferência) para versionamento e disponibilização do código.

**O aplicativo deve ser construído em React Native**

## O que será avaliado

Queremos avaliar sua capacidade de desenvolver e documentar a aplicação. Serão avaliados:

-   Código bem escrito e limpo;
-   Quais ferramentas foram usadas, como e porquê;
-   Seu conhecimento na construção de componentes reutilizáveis, consumo de APIs REST;
-   Sua capacidade de documentação da sua parte da aplicação.

## O mínimo necessário

- README.md contendo informações básicas do projeto e como executá-lo.
- Estilização de componentes com Styled Components
- Gerenciamento de estado com Redux e Context API
- React Hooks
- Typescript
- AsyncStorage
- Utilização de React Native CLI ou Expo

## Bônus

Os seguintes itens não são obrigatórios, mas darão mais valor ao seu trabalho:

- Uso de ferramentas ou bibliotecas externas que facilitem o seu trabalho;
- Cuidados especiais com otimização, padrões, entre outros;
- Animação nas micros interações;
- Testes Unitários;
- Offline first;
- Documentação dos componentes utilizando ferramentas como Storybook;
- Sugestões sobre o desafio embasadas em alguma argumentação.
- Autenticação
- Paginação
- Otimizações e abrangências em buscas(ex: Like Search)
- Foto de perfil(https://ui-avatars.com/)

## Layout
[Figma](https://www.figma.com/design/HcvpZmF73HxFIZkqcpzlSF/Teste-Front?node-id=0-1&t=swHc0l6DMYzOswMb-1)

## Funcionalidades

### Tela Inicial

- Visualizar uma lista de postagens com seus respectivos títulos e autores.
- Favoritar publicação
- Buscar postagens por título ou conteúdo.
- Botão flutuante para criar uma nova postagem.

### Tela de Criar Postagem

- Criar uma postagem com os campos título e conteúdo.

### Tela de Visualizar Postagem

- Visualizar o título, conteúdo e comentários da publicação.
- Criar um comentário.
- Acessar o perfil do usuário que realizou comentário na publicação.

### Tela de Perfil do Usuário

- Visualizar as informações de perfil do usuário.
- Visualizar as postagens criadas por esse usuário.

### Tela de favoritos

- Visualizar uma lista de postagens favoritas com seus respectivos títulos e autores.
- Favoritar publicação
- Buscar postagens por título ou conteúdo.
- Botão flutuante para criar uma nova postagem.

## API

Utilize a seguinte API para desenvolvimento do APP: https://jsonplaceholder.typicode.com

### Rotas
https://jsonplaceholder.typicode.com/guide/
```
GET 	/posts
GET 	/posts/1
GET 	/posts/1/comments
POST 	/posts/1/comments
POST 	/posts
PUT 	/posts/1
PATCH 	/posts/1
DELETE 	/posts/1
GET 	/users/1
GET 	/users/1/posts
```

## Recursos

### Publicação

- **Atributos:**
  - id
  - título
  - conteúdo
  - autor (usuário)
  - comentários

### Usuário

- **Atributos:**
  - id
  - nome
  - nome de usuário (ex: @joe)
  - email
  - endereço
  - telefone
  - empresa
  - foto de perfil (atributo bônus)

### Comentário

- **Atributos:**
  - autor (usuário)
  - conteúdo

## Importante

- Esta é uma **API fake**, se for adicionado um post, por exemplo, o post não é persistido no servidor, mas é retornado uma `response` para que o post seja adicionado na listagem. O mesmo deve ser lembrado para remoção.
- A API não fornece rota para favoritar postagem, utilize alguma forma de cache para isso.

----

### 🙏 Bom trabalho!
