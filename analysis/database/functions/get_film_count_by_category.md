# Function: DEMO.get_film_count_by_category

## Description
This function takes a category name as input and returns the count of films in that category.

## Business Rules
- The function retrieves the count of films belonging to a specific category.
- It uses the `film`, `film_category`, and `category` tables to determine the count.

## Data Interaction Details
- The function joins the `film`, `film_category`, and `category` tables to establish the relationship between films and their categories.
- It filters the results based on the provided category name.
- The count of films is retrieved using the `COUNT(*)` aggregate function.

## Parameters
- `category_name` (IN): The name of the category for which the film count is requested.

## Code Metrics
- Lines of code: 11
- Number of joins: 2 (`film` -> `film_category`, `film_category` -> `category`)

## Logic Structure
1. Declare a variable `film_count` to store the count of films.
2. Execute a SELECT statement to retrieve the count of films in the specified category.
   - Join the `film`, `film_category`, and `category` tables.
   - Filter the results based on the provided `category_name`.
   - Store the count in the `film_count` variable.
3. Return the `film_count` value.

## Nested Elements
- The function does not contain any nested elements.

## Dependencies
- The function depends on the `film`, `film_category`, and `category` tables.

## Overview
The `get_film_count_by_category` function provides a way to retrieve the count of films belonging to a specific category. It takes a category name as input and returns the corresponding film count by joining the relevant tables and filtering the results based on the provided category name.

## Lineage Graph
```mermaid
graph LR
A[film] --> C[JOIN]
B[film_category] --> C
C --> D[JOIN]
E[category] --> D
D --> F[COUNT(*)]
F --> G[film_count]
```

## Complexity of the Function
The function has a simple structure with a single SELECT statement and two joins. It does not contain any loops or complex logic. The complexity of the function is relatively low, as it performs a straightforward count based on the provided category name.