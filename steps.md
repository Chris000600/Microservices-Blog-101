1. npx create-react-app client
2. posts & comments:
   `npm init -y`
   `npm i express cors axios nodemon`
3. posts & comments: edit start script, then run `npm start`
4. test posts on thunderclient
5. client: `npm i axios`, then try creating a post and check on thunderclient
6. event-bus:
   `npm i express nodemon axios`
7. query:
   `npm init -y`
   `npm i axios express cors nodemon`
8. moderation:
   `npm init -y`
   `npm i axios express nodemon`

How to run:
`npm start`

note:

- every time comments or posts are refreshed, the existing data will be lost

source:
https://www.udemy.com/course/microservices-with-node-js-and-react/

How it works:

1. Post created on React App (sends data to posts)
2. Posts service creates post and sends event to event-bus
3. Event bus sends out the event to every microservice
4. Event bus also saves a history of events
5. Query service takes the history of events and ensures data is up to date

6. Comment created on React App (sends data to comments)
7. Comments service creates comment with tag 'pending' and sends event to event bus
8. Event bus sends out the event to every microservice
9. Moderation service processes the new event and sends out the updated event to the event bus
10. Event bus sends out the event to every microservice
11. Query service updates the data on React
