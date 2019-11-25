# ta-hours-queue
A website with queue functionalities to help teaching assistants (TAs) during their teaching assistant hours. This project was built with the intention to serve the Smith College Computer Science department, based on the needs I identified during my time as teaching assistant. This is a personal project done with guidance from [Professor Foley](https://jjfoley.me/) as a special studies course in my final semester (Fall 2019). It is not officially associated with the Smith College Computer Science department. Please feel free to adapt this project to your own needs (with due credit where necessary), and contact me with any questions.

# About the Project
## Background
The Smith College Computer Science department has teaching assistants (TAs) that have hours almost daily. During these hours, students who need help typically write their name on the board and are assisted in the order that they write their names. Once students are helped, they are typically erased off the board. This method of maintaining a "ta hours queue" can lead to a lot of problems, such as: 
* when TA hours are very crowded, students tend to write their name multiple times on the queue. There is no way to ensure fairness, and the queue is typically based on who was able to get to the classroom first. Sometimes, a large queue of students have already formed before TAs arrive. 
* there is no way for a student to measure how crowded TA hours are for a session. Most TA hours take place during night time, and sometimes students are required to treck through inclimate weather on a dark campus to TA hours only to find that the queue is beyond full. 
* there is no way to efficiently and effectively track how many students have gone to the TA hours session. This is especially important when it comes to justifying funding for TA horus to continue. TAs are manually filling out forms and tracking student names, which is sometimes forgotten when TA hours are especially crowded. 
* more: - lack of issues tracking, - unable to request a specific TA, - TAs unable to review what the student needs help with, before going to the student, -professors unable to determine what students struggled the most with, etc ... 

## Project Info
To address these issues, I've created this sqlite database backed queue. At its core is the queue functionality, where students can add their names to a queue and have their information saved to a database. Additionally, there is the added concept of sessions - a session represents a literal TA session (i.e. a 2 hour session for Intro to Computer Science teaching assistant hours). The main webpage populates with TA sessions created by TAs. Each session has a public key and a private key - the private key is needed to perform TA only functions (deleting names, clearing the queue, deleting the session, etc). The public key is needed to access the session and add entries to it. Each session can be deleted, and all entries on the queue of that session will be saved. There is also key saving - all keys that are connected to active sessions will be stored in localStorage, and the user can enter key pairings manually. These keys are automatically checked when performing TA only functions. Also, keys will automatically clear from the localStorage if the sessions they are connected to are no longer active.

### Queue
Here are some of the current functionalities of the queue (for student names):
Anybody can:
-add their name to the queue
TAs can: 
-delete a name off a queue 
-clear the entire queue (and thus, archiving all of the entries)
-check a name off as "complete"

### Session
Anybody can: 
-start a session (which will effectively give them all TA functions)
-add a public key and/or private key
TAs can:
-delete a session

# Author
Tiffany Xiao
