# Projeto Vanilla

>A solução definitiva para gerenciar usuários com nossa API de cadastro! 
Desenvolvida para integrar perfeitamente frontend e backend, nossa API oferece segurança de dados de última geração, com autenticação e autorização robustas. 
Sua escalabilidade e flexibilidade são incomparáveis, seguindo os padrões RESTful mais avançados e as melhores práticas de codificação. 

## Figma
> Acompanhe o projeto no [Figma](#https://www.figma.com/file/bttjiVEWWnXBX94D5sy1E7/Vanilla-551325?type=design&node-id=0%3A1&mode=design&t=nErIXMAJZodXbkGg-1) ou no [Trello](#https://trello.com/invite/b/Z8ans0Wy/ATTI2e95d85a93f86da7afa9d4468b739b4827F539C9/vanilla).

## Requisitos

- [ ] CRUD de Clientes
- [ ] CRUD de produto
- [ ] CRUD de usuários
- [ ] CRUD de ordem de serviço
- [ ] Autenticação
- [ ] Dashboard

## Documentação da API

### Endpoint de Clientes

- [Listar clientes](#listar-clientes)
- [Cadastrar clientes](#cadastrar-clientes)
- [Detalhar clientes](#detalhar-clientes)
- [Apagar clientes](#apagar-clientes)
- [Atualizar clientes](#atualizar-clientes)


### Listar Clientes

`GET` /clientes

>Se o usuário estiver autenticado, retorna um array com os clientes cadastrados.

#### Exemplo de resposta

```js
{
	"id": 1,

	"nome": "clientes",
	"icone": "clientes-icon",
}
```

#### Codigo de status

|Código    | Descrição
|:---------:|----------
| 200          | lista de categorias retornado com sucesso.
| 401           | não autenticado. Se autentique em /link.

---

### Cadastrar Clientes

`POST` /clientes

>Cadastra uma categoria com os dados enviados no corpo da requisição. 

#### Corpo da requisição

| Campo | Tipo | Obrigatório | Descrição
|--------|-----|:------------:|-----------
| nome | string | sim | o nome do cliente master.
| icone | string | nao | ../img/client/?.

#### Exemplo de requisição

```js
{
	"nome": "Vanilla"
}
```

#### Exemplo de resposta

```js
{
	"id": 1

	"nome": "Vanilla",
	"icone": "vanilla-icon"
}
```
#### Codigo de status

|Código | Descrição
|:---------:|----------|
|201 | O cliente foi criado com sucesso.
|400| A validação falhou. verifique o corpo da requisição.
|401 | Não autenticado. Necessário autenticação ../link.


---

### Detalhar Clientes

`GET` /cliente/`id`

>Retorna os detalhes dos clientes de acordo com o `id` informado no path.

#### Exemplo de resposta

```js
{
	"id": 1

	"nome": "Vanilla",
	"icone": "vanilla-icon"
}
```
#### Codigo de status

|Código | Descrição
|:---------:|----------|
|201 | Cliente criado com sucesso.
|400| A validação falhou. Verifique o corpo da requisição.
|401 | Não autenticado. Necessário autenticação ../link.
|403 | Não autorizado. Esse cliente nao pertence ao usuário autenticado.
|404 | Não existe cliente com o `id` informado.

---

### Apagar Clientes

`DELETE` /clientes/`id`

>Apaga o cliente selecionado com o `id` informado no path.

#### codigo de status

|Código | Descrição
|:---------:|----------|
|201 | A categoria foi apagada com sucesso.
|401 | Não autenticado. Necessário autenticação ../link.
|403 | Não autorizado. Esse cliente nao pertence ao usuário autenticado.
|404 | Não existe cliente com o `id` informado.

### Atualizar Clientes

`PUT`  /clientes/`id`

>Atualiza os dados do cliente com o `id` informado no path, utilizando as informações do corpo da requisição.

#### Corpo da requisição

| Campo | Tipo | Obrigatório | Descrição
|--------|-----|:------------:|-----------
| nome | string | sim | O nome do cliente alterado.
| icone | string | sim | O novo ícone do cliente.

#### Exemplo de requisição

```js
{
	"nome": "Purple",
	"icone": "purple-icon"
}
```

#### Exemplo de resposta

```js
{
	"id": 1

	"nome": "Purple",
	"icone": "purple-icon"
}
```
#### Codigo de status

|Código | Descrição
|:---------:|----------|
|201 | Cliente criado com sucesso.
|400| A validação falhou. Verifique o corpo da requisição.
|401 | Não autenticado. Necessário autenticação ../link.
|403 | Não autorizado. Esse cliente nao pertence ao usuário autenticado.
|404 | Não existe cliente com o `id` informado.
