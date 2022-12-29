# JSON-Server | Nomad Room

## 🔰 Base url: https://nomad-room-json-server-udrn.onrender.com
> Fake Api utilizada na aplicação <a href="https://github.com/steinerstt/nomad-room" target="_blank"> Nomad Room </a>

## Endpoints
Essa fake-api tem um total de 8 endpoints que podem ser utilizados.

# Rotas que não requerem de autenticação

## Login

POST /login
```JavaScript
{
  method: "POST"
}
```

Body
```JavaScript
{
  "email": "diogotrue@gmail.com",
  "password": "123456"
}
```

Response - 200
```JavaScript
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImRpb2dvdHJ1ZUBnbWFpbC5jb20iLCJpYXQiOjE2NjczMTQxMDIsImV4cCI6MTY2NzMxNzcwMiwic3ViIjoiMiJ9.q4Blfnde4cLBf3xGHzP7guok8obPaEYnXWZvhHVPW3Q",
  "user": {
    "email": "diogotrue@gmail.com",
    "name": "Diogo",
    "last_name": "Steiner",
    "age": 21,
    "genre": "Masculino",
    "profession": "Develop",
    "profile_photo": "https://i.imgur.com/XnEcZ0p.jpg",
    "validation": true,
    "id": 2
  }
}
```

<br>

## Cadastro do usuário

POST /register
```JavaScript
{
    method: "POST"
}
```

Body
```JavaScript
{
  "name": "Diogo",
  "last_name": "Steiner",
  "email": "diogotrue@gmail.com",
  "password": "123456",
  "age": 21,
  "genre": "Masculino",
  "profession": "Develop",
  "profile_photo": null,
  "validation": false
}

```

Response - 200
```JavaScript
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImRpb2dvdHJ1ZUBnbWFpbC5jb20iLCJpYXQiOjE2NjczMTA0OTMsImV4cCI6MTY2NzMxNDA5Mywic3ViIjoiMiJ9.XUQ-w3vut-RYGGzbJ4TIzA9OHaHIylfUIbnrD8nCrco",
  "user": {
    "email": "diogotrue@gmail.com",
    "name": "Diogo",
    "last_name": "Steiner",
    "age": 21,
    "genre": "Masculino",
    "profession": "Develop",
    "profile_photo": null,
    "validation": false,
    "id": 2
  }
}
```

<br>

## Buscar todos os quartos

GET /rooms
Response - 200

```JavaScript
[
  {
    "userId": 2,
    "title": "Quarto INDIVIDUAL a 3 minutos a pé da estação Carrão do METRÔ!!!",
    "description": "Não cobramos mais nenhuma taxa extra. Não fornecemos internet, você pode solicitar uma ou dividir o sinal com os outros hóspedes!",
    "about": {
      "gym": false,
      "internet": true,
      "tv": false,
      "garage": false,
      "animals": true,
      "furnished": false
   },
    "localization": {
      "zip_code": "03071-100",
      "district": "Tatuapé",
      "state": "São Paulo , SP",
      "street": "Rua Doutor Raul da Rocha Medeiros",
      "number": 88
    },
  "room_photo": "https://i.imgur.com/e7SgPd5.jpg",
  "contact": 21999999999,
  "id": 1
},
{
  "userId": 2,
  "title": "Quarto com suíte em frente a praia - Recreio dos Bandeirantes",
  "description": "Linda suíte privativa, recém reformada, dedcorada e bem iluminada. Totalmente equipada: 1 king size,  frigobar, bebidas, closet, Ar-condicionado padrão. Com 30 m², cheio de comércios por perto. bla bla bla bla bla bla",
  "about": {
    "gym": true,
    "internet": true,
    "tv": true,
    "garage": true,
    "animals": true,
    "furnished": true
  },
  "localization": {
    "zip_code": "22795-009",
    "district": "Recreio dos Bandeirantes",
    "state": "Rio de Janeiro, RJ",
    "street": "Avenida Lúcio Costa",
    "number": 190
  },
  "room_photo": "https://i.imgur.com/TmrNGxu.jpg",
  "contact": 21999999999,
  "id": 2
},
  {}....
]
```

<br>

## Buscar quarto específico

GET /rooms/${id}

Response - 200
```JavaScript
{
  "userId": 2,
  "title": "Quarto Proa",
  "description": "Propriedade exclusiva e isolada projetada pelo premiado arquiteto dentro da Mata Atlântica com uma vista incrível e única para a Baía de Paraty. A vista pode ser apreciada a partir da cama ou da encantadora varanda do lado de fora do quarto.",
  "about": {
    "gym": false,
    "internet": false,
    "tv": false,
    "garage": false,
    "animals": true,
    "furnished": true
  },
  "localization": {
    "zip_code": "22641-209",
    "district": "Itanhangá",
    "state": "Rio de Janeiro, RJ",
    "street": "Travessa Pedreira da Floresta",
    "number": 1920
},
  "room_photo": "https://i.imgur.com/csJRYEj.jpg",
  "contact": 21999999999,
  "id": 5
}
```

<br>

## Buscar todos os quartos favoritados do usuário

GET /favorites?userId=${userId}

Response - 200
```JavaScript
[
  {
    "userId": 2,
    "title": "Quarto INDIVIDUAL a 3 minutos a pé da estação Carrão do METRÔ!!!",
    "description": "Não cobramos mais nenhuma taxa extra. Não fornecemos internet, você pode solicitar uma ou dividir o sinal com os outros hóspedes!",
    "about": {
      "gym": false,
      "internet": true,
      "tv": false,
      "garage": false,
      "animals": true,
      "furnished": false
  },
  "localization": {
    "zip_code": "03071-100",
    "district": "Tatuapé",
    "state": "São Paulo , SP",
    "street": "Rua Doutor Raul da Rocha Medeiros",
    "number": 88
  },
  "room_photo": "https://i.imgur.com/e7SgPd5.jpg",
  "contact": 21999999999,
  "id": 1
  },
  {}...
]
```

<br>
<br>

# Rotas que requerem de autenticação

## Validação do usuário

PATCH /users/${userId}
```JavaScript
{
  method: "PATCH"
  headers: {
    "Authorization": "Bearer ${token}"
  }
}
```

Body
```JavaScript
{
  "profile_photo": "https://i.imgur.com/XnEcZ0p.jpg",
  "validation": true
}
```

Response - 200
```JavaScript
{
  "email": "diogotrue@gmail.com",
  "password": "$2a$10$2mwZAftRtG9tSa3A3zzX.O8mESR63X10jZP5MNzjhXZz50UGAW1E.",
  "name": "Diogo",
  "last_name": "Steiner",
  "age": 21,
  "genre": "Masculino",
  "profession": "Develop",
  "profile_photo": "https://i.imgur.com/XnEcZ0p.jpg",
  "validation": true,
  "id": 2
}
```

<br>

## Adicionar quarto

POST /rooms
```JavaScript
{
  method: "POST"
  headers: {
    "Authorization": "Bearer ${token}"
  }
}
```

Body
```JavaScript
{
  "userId": 1,
  "title": "Quarto com suíte em frente a praia - Recreio dos Bandeirantes",
  "description": "Linda suíte privativa, recém reformada, dedcorada e bem iluminada. Totalmente equipada: 1 king size,  frigobar, bebidas, closet, Ar-condicionado padrão. Com 30 m², cheio de comércios por perto. bla bla bla bla bla bla",
  "about": {
    "gym": false,
    "internet": true,
    "tv": true,
    "garage": true,
   "animals": true,
   "furnished": true
  },
  "localization": {
    "zip_code": "22795-009",
    "district": "Recreio dos Bandeirantes",
    "state": "Rio de Janeiro, RJ",
    "street": "Avenida Lúcio Costa",
    "number": 190
  },
  "room_photo": "https://i.imgur.com/TmrNGxu.jpg",
  "contact": 21999999999
}
```

Response - 200
```JavaScript
{
  "userId": 1,
  "title": "Quarto com suíte em frente a praia - Recreio dos Bandeirantes",
  "description": "Linda suíte privativa, recém reformada, dedcorada e bem iluminada. Totalmente equipada: 1 king size,  frigobar, bebidas, closet, Ar-condicionado padrão. Com 30 m², cheio de comércios por perto. bla bla bla bla bla bla",
  "about": {
    "gym": false,
    "internet": true,
    "tv": true,
    "garage": true,
    "animals": true,
    "furnished": true
  },
  "localization": {
    "zip_code": "22795-009",
    "district": "Recreio dos Bandeirantes",
    "state": "Rio de Janeiro, RJ",
    "street": "Avenida Lúcio Costa",
    "number": 190
},
  "room_photo": "https://i.imgur.com/TmrNGxu.jpg",
  "contact": 21999999999
  "id": 2
}
```

<br>

## Adicionar quarto como favorito

POST /favorites
```JavaScript
{
  method: "POST"
  headers: {
    "Authorization": "Bearer ${token}"
  }
}
```

Body
```JavaScript
{
  "userId": 2,
  "title": "Quarto INDIVIDUAL a 3 minutos a pé da estação Carrão do METRÔ!!!",
  "description": "Não cobramos mais nenhuma taxa extra. Não fornecemos internet, você pode solicitar uma ou dividir o sinal com os outros hóspedes!",
  "about": {
    "gym": false,
    "internet": true,
    "tv": false,
    "garage": false,
    "animals": true,
    "furnished": false
  },
  "localization": {
    "zip_code": "03071-100",
    "district": "Tatuapé",
    "state": "São Paulo , SP",
    "street": "Rua Doutor Raul da Rocha Medeiros",
    "number": 88
  },
  "room_photo": "https://i.imgur.com/e7SgPd5.jpg",
  "contact": 21999999999
}
```

Response - 200
```JavaScript
{
  "userId": 2,
  "title": "Quarto INDIVIDUAL a 3 minutos a pé da estação Carrão do METRÔ!!!",
  "description": "Não cobramos mais nenhuma taxa extra. Não fornecemos internet, você pode solicitar uma ou dividir o sinal com os outros hóspedes!",
  "about": {
    "gym": false,
    "internet": true,
    "tv": false,
    "garage": false,
    "animals": true,
    "furnished": false
  },
  "localization": {
    "zip_code": "03071-100",
    "district": "Tatuapé",
    "state": "São Paulo , SP",
    "street": "Rua Doutor Raul da Rocha Medeiros",
    "number": 88
  },
  "room_photo": "https://i.imgur.com/e7SgPd5.jpg",
  "contact": 21999999999
  "id": 3
}
```
