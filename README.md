# DMIT2015 – Jakarta Data: Human Resources Demo

## Overview

This project is a guided classroom demonstration of Jakarta Data repositories with Hibernate in a Jakarta EE 11 application.

We will use the **Oracle Human Resources (HR) sample database schema** to generate Jakarta Persistence entities, create Jakarta Data repository interfaces, and build a Jakarta Faces application for searching employees.

This lesson prepares you for **Assignment 4**, which uses similar techniques with the Oracle Customer Orders (CO) database schema.

## Learning Objectives

By the end of this lesson, you should be able to:

- Explain how Jakarta Data differs from Jakarta Persistence.
- Generate JPA entities from existing database tables using IntelliJ IDEA.
- Define Jakarta Data repository interfaces using `@Repository`.
- Create automatic query methods using `@Find`.
- Write parameterized queries using `@Query`.
- Filter, sort, and join related entity data.
- Use `JOIN FETCH` to retrieve associations required by a Faces page.
- Build a PrimeFaces AutoComplete search interface with a Faces Converter.

## Development Environment

- IntelliJ IDEA Ultimate
- JDK 25
- Jakarta EE 11
- WildFly 40
- Hibernate ORM / Jakarta Data
- Oracle Database 23ai Free
- Jakarta Faces, PrimeFaces, and OmniFaces
- Maven

Use the dependencies and versions provided in this starter project.

## Getting Started

### 1. Start Oracle Database

Start the Oracle container on the course Ubuntu Desktop VM:

```bash
podman start dmit2015-oracle-free-lite
```

Check its status:

```bash
podman ps
```

### 2. Open the Project

Open the project in IntelliJ IDEA Ultimate and allow Maven to load the dependencies.

Review the following configuration files:

- `pom.xml`
- `ApplicationConfig.java`
- `persistence.xml`
- `jboss-deployment-structure.xml`, if provided

Confirm that the application uses the Oracle Human Resources datasource and the `oracle-hr-jpa-pu` persistence unit.

### 3. Connect to the Human Resources Database

In IntelliJ IDEA's Database tool window, configure or select the Oracle Human Resources datasource.

Use the Oracle connection information provided in the lesson slides.

Test the connection before proceeding.

## Classroom Activities

### Part 1 – Database-First Entity Generation

Use IntelliJ IDEA's **Create JPA Entities from DB** feature.

Generate the entity classes and relationships from the Oracle HR schema into:

`dmit2015.entity`

Inspect the generated entities and their relationships.

### Part 2 – Jakarta Data Repositories

Create a `HumanResourcesRepository` interface in:

`dmit2015.repository`

Practice repository operations using `@Find` and `@Query`.

Explore queries that filter employees, sort results, and retrieve related departments, jobs, and managers.

### Part 3 – Employee Search

Build a Jakarta Faces page that allows users to search for employees by department name.

Implement:

- PrimeFaces AutoComplete for department selection.
- A Faces Converter to convert the selected department into a `Department` object.
- A CDI backing bean that uses the Jakarta Data repository.
- A PrimeFaces DataTable to display matching employees.

Display the following employee information:

- Full Name
- Hire Date
- Salary
- Department
- Manager

### Part 4 – Practice Exercise

Extend the Employee Search page to support searching by **Job Title** using another PrimeFaces AutoComplete component.

Use the existing Department Search implementation as a reference.

## Expected Outcome

At the end of the demonstration, the application should allow users to select a department and retrieve employees in that department.

After completing the practice exercise, the application should also support searching for employees by job title.

## Connection to Assignment 4

This lesson uses the Oracle **Human Resources** schema.

Assignment 4 uses the Oracle **Customer Orders** schema to search for products and inventory across stores.

You will apply the same Database-First, Jakarta Data, AutoComplete, converter, and relationship-query concepts in Assignment 4.

**Do not substitute this classroom demo project for your Assignment 4 repository.**

## Reference Materials

- DMIT2015 – Jakarta Data lesson slides
- Assignment 4 specification and starter project
- Jakarta Data 1.0 specification
- Hibernate Data Repositories documentation