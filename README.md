This project is a fork of the [https://github.com/apollographql/graphql-tutorial.git](https://github.com/apollographql/graphql-tutorial.git) project modified to support _**GraphQL Subscription**_ based on the awesome Apollo article [Tutorial: GraphQL Subscriptions on the Server](https://dev-blog.apollodata.com/tutorial-graphql-subscriptions-server-side-e51c32dc2951). 

This project got created to test GraphQL Subscription support for my [SchemaGlue](https://github.com/nicolasdao/schemaglue) project. SchemaGlue allows to nicely organize GraphQL schemas and resolvers across folders, and glue them back. 

# How To Run This Project
### Step 1 - Download client & Server Project & Load Dependencies
```
git clone https://github.com/nicolasdao/apollo-subscription-demo.git
cd apollo-subscription-demo
cd server && npm install
cd ../client && npm install
```
### Step 2 - Start GraphQL Server

Browse to your _apollo-subscription-demo_ folder and then run:
```
cd server
npm start
```

### Step 3 - Start Your Test Client

Open a new terminal and browse to your _apollo-subscription-demo_ folder and then run:
```
cd client
npm start
```

### Step 4 - Do Test

Open the GraphiQL client hosted on [http://localhost:4000/graphiql](http://localhost:4000/graphiql) and subscribe to a message as follow:

```
subscription {
  messageAdded(channelId: 1) {
    id
    text
  }
}
```

Open your test client hosted on [http://localhost:3000/channel/1](http://localhost:3000/channel/1) and add a new item:

![alt text](https://cdn-images-1.medium.com/max/1600/1*oYyCf2u9MNCikiAvlWwmiw.gif)

As soon as you've added that item, you should see your GraphiQL receiving an update:

![alt text](https://cdn-images-1.medium.com/max/1600/1*O8YVfjtXV44TAYsi7hTenA.gif)