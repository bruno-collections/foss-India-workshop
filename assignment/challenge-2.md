# Challenge 2: GraphQL Query Testing with Bruno

## What is GraphQL?

**GraphQL** is a query language and runtime for APIs that provides a more efficient, powerful, and flexible alternative to REST APIs. Key features include:

- **Single Endpoint**: Unlike REST which uses multiple endpoints, GraphQL uses a single endpoint for all operations
- **Query Language**: Uses a declarative syntax to request exactly the data you need
- **Type System**: Strongly typed schema that defines the API structure
- **Real-time Subscriptions**: Built-in support for real-time data updates
- **Introspection**: APIs are self-documenting and explorable

## Step-by-Step Instructions

### Step 1: Create a GraphQL Request
1. Open Bruno and create collection with name **echo-graphql** from context menu
2. Create a new **GraphQL** request
3. Configure the request:
   - **Name**: `pokemon`
   - **URL**: `https://graphql-pokeapi.graphcdn.app/`
   - **Method**: `POST` (default for GraphQL)

### Step 2: Write the GraphQL Query
1. Navigate to the **Query** tab
2. Add the following GraphQL query:

```graphql
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

**Query Explanation:**
- `query`: Defines this as a read operation
- `pokemon(name: "pikachu")`: Calls the pokemon field with "pikachu" as argument
- `id, name, height, weight`: Request scalar fields
- `types { type { name } }`: Request nested object data

### Step 3: Execute the Request
1. Click the **Send** button to execute the GraphQL query
2. Wait for the response to load

### Step 4: Verify the Response
Check that your response matches the expected structure:

```json
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

## Expected Results
- **Response Status**: 200 OK
- **Response Structure**: Contains a `data` object with the requested Pokemon information
- **Pokemon Data**: Should include id, name, height, weight, and type information
- **Nested Data**: The `types` array should contain the Pokemon's type information
