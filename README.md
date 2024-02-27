# Projeto Vanilla

Construção da API para consumo futuro.

## Requisitos

- [     ] CRUD de categorias
- [     ] CRUD DE CATEGORIAS
- [     ] CRUD DE MOVIMENTAÇÕES
- [     ] CRUD DE USUÁRIOS

	INDIVIDUAL

	COLETIVO

	SEPARADO POR DEPARTAMENTO

- [     ] AUTENTICACAO

	LOGIN

	LOGOUT

	GESTÃO DE USUÁRIO

- [     ] DASHBOARD

## DOCUMENTAÇÃO DA API

### ENDPOINT

- LISTAR CATEGORIAS
- CADASTRAR CATEGORIAS
- DETALHAR CATEGORIAS
- ATUALIZAR CATEGORIAS
- APAGAR CATEGORIAS

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
