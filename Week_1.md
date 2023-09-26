## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/server/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
 
 #### Conditionally set ports for our server based on the runtime environment

- By creating a constant PORT and *assigning* it `process.env.PORT`, the port the server runs on can be set via an environmental variable when starting the server, e.g. `PORT=7777 node index.js`. If no environmental variable is passed in, then `process.env.PORT` will be `undefined`, which evaluates to **falsey** and PORT will be assigned the value of 3000 as well due to the OR operator `||`.
```js
const PORT = process.env.PORT || 3000;
server.listen(PORT, () => console.log(`listening at http://localhost:${PORT}`));
```

 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
 #### Write tests with the built-in Node Test Runner

- Writing back-end tests turned out to be a lot more complicated an affair than the simple synchronous function tests for javascript code running in the browser I'd done up to this point. It was a very productive experience though, and I'll keep practicing!

## Feedback
#### Mark Hanley
- Mark was super helpful, and very knowledgable whenever we ran into technical difficulties.

> Beth

> You’ve demonstrated a solid understanding of environment variables and server configuration ⚡️

> Consider taking on the QA role in a future project. A good place to start is selecting a simple server route within the project and writing tests for it independently. You can also explore asynchronous testing. Practice handling asynchronous code, using tools like async/await or promises, to ensure your tests can handle real-world scenarios effectively 🦑

