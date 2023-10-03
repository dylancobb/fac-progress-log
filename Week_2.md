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

> Beth

> Excellent job using environment variables for database initialisation! As a next step, consider diving deeper into managing and securing environment variables, especially when deploying to various environments 💥

> Another team used multiple joins to access data from multiple tables. Here is the code:
const select_venue_info = db.prepare(/*sql*/ `
    SELECT
        v.name AS venueName,
        l.street AS address,
        l.name AS borough,
        l.postcode AS postcode,
        GROUP_CONCAT(c.name, ', ') AS cuisines
    FROM venue AS v
    JOIN location AS l ON v.location_id = l.id
    LEFT JOIN venue_cuisine AS vc ON v.id = vc.venue_id
    LEFT JOIN cuisine AS c ON vc.cuisine_id = c.id
    GROUP BY v.id
`);
Here is a breakdown of the join statements:
JOIN location AS l ON v.location_id = l.id: Joins venue with the location table based on matching location_id and id in venue and location respectively.
LEFT JOIN venue_cuisine AS vc ON v.id = vc.venue_id: Performs a LEFT JOIN with venue_cuisine where the id in venue matches venue_id in venue_cuisine.
LEFT JOIN cuisine AS c ON vc.cuisine_id = c.id: Further joins cuisine table where cuisine_id in venue_cuisine matches id in cuisine.

Hopefully this provides you with some inspiration for using joins in the future! 

