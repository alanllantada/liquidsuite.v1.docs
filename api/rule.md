# Rules

Rules são as regras dentro do sistema Liquid, atreladas ao objetos do sistema (Armários, Pastas, Documentos, Grupos, Usuários, Fichas).

As regras são aplicadas aos diversos objetos do Sistema, num contexto de validação sobre uma determinada ação a um objeto.

Cada Regra possui ações que pode ser realizadas (ou negadas) para os objetos do sistema, como Armários, Pastas, Documentos e Páginas.

Como funciona:  

Contexto - Grupo

Um Grupo pode possuir quantas regras forem aplicadas. Todos os usuários deste Grupo irão herdar as regras do mesmo.

Contexto - Usuário

Um Usuario pode possuir quantas regras forem aplicadas. Por herança, todas as regras aplicadas ao Grupo do qual o Usuáro faz parte, serão consideradas validas para o Usuario em tempo de execução.

Contexto - Ficha

Uma Ficha pode possuir uma ou mais Regras. Quando uma ficha possui uma Regra XYZ, todos os usuários (ou grupos) que possuirem esta regra, poderão realizar ações sobre os Documentos desta Ficha.

- Os mesmos só podem possuir pastas. <br /><br />

## **Get**

Retorna as informações básicas do Armário.

- Chamada deve ser autenticada.
- Request Header's (veja seção sobre cabeçalhos)

---

ENDPOINTS

`GET /v1/armarios/{id}`

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

[Armario basic object](#armario-basic-object)

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

fetch('https://coredomain/v1/api/armarios/1', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```

```json
// RESPONSE

{
  "id": 101,
  "nome": "Armario 123"
}
```

---

<br />

### **Rule basic object**

```json
id: integer // identificador
nome: string // nome do armário
```
