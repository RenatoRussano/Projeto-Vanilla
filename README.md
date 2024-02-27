# Projeto Vanilla

Construção da API para consumo futuro.

## Requisitos

- [     ] CRUD de categorias
- [     ] CRUD DE CATEGORIAS
- [     ] CRUD DE MOVIMENTAÇÕES
- [     ] CRUD DE USUÁRIOS
- [     ] AUTENTICACAO
- [     ] DASHBOARD

## DOCUMENTAÇÃO DA API

### ENDPOINT

- [LISTAR CATEGORIAS](#listar-categorias)
- [CADASTRAR CATEGORIAS](#cadastrar-categoria)
- [DETALHAR CATEGORIAS](#detalhar-categoria)
- [APAGAR CATEGORIAS](#apagar-categoria)
- [ATUALIZAR CATEGORIAS](#atualizar-categoria)

### LISTAR CATEGORIAS

`GET` /categoria

Retorna um array com as categorias do usuario autenticado

#### Exemplo de resposta

```js
[
	{
		"id": 1,
		"nome": "da-categoria",
		"icone": "nome-do-icone",
	}
]
```

#### Codigo de status
|codigo | descricao
|-------|----------
|200 | lista de categorias retornado com sucesso
|401 | não autenticado. Se autentique em /link

---

### CADASTRAR CATEGORIA

`POST` /categoria

Cadastra uma categoria com os dados enviados no corpo da requisição

#### Corpo da requisição

| campo | tipo | obrigatório | descrição
|--------|-----|:------------:|-----------
| nome | string | sim | escerver algo que ajude quem vai fazer isso
| icone | string | nao | nome do icone conforme material icons

#### Exemplo de requisição

```js

{
	"nome": "Alimentação"
}

```

#### Exemplo de resposta

```js
{
	"id": 1
	"nome": "Alimentação",
	"icone": "fast-food"
}
```
#### Codigo de status
|codigo | descricao
|-------|----------
|201 | categoria foi criada com sucesso
|400| validação falhou. verifique o corpo da requisição
|401 | não autenticado. Se autentique em /link


---

### Detalhar Categoria

`GET` /categoria/`{id}`

retorna os detalhes da categoria com o `id` informado no path.

#### Exemplo de resposta

```js
// GET / categoria / 1
{
	"id": 1
	"nome": "Alimentação",
	"icone": "fast-food"
}

```
#### Codigo de status
|codigo | descricao
|-------|----------
|201 | categoria foi criada com sucesso
|400| validação falhou. verifique o corpo da requisição
|401 | não autenticado. Se autentique em /link
|403 | NAO AUTORIZADO. essa categoria nao pertence ao usuario autenticado
|404 | NAO EXISTE CATEGORIA COM O `{id}` INFORMADO

---

### APAGAR CATEGORIA

`DELETE` / CATEGORIA/`{ID}`

apaga a categoria com o `id` informado no path

#### codigo de status

|codigo | descricao
|-------|----------
|201 | categoria foi criada com sucesso
|401 | não autenticado. Se autentique em /login
|403 | NAO AUTORIZADO. essa categoria nao pertence ao usuario autenticado
|404 | NAO EXISTE CATEGORIA COM O `id` INFORMADO

### atualizar categoria

`PUT`  / categoria /`{id}`

Atualiza os dados da categoria com o `id` informado no path, utilizando as informações do corpo da requisição 

#### Corpo da requisição

| campo | tipo | obrigatório | descrição
|--------|-----|:------------:|-----------
| nome | string | sim | o novo nome da categoria
| icone | string | sim | obrigatório enviar o icone conforme material icon

#### Exemplo de requisição

```js

{
	"nome": "Restaurante",
	"icone": "fast-food"
}

```

#### Exemplo de resposta

```js
{
	"id": 1
	"nome": "Restaurante",
	"icone": "fast-food"
}
```
#### Codigo de status
|codigo | descricao
|-------|----------
|200 | categoria atualizada com sucesso
|400| validação falhou. verifique o corpo da requisição
|401 | não autenticado. Se autentique em /link
|403 | NAO AUTORIZADO. essa categoria nao pertence ao usuario autenticado
|404 | NAO EXISTE CATEGORIA COM O `id` INFORMADO
