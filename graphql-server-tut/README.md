# Working Graphql

- Up to date node, node.js, npm (could use yarn)

```
npm -v
7.24.0

$ node -v
v16.10.0
```
## Steps
```
mkdir graphql-server-tut
cd graphql-server-tut

npm init -y # to initialise npm and create package.json

npm install apollo-server graphql
```

- Details are outlined in file `index.js`
- run `index.js` via `node index`
- port 8080 on localhost shows the Graphql interface.

## To avoid
```
npm install --save-dev graphpack
```
https://www.freecodecamp.org/news/a-beginners-guide-to-graphql-86f849ce1bec/

The above caused circular errors - attempting to fix in package.json didn't work
- error was
```
import { ApolloServer, gql } from 'apollo-server'; 
^^^^^^ SyntaxError: Cannot use import statement outside a module
```

## Adding a mutation
```
mutation($firstName: String!, $lastName: String!, $email: String!) {
  addUser(firstName: "gerry", lastName: "Smyth", email: "gerry@gerry.com") {
    email
    firstName
    lastName
  }
}
```
produces
```
mutation($firstName: String!, $lastName: String!, $email: String!) {
  addUser(firstName: "gerry", lastName: "Smyth", email: "gerry@gerry.com") {
    email
    firstName
    lastName
  }
}
```

## References
- https://medium.com/techtalkers/a-beginners-guide-to-graphql-12d60d3fba03