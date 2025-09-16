# GraphQL

1. Open Bruno and create New `graphql` request

2. Enter name `pokemon` and url `https://graphql-pokeapi.graphcdn.app/` keep default method `POST`

3. Go to `query` tab and add 

```json 
query {
  pokemon(name: "pikachu") {
    id
    name
    height
    weight
    types {
      type {
        name
      }
    }
  }
}
```

4. Execute request and verify response as below:

```js
{
  "data": {
    "pokemon": {
      "id": 25,
      "name": "pikachu",
      "height": 4,
      "weight": 60,
      "types": [
        {
          "type": {
            "name": "electric"
          }
        }
      ]
    }
  }
}
```

If your response recieve above object you have completed the assignment.