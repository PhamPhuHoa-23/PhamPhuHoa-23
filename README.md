# Design Document

By YOUR NAME HERE

Video overview: <https://youtu.be/zebwFSmUTro>

## Scope

In this section you should answer the following questions:

* What is the purpose of your database?
I take an idea while using my facebook accounts and I think why shouldn't I try to recreate Facebook database. And that my purpose, for searching information about friends, knowing more about hobbies, review the conversation and more things you can do with my database!
* Which people, places, things, etc. are you including in the scope of your database?
All people using Facebook may need it. But I build kinda simple so I'll improve in the future!
* Which people, places, things, etc. are *outside* the scope of your database?
May be someone who not care about social media, or may be Doctor may not need to you mine database, there so many of them. But thanks for the questions.

## Functional Requirements

In this section you should answer the following questions:

* What should a user be able to do with your database?
Search data; add user, friends; see how many reaction; analyzing reaction; search the chat conversation; review some notifications; find the song in some story, find images either; keep track of so many shared, password, and username, user describe; post a status to the database, keeping track of it; comment in the status, or react story. There so many things you can do with this database
* What's beyond the scope of what a user should be able to do with your database?
For example, create a group chat or communities in Faceebook.

## Representation

### Entities

In this section you should answer the following questions:

* Which entities will you choose to represent in your database?
To tell, it is a lot of them
 * Users
 * Status
 * Story
 * Image
 * Song
 * Reaction
 * Comment
 * Friend
 * Conversation
 * Calling
 * Notifications
* What attributes will those entities have?
For example the message entity
 * messages
  1. message_id: identify for message
  2. content inside of the message.
  3. status: like 'seen', 'send', 'error-send'.
 * to_message
  1. from_user_id: the user id of the person who sending the message.
  2. to_user_id: the user id of the person who receiving the message.
  3. message_id: identify for message.
  4. datetime: when the message is sending.
* Why did you choose the types you did?
 * messages
  1. id: INT(PRIMARY KEY)
  2. content: TEXT NOT NULL
  3. status: TEXT NOT NULL CHECK("status" IN ('seen', 'send', 'error-send'))
* Why did you choose the constraints you did?
Because sometime, I just want to processing the inforamtion that I need to, if it noise, there is so difficult to analyzing any data.

### Relationships

In this section you should include your entity relationship diagram and describe the relationships between the entities in your database.
![ER Diagram](diagram.png)

## Optimizations

In this section you should answer the following questions:

* Which optimizations (e.g., indexes, views) did you create? Why?
I choose both indexes and views
 1. Example of Indexes
 ```
 CREATE INDEX "search_by_name" ON "users"("first_name", "last_name");
 ```
 2. Example of Views
 ```
 CREATE VIEW "secure_user" AS
 SELECT "id", "first_name", "last_name", 'Ambigious' AS "password" FROM "users";
 ```
Because indexes will help me search more faster with a B-Tree Structure, and Views may be that me more time to run, but it's simplify the query i want to write, and basicly storing views is storing a scripts, it's don't take so much of my memory so I choose to balance between two these things.


## Limitations

In this section you should answer the following questions:

* What are the limitations of your design?
I think that it's so much simple than the original ones. Limits me about the time to run the code, time to insert although i try to not create so many indexes but it's slowdown the insert time. The search time may optimiz with indexes but to many nested queries and view combine together, it's still take a lot of time. My design are not precisely enough like the user_describe, it's should have more information. Or may be for users password, it's may have a better way to store and keep track of it. Or the same with message structure. Status limit the users to comment something like sticker or GIFs. Or story doesn't good enough when keep track of the time its upload. More shortcoming, but I'll try to improve this structure in the future
* What might your database not be able to represent very well?
I may say that because of its structure not optimizing enough and also by me who haven't have enough experience in this domain.

## Mini Game
BESIDE I INSERT SOME DATA THAT MIGHT YOU GET INTERSRTED TO. IT BASED ON THE IDEAOF FIFTYVIILAGE. I CREATE SMALL STORY ABOUT ALL MY TEDDY AND EACH OWN HAVE THEIR NAME, THEIR ABOUT 30 OF THEM BUT I CANNOT WRITE IT ALL TO THE INSERT BECAUSE I AM TOO LAZY, EACH ONE HAVE THEIR OWN ELEMENT MAGIC

Hint: Youu should check all the post that exist in the database with two name in the question!

* GUESS ELEMENT MAGIC OF:

 1. QUESTION 1: "ANH TRAU"
-- A. FIRE ---- B. LIGHT ---- C. THUNDER ---- D. WATER

 2. QUESTION 2: "ANH BI"
-- A. FIRE ---- B. LIGHT ---- C. THUNDER ---- D. WATER

JUST A SMALL GAME FOR UNDERSTANDING MY STRUCTURE. THANKS ALL OF YOU GUYS!!! MOAHZ~~~
