# Class 29 reading: Rooms Db

### What database engine is Room wrapped around? Do you think this is a good choice? Why or why not?

Room is built on SQLite, which is an excellent choice for Android due to its efficiency, ACID compliance, and portability. Room simplifies SQLite usage, making it a great option for most Android apps. Other databases may be better for specific use cases, but SQLite is a solid default choice.



### Do Rooms have any similarities to JPA?


Yes, Room has similarities to JPA (Java Persistence API) as both are used for data persistence and mapping 


### Describe a DAO in your own words

 Data Access Object, is a component that acts as an intermediary between an application and a database. It abstracts the database operations and provides methods for performing CRUD (Create, Read, Update, Delete) operations on the database. It helps maintain a separation of concerns in an application and makes it easier to work with the database.