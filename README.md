# Go GraphQL API with gqlgen

This is a simple GraphQL API written in Go using the [gqlgen](https://github.com/99designs/gqlgen) library. It was developed as part of the **FullCycle 3.0** course and demonstrates basic usage of GraphQL with mutations and queries for `Category` and `Course` entities.

## Features

- Create and list categories
- Create and list courses
- Query categories with their associated courses
- Query courses with their associated category
- Built with Go and gqlgen

## Technologies

- Go
- GraphQL
- gqlgen
- UUID for ID generation

## Getting Started

### Requirements

- Go 1.20+
- [gqlgen](https://gqlgen.com/getting-started/)
- A tool like Postman, Insomnia, or GraphQL Playground to test queries

### Install dependencies

```bash
go mod tidy
```

### Run the application

```bash
go run server.go
```

> This will start the server at `http://localhost:8080/`.

## GraphQL Usage

Use the following sample queries and mutations in the GraphQL Playground or your preferred tool:

### Create a Category

```graphql
mutation createCategory {
  createCategory(input: { name: "Test", description: "Category Test" }) {
    id
    name
    description
  }
}
```

### Create a Course

```graphql
mutation createCourse {
  createCourse(input: { name: "Course", description: "Course Test", categoryId: "ebde21a5-9da8-476a-8c8b-50edb5c99e85" }) {
    id
    name
  }
}
```

### List all Categories

```graphql
query queryCategories {
  categories {
    id
    name
    description
  }
}
```

### List Categories with Courses

```graphql
query queryCategoriesWithCourses {
  categories {
    id
    name
    description
    courses {
      id
      name
      description
    }
  }
}
```

### List all Courses

```graphql
query queryCourses {
  courses {
    id
    name
    description
  }
}
```

### List Courses with Category

```graphql
query queryCoursesWithCategory {
  courses {
    id
    name
    description
    category {
      id
      name
    }
  }
}
```

## License

This project is for educational purposes and part of the FullCycle 3.0 course.