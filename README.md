# Zen Class Programme - MongoDB Database Design

## Overview
This project involves designing a MongoDB database for the **Zen Class Programme** and writing queries to retrieve specific data from collections.

## Database Collections
The database consists of the following collections:
- `users`
- `codekata`
- `attendance`
- `topics`
- `tasks`
- `company_drives`
- `mentors`

## Queries and Requirements

use zenclass
switched to db zenclass

1.Find all the topics and tasks which are thought in the month of October
db.topics.find({month:"october"})

2.Find all the company drives which appeared between 15 oct-2020 and 31-oct-2020

db.company_drives.find({date:{$gt:new Date("2020-10-15"),$lt:new Date("2020-10-31")}})


3.Find all the company drives and students who are appeared for the placement.

db.company_drives.find().forEach(function(value){
    print("Company Name : "+value.company_name);
    print("Students Appeared : "+value.students_appeared);
})
Company Name : undefined
Students Appeared : undefined

4.Find the number of problems solved by the user in codekata

db.codekata.find().forEach(function(value){
    print("Name : "+value.user_name);
    print("Problems Solved : "+value.problems_solved)
})
Name : undefined
Problems Solved : undefined


5.Find all the mentors with who has the mentee's count more than 15

db.mentors.find({mentees_count:{$gt:15}})

6.Find the number of users who are absent and task is not submitted  between 15 oct-2020 and 31-oct-2020

    db.usertask.find({date:{$gt:new Date("2020-10-15"),$lt:new Date("2020-10-31")}}).forEach(function(value){
    print("Name : "+value.user_name);
    print("Attendance :"+value.attendance);
    print("Task : "+value.task_submission)
})
```

## Tech Stack
- **Database:** MongoDB
- **Query Language:** MongoDB Query Language (MQL)

## How to Run
1. Install MongoDB and start the MongoDB server.
2. Import the collections into your MongoDB instance.
3. Run the provided queries in a MongoDB shell or MongoDB Compass.

## Contributing
Contributions are welcome! Feel free to fork the repository and submit a pull request.

## License
This project is open-source under the **MIT License**.

