# Self Studies: Object-Relational Mapping with JPA

## Overview

In this lesson you will refactor the `simple-crm` application to use a real database instead of an in-memory `ArrayList`. The self-study materials below will help you arrive with a clear understanding of what JPA is, how entity annotations work, and how database relationships are modelled — so you can focus on the code-along rather than catching up on concepts.

**Estimated Prep Time:** 60–80 minutes

---

## Task 1: Spring Data JPA and Hibernate

This video covers how to set up Spring Data JPA in a Spring Boot project, create entity classes with annotations, and use `JpaRepository` to perform CRUD operations without writing SQL. This maps directly to Parts 2, 3, and 4 of the lesson.

**Watch:** Spring Boot JPA and Hibernate Tutorial
🎬 https://www.youtube.com/watch?v=wQLva08PcJY

**Then read:** Lesson 3.16 — Parts 1 to 4

**Guiding Questions:**
- What is the difference between JPA and Hibernate?
- What does the `@Entity` annotation tell Spring Boot?
- What is a primary key and why does every database table need one?
- What does `JpaRepository` give us that our old `CustomerRepository` class did not?

---

## Task 2: JPA Relationships — ManyToOne and OneToMany

This video explains how to model relationships between entities in JPA — specifically many-to-one and one-to-many — and how foreign keys work under the hood. This maps directly to Part 5 of the lesson.

**Watch:** JPA Relationships — OneToMany and ManyToOne
🎬 https://www.youtube.com/watch?v=DsVy8XG2UNc

**Then read:** Lesson 3.16 — Part 5

**Guiding Questions:**
- What is a foreign key and how does it link two database tables?
- What does `@ManyToOne` mean in plain English?
- Why do we use `@JoinColumn` and what does it specify?
- What is a nested route and when would you use one?

---

## Active Engagement Strategies

- After watching the first video, try to list all the annotations you will need to convert the `Customer` class into a JPA entity — write them from memory before checking the lesson
- After watching the second video, sketch a simple diagram showing the relationship between the `Customer` and `Interaction` tables, including the foreign key column
- Before class, make a copy of your `simple-crm` project so you can freely refactor without worrying about breaking your previous work

---

## Additional Reading Material

- [JPA Entity Annotations — Baeldung](https://www.baeldung.com/jpa-entities)
- [Spring Data JPA Repository — Baeldung](https://www.baeldung.com/the-persistence-layer-with-spring-data-jpa)
- [JPA Many-To-One Relationship — Baeldung](https://www.baeldung.com/hibernate-one-to-many)
- [H2 Database with Spring Boot — Baeldung](https://www.baeldung.com/spring-boot-h2-database)