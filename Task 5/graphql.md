## Scheme

type Query {
    client(id: ID!): Client
    documents(id: ID!): [Document]
    relatives(id: ID!): [Relative]
}

type Client {
    id: ID!
    name: String!
    age: Int
    documents: [Document]
    relatives: [Relative]
}

type Document {
    id: ID!
    type: String!
    number: String!
    issueDate: String!
    expiryDate: String!
}

type Relative {
    id: ID!
    relationType: String!
    name: String!
    age: Int!
}


## Queries

<!-- Получить основную информацию о клиенте -->
query {
  client(id: "{id}") {
    id
    name
    age
  }
}

<!-- Получить список документов клиента -->
query {
  documents(id: "{id}") {
    id
    type
    number
    issueDate
    expiryDate
  }
}

<!-- Получить информацию о родственниках клиента -->
query {
  relatives(id: "{id}") {
    id
    relationType
    name
    age
  }
}

