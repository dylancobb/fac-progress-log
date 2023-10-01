## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/database/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
> **Set enviroment variables and understand their use case**
The database is initialised through an environmental variable—if none is provided, it will default to `db.sqlite`, which was the local database path we used.
```js
const Database = require('better-sqlite3')
const db = new Database(process.env.DB_FILE || 'db.sqlite')
```

 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> **Use joins to access related data in different tables**
> I didn't get enough of an opportunity to write join queries this week as my time was taken up with DevOps tasks. Next time, hopefully!

## Feedback  
> Zak was a helpful mentor when needed; he helped us sort out and understand several problems that arose over the course of the project.
