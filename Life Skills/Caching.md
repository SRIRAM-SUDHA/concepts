# Caching

## What is caching?

 - Caching is a technique to temporarily store the frequently accessed data in a storage called a cache.

 - It's improved the performance of the application and reduced the load on the server.

<img width="1157" height="527" alt="image" src="https://github.com/user-attachments/assets/c463fedf-67c3-43bf-a059-dcacdcb85a62" />

## How does the caching work?

 - Mostly, web applications store their data in the database. When an application needs data, it fetches data from the DB by doing

   HTTP requests and I/O operations, which makes the application lazy. To minimize this laziness in the application, the thought of storing data in the application arises.

   which is good for small applications, but for dynamic loading and big applications like Flipkart, it's a bad idea.

 - Storing the frequently accessed data temporarily in the server or client comes, and that is called caching, and

   Various cache techniques are being used in application development today.

## Types of Caching Strategies

  1. Cache-Aside

  2. Read-Through

  3. Write-Through

  4. Write-Back

### Commonly Used Words 

  - Cache hit: When the data required by the application is already located in the cache, then it's called a cache hit.

  - Cache miss: when the data required by the application is not located in the cache and the application needs to make a server call

    Then it's called a cache miss.

    

### Cache-Aside

 - This is also called lazy loading, and it's the most commonly used strategy. In this strategy, the application  is responsible for managing the cache and the database.

 - When the application needs the data, it first checks the cache. If it's a cache hit, it gets data from there. else

    The application needs to fetch the data from the database and store it in the cache for future purposes.

### Read-Through

 - In this strategy, the cache sits between the application and the database.

 - The application interacts with the cache, and the cache is responsible for providing data to the application.

 - When the application asks to cache the data, if it has it, it will provide it; otherwise, the cache itself fetches the data.

    from the database and store it for future purposes, then return the data to the application

### Write-Through

 - The strategy is to keep the cache and the database in sync. When an application writes data, it writes data both in

    cache and database simultaneously

 - The application writes the data in the cache, which is simultaneously written in the database. The write operation is completed when
    Both the cache and the database are in sync.
   
### Write-Back

  - This is also called a write-behind strategy.

  - The application writes the date in the cache first and sets it as completed.

    Thereafter, the cache is responsible for updating the data in the database asynchronously.


#### References 
 - [Reference 1](https://www.geeksforgeeks.org/system-design/caching-system-design-concept-for-beginners/)
 - [Reference 2](https://docs.aws.amazon.com/whitepapers/latest/database-caching-strategies-using-redis/caching-patterns.html)
 - [Reference 3](https://www.designgurus.io/answers/detail/what-is-read-through-vs-write-through-cache)

