# Pastas

As pastas no Liquid Suite são objetos que podem possuir documentos e subpastas como seus decendentes.

As pastas tambem podem possuir uma ficha atribuida a mesma, onde os documentos importados para a mesma irão assumir essa ficha como padrão.

<br /><br />

## **Get**

Retorna as informações básicas da Pasta.

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

---

ENDPOINTS

`GET /v1/api/pastas/{id}`

---

PATH PARAMETERS

`id` - required - integer - greather then zero

Identificador da pasta

---

QUERY STRING PARAMETERS

None

---

BODY REQUEST

None

---

RESPONSE

`Http Status Code - 200`

Content - [Pasta basic object](#pasta-basic-object)

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'GET',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    Authorization: 'Bearer token12345'
  }
};

fetch('https://coredomain/v1/api/pastas/1', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

```json
// RESPONSE

{
  "id": 1,
  "nome": "Pasta 123",
  "armarioId": 1,
  "pastaPaiId": null
}
```

---

<br />

## **Get All by Armario**

Retorna todas* as Pastas que descendem do Armário informado.

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

*\*Serão retornados todas as Pastas as quais o usuário(token) tem direito de acesso*

---

ENDPOINTS

`GET /v1/api/pastas/byarmario/{id}`

---

PATH PARAMETERS

`id` - required - integer - greather then zero

Identificador do armário

---

QUERY STRING PARAMETERS

None

---

BODY REQUEST

None

---

RESPONSE

`Http Status Code - 200`

Content - Um Array de [Pasta short object](#pasta-short-object)

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'GET',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    Authorization: 'Bearer token12345'
  }
};

fetch('https://coredomain/v1/api/pastas/byarmario/1', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

```json
// RESPONSE

[
  {
    "id": 1,
    "nome": "Pasta 123"
  },
  {
    "id": 2,
    "nome": "Pasta 456"
  }
]
```

---

<br />

## **Get All by Pasta Pai**

Retorna todas* as Pastas que descendem da Pasta informada.

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

*\*Serão retornados todas as Pastas as quais o usuário(token) tem direito de acesso*

---

ENDPOINTS

`GET /v1/api/pastas/bypastapai/{id}`

---

PATH PARAMETERS

`id` - required - integer - greather then zero

Identificador da pasta pai

---

QUERY STRING PARAMETERS

None

---

BODY REQUEST

None

---

RESPONSE

`Http Status Code - 200`

Content - Um Array de [Pasta short object](#pasta-short-object)

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'GET',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    Authorization: 'Bearer token12345'
  }
};

fetch('https://coredomain/v1/api/pastas/bypastapai/1', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

```json
// RESPONSE

[
  {
    "id": 4,
    "nome": "Pasta 004"
  },
  {
    "id": 5,
    "nome": "Pasta 005"
  }
]
```

---

<br />

## **Rules**

Retorna as regras aplicadas a Pasta

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

---

ENDPOINTS

`GET /v1/api/pasta/rules/{id}`

---

PATH PARAMETERS

`id` - required - integer - greather then zero

Identificador da pasta

---

QUERY STRING PARAMETERS

None

---

BODY REQUEST

None

---

RESPONSE

`Http Status Code - 200`

Content - Um Array de [Rule basic object](rule.md#rule-basic-object)

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'GET',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    Authorization: 'Bearer token12345'
  }
};

fetch('https://coredomain/v1/api/pastas/rules/1', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

```json
// RESPONSE

[
  {
    "id": 101,
    "nome": "Regra 123"
  },
  {
    "id": 102,
    "nome": "Regra 456"
  }
]
```

---

<br />

## **Access Rules**

Retorna as regras de acesso aplicadas a Pasta

*Uma regra de acesso é uma Regra que é aplicada ao objeto para que se tenha direito de Acessar o mesmo e tem por função somente o acesso, sem ações sobre o objeto*

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

---

ENDPOINTS

`GET /v1/api/pastas/accessrules/{id}`

---

PATH PARAMETERS

`id` - required - integer - greather then zero

Identificador da Pasta

---

QUERY STRING PARAMETERS

None

---

BODY REQUEST

None

---

RESPONSE

`Http Status Code - 200`

Content - Um Array de [Rule basic object](rule.md#rule-basic-object)

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'GET',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    Authorization: 'Bearer token12345'
  }
};

fetch('https://coredomain/v1/api/pastas/rules/1', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

```json
// RESPONSE

[
  {
    "id": 101,
    "nome": "Regra 123"
  },
  {
    "id": 102,
    "nome": "Regra 456"
  }
]
```

---

<br />

## **Properties**

Retorna as propriedades da Pasta

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

---

ENDPOINTS

`GET /v1/api/pastas/properties/{id}`

---

PATH PARAMETERS

`id` - required - integer - greather then zero

Identificador da Pasta

---

QUERY STRING PARAMETERS

None

---

BODY REQUEST

None

---

RESPONSE

`Http Status Code - 200`

Content - [Pasta properties](#pasta-properties)

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'GET',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    Authorization: 'Bearer token12345'
  }
};

fetch('https://coredomain/v1/api/pastas/properties/1', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

```json
// RESPONSE

{
  "id": 1,
  "nome": "PASTA 123",
  "nomeFicha": null,
  "dtCriacao": "2022-01-01T16:55:01.920053",
  "tamanho": 36705818,
  "pastas": 11,
  "documentos": 4,
  "paginas": 17
}
```

---

<br />

## **Virtual Path**

Retorna o caminho "virtual" da pasta, desde o Armário ate a pasta informada, utilizando o separador "\\" entre os níveis

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

---

ENDPOINTS

`GET /v1/api/pastas/virtualpath/{id}`

---

PATH PARAMETERS

`id` - required - integer - greather then zero

Identificador da Pasta

---

QUERY STRING PARAMETERS

None

---

BODY REQUEST

None

---

RESPONSE

`Http Status Code - 200`

Content - [Pasta Virtual Path](#pasta-virtual-path)

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'GET',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    Authorization: 'Bearer token12345'
  }
};

fetch('https://coredomain/v1/api/pastas/virtualpath/1', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

```json
// RESPONSE

{
  "id": 1,
  "path": "ARMARIO 123\\PASTA 123"
}
```

---

<br />

## **Create**

Cria um novo Armário

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

---

ENDPOINTS

`POST /v1/api/armarios`

---

PATH PARAMETERS

None

---

QUERY STRING PARAMETERS

None

---

BODY REQUEST

[Armario basic object](#armario-basic-object)

---

RESPONSE

`Http Status Code - 201`

Content - Identificador do Armário criado (ID) - integer

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'POST',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    'Content-Type': 'application/json',
    Authorization: 'Bearer token12345'
  },
  body: '{"id":0,"nome":"Armário 123"}'
};

fetch('https://coredomain/v1/api/armarios', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

```json
// RESPONSE

20
```

---

<br />

## **Update**

Atualiza/Modifica o nome de um Armário

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

---

ENDPOINTS

`PUT /v1/api/armarios`

---

PATH PARAMETERS

None

---

QUERY STRING PARAMETERS

None

---

BODY REQUEST

[Armario basic object](#armario-basic-object)

---

RESPONSE

`Http Status Code - 200`

Content: None

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'PUT',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    'Content-Type': 'application/json',
    Authorization: 'Bearer token12345'
  },
  body: '{"id":20,"nome":"Armário 123  - Rename"}'
};

fetch('https://coredomain/v1/api/armarios', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

---

<br />

## **Update Rules**

Adiciona/Remove Regras ao Armário e seus decendentes. Como está operção pode envolver vários objetos (Pastas e Documentos) que estão "abaixo" do Armário, a chamada a este método pode levar vários minutos, pois se trata de uma chamada recursiva.

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

*A regra de Administrador Sistema, mesma não informada, será mantida para todos os objetos do sistema*

---

ENDPOINTS

`PUT /v1/api/armarios/rules`

---

PATH PARAMETERS

None

---

QUERY STRING PARAMETERS

`applyToChilds` - required - boolean

*Ao enviar como true, todas as alterações serão aplicadas aos descendentes deste objeto, recursivamente, em todos os níveis.*

*OBS: O sistema irá verificar se existe alguma inconsistencia em aplicar as regras para os descendentes. Exemplo: Caso esteja removendo uma regra de acesso, porém um descendente (seja em qualquer nível) possuir esta regra como ação, o sistema não podera completar a operação!*
*Caso queria forçar que as regras de ações dos descendentes também sejam excluidas, utilize o parametro 'forceDeleteRoles' como true para forçar exclusão de regras de ação dos descendentes!*

`applyToChilds` - required - boolean

*Ao enviar como true, o sistema irá remover a(s) regra(s) de ação dos descendentes, caso estas tenham sido removidas do objeto Pai!*

---

BODY REQUEST

[Armario complete object](#armario-complete-object)

---

RESPONSE

`Http Status Code - 200`

Content: None

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'PUT',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    'Content-Type': 'application/json',
    Authorization: 'Bearer token12345'
  },
  body: '{"id":20,"nome":"Armário 123  - Rename","extendAccessRoles":true,"objectsRules":[{"id":1,"nome":"Administrador Sistema"},{"id":2,"nome":"REGRA 01"}],"objectsRulesAccess":[{"id":1,"nome":"Administrador Sistema"},{"id":2,"nome":"REGRA 01"}]}'
};

fetch('https://coredomain/v1/api/armarios/rules?applyToChilds=true&forceDeleteRoles=true', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

---

<br />

## **Delete**

Exclui um Armário e os objetos (Pastas, Documentos e Páginas) que descendem dele.

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

*Importante!! Ao excluir um Armário, também será excluido as Pastas, Documentos e Páginas que descendem deste Armário, incluindo os arquivos*

---

ENDPOINTS

`DELETE /v1/api/armarios/{id}`

---

PATH PARAMETERS

`id` - required - integer - greather then zero

Identificador do armário

---

QUERY STRING PARAMETERS

None

---

BODY REQUEST

None

---

RESPONSE

`Http Status Code - 200`

Content: None

---

ERROR RESPONSE

[Error response API Liquid Suite](errorresponse.md)

---

EXAMPLE

```javascript
// REQUEST

const options = {
  method: 'DELETE',
  headers: {
    'X-Application-Name': 'aplicationidentifier',
    Authorization: 'Bearer token12345'
  }
};

fetch('https://coredomain/v1/api/armarios/20', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

---

<br />

## **Objects**

### **Pasta short object**

```json
id: integer // identificador
nome: string // nome da pasta
```

### **Pasta basic object**

```json
id: integer // identificador
nome: string // nome da pasta
armarioId: int? // identificador do armário quando o mesmo descende de um armário (senão null)
pastaPaiId: int? // identificador da pasta pai quando o mesmo descende de uma pasta (senão null)
```

### **Pasta properties**

```json
nome: string // nome do armário
nomeFicha: string // nome da ficha (quando atribuida a uma pasta)
dtCriacao: datetime // datetime local no formato: yyyy-MM-ddTHH:mm:ss.ffffff
tamanho: long // tamanho em bytes
pastas: long // total de pastas 
documentos: long // total de documentos
paginas: long // total de paginas
```

### **Pasta Virtual Path**

```json
id: integer // identificador
path: string // caminho virtual da pasta
```

### **Armario complete object**

```json
id: integer // identificador
nome: string // nome do armário
pastas: array de pastas // pastas
extendAccessRoles: boolean // flag extender regras de acesso
objectsRules: array de rules  // regras
objectsRulesAccess: array de rules // regras de acesso
```

[Referência a rule](rule.md#rule-basic-object)
