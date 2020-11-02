<h3 align="center">
  Desafio Bootcamp Rocketseat GoStack 02: Conceitos do Node.js
</h3>

## :rocket: Sobre o desafio

Essa desafio teve o objetivo de criar uma aplicação para armazenar repositórios de um portfólio, que permite a criação, listagem, atualização e remoção dos repositórios, e além disso permitir que os repositórios possam receber "likes".

### Rotas da aplicação

- **`POST /repositories`**: A rota deve receber `title`, `url` e `techs` dentro do corpo da requisição, sendo a URL o Link para o GitHub desse repositório. Ao cadastrar um novo repositório, ele deve ser armazenado dentro de um objeto no seguinte formato: `{ id: "uuid", title: 'Desafio Node.js', url: 'http://github.com/...', techs: ["Node.js", "..."], likes: 0 }`; Os likes sempre começam com 0.

- **`GET /repositories`**: Rota que lista todos os repositórios cadastrados;

- **`PUT /repositories/:id`**: A rota deve alterar apenas o `title`, a `url` e as `techs` do repositório que possua o `id` igual ao `id` presente nos parâmetros da rota;

- **`DELETE /repositories/:id`**: A rota deve deletar o repositório com o `id` presente nos parâmetros da rota;

- **`POST /repositories/:id/like`**: A rota deve aumentar o número de likes do repositório específico escolhido através do `id` presente nos parâmetros da rota, a cada chamada dessa rota, o número de likes deve ser aumentado em 1;

### Especificação dos testes

Para esse desafio temos os seguintes testes unitários:

- **`should be able to create a new repository`**: Para que esse teste passe, a aplicação deve permitir que um repositório seja criado, e retorne um JSON com o repositório criado.

- **`should be able to list the repositories`**: Para que esse teste passe, a aplicação deve permitir que seja retornado um Array com todos os repositórios que foram criados até o momento.

- **`should be able to update repository`**: Para que esse teste passe, a aplicação deve permitir que sejam alterados apenas os campos `url`, `title` e `techs`.

- **`should not be able to update a repository that does not exist`**: Para que esse teste passe, deve validar a rota de update se o id do repositório enviado pela URL existe ou não. Caso não exista, retornar um erro com status `400`.

- **`should not be able to update repository likes manually`**: Para que esse teste passe, não deve permitir que a rota de Update altere diretamente os likes desse repositório, mantendo o mesmo número de likes que o repositório já possuia antes da atualização. Isso porque o único lugar que deve atualizar essa informação é a rota responsável por aumentar o número de likes.

- **`should be able to delete the repository`**: Para que esse teste passe, deve permitir que a a rota de Delete exclua um repositório, e ao fazer a exclusão, ele retorne uma resposta vazia, com status `204`.

- **`should not be able to delete a repository that does not exist`**: Para que esse teste passe, deve validar na rota de Delete se o id do repositório enviado pela URL existe ou não. Caso não exista, retornar um erro com status `400`.

- **`should be able to give a like to the repository`**: Para que esse teste passe, a aplicação deve permitir que um repositório com o id informado possa receber likes. O valor de likes deve ser incrementado em 1 a cada requisição, e como resultado, retornar um JSON contendo o repositório com o número de likes atualizado.

- **`should not be able to like a repository that does not exist`**: Para que esse teste passe, deve validar na a rota de like se o id do repositório enviado pela URL existe ou não. Caso não exista, retornar um erro com status `400`.

# :toolbox: Quais tecnologias foram utilizadas?

- Javascript.
- Node.js.
- Express.
- uuidv4.
- Jest.

# :computer: Executar a aplicação.

Com o Node.js versão 12 e o Git instalado em seu computador execute os comandos abaixo:

```
git clone https://github.com/NatanNMB15/gostack-template-conceitos-nodejs
cd gostack-template-conceitos-nodejs
yarn install
yarn dev
```

# :heavy_check_mark: Executar testes.

Após executar os passos de execução da aplicação acima, encerre a aplicação, e rode o comando abaixo para executar os testes unitários:

```
yarn test
```
