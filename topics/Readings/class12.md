# Class 12 reading: 
# Spring MVC Controllers and Data Repositories JPA. 
# Spring Data JPA Query Methods and Annotations

## Query Methods in Spring Data JPA

In Spring Data JPA, query methods are defined by declaring method signatures in a repository interface. These query methods follow a naming convention that allows Spring Data JPA to automatically generate the corresponding database queries. For instance, if you have an entity called `Customer` with a field named `lastName`, you can define a query method like this:

```java
List<Customer> findByLastName(String lastName);
```

This method declaration tells Spring Data JPA to generate a query to find all customers with the specified last name.

## Dependencies for the Spring Guide

To complete the Spring guide described in the text, you will need the following dependencies:

- **Spring Boot Starter Data JPA:** This dependency provides Spring Data JPA and the necessary infrastructure for working with JPA repositories.

- **H2 Database:** The H2 in-memory database is used for demonstration purposes in the guide.

- **Spring Boot Starter Web:** This starter is used for building web applications with Spring MVC.

## Annotations for Auto-Generated Identification Number

When working with Spring Data JPA, you can use annotations to specify an auto-generated identification number for an entity. The key annotations are:

- `@Id`: This annotation marks a field as the primary key of the entity.

- `@GeneratedValue`: This annotation specifies the strategy for generating values of the primary key field. For example, `@GeneratedValue(strategy=GenerationType.AUTO)` indicates that the ID should be generated automatically.

Here's an example of their usage:

```java
@Entity
public class Customer {

  @Id
  @GeneratedValue(strategy=GenerationType.AUTO)
  private Long id;

  // Other fields and methods...
}
```


# Spring Data Repository Interfaces

## Overview
In this quick article, we’ll focus on different kinds of Spring Data repository interfaces and their functionality. We’ll touch on:

- CrudRepository
- PagingAndSortingRepository
- JpaRepository

Simply put, every repository in Spring Data extends the generic Repository interface, but beyond that, they each have different functionality.

## Spring Data Repositories
Let’s start with the JpaRepository – which extends PagingAndSortingRepository and, in turn, the CrudRepository.

Each of these defines its functionality:

- CrudRepository provides CRUD functions
- PagingAndSortingRepository provides methods to do pagination and sorting of records
- JpaRepository provides JPA-related methods such as flushing the persistence context and deleting records in a batch

And so, because of this inheritance relationship, the JpaRepository contains the full API of CrudRepository and PagingAndSortingRepository.

When we don’t need the full functionality provided by JpaRepository and PagingAndSortingRepository, we can use the CrudRepository.

Here's a simple example:

```java
@Entity
public class Product {

    @Id
    private long id;
    private String name;

    // getters and setters
}

@Repository
public interface ProductRepository extends JpaRepository<Product, Long> {
    Product findByName(String productName);
}
```

## CrudRepository
The CrudRepository interface provides typical CRUD functionality:

- `save(…)` – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch.
- `findOne(…)` – get a single entity based on passed primary key value.
- `findAll()` – get an Iterable of all available entities in the database.
- `count()` – return the count of total entities in a table.
- `delete(…)` – delete an entity based on the passed object.
- `exists(…)` – verify if an entity exists based on the passed primary key value.

## PagingAndSortingRepository
The PagingAndSortingRepository interface extends CrudRepository and provides methods for pagination:

- `findAll(Sort sort)` – get entities sorted by the provided condition.
- `findAll(Pageable pageable)` – get entities with pagination.

## JpaRepository
The JpaRepository interface provides additional methods, including:

- `findAll()` – get a List of all available entities in the database.
- `findAll(…)` – get a List of all available entities sorted using the provided condition.
- `save(…)` – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch.
- `flush()` – flush all pending tasks to the database.
- `saveAndFlush(…)` – save the entity and flush changes immediately.
- `deleteInBatch(…)` – delete an Iterable of entities. Here, we can pass multiple objects to delete them in a batch.

## Downsides of Spring Data Repositories
Beyond all the very useful advantages of these repositories, there are some basic downsides of directly depending on these as well:

- We couple our code to the library and to its specific abstractions, such as `Page` or `Pageable`; that’s, of course, not unique to this library – but we do have to be careful not to expose these internal implementation details.
- By extending, e.g., `CrudRepository`, we expose a complete set of persistence methods at once. This is probably fine in most circumstances as well, but we might run into situations where we’d like to gain more fine-grained control over the methods exposed, e.g., to create a ReadOnlyRepository that doesn’t include the `save(…)` and `delete(…)` methods of `CrudRepository`.
