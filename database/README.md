# Pivotal Agency Database Style Guide

This style guide is intended for use when creating new database schemas.

## Table of Contents

1. [Naming](#naming)
    - [Database](#database)
    - [Table](#table)
    - [Columns](#columns)
1. [Field Types](#field-types)
1. [Indexes](#indexes)


## Naming

### Database

Database names must use `snake_case` and be lowercase. They should describe the application / project.

Example:

  - acme_dashboard
  - projects_system

If a new version of a database is required, use version numbers (eg. `projects_system_3`).

If a backup of a database was created, use the `backup` designator (eg. `projects_system_3_backup`).


### Table

Table names must use `snake_case`, be lowercase and use plural names of the entity they represent. They should clearly describe the data they contain.

Example:

  - clients
  - weight_logs

If a backup of a table was created, use the `backup` designator (eg. `weight_logs_backup`).


### Columns

Column names must use `snake_case`, be lowercase and use singular names of the value they represent. They should clearly describe the data they contain.

Example:

  - firstname
  - created_at

Do not prefix column names with the table name (eg. `task_created_at`).

Primary key columns should be `id`.

Foreign key columns should use the name of the entity ending with `_id` (eg. `client_id`). In some circumstances using a different name would be more meaningful (eg. `created_by_id`, which is a foreign key of `users` table).

When storing boolean data use the `is_` prefix (eg. `is_completed`).


## Field Types

Stick to well-known field types:

  - `CHAR` / `VARCHAR`
  - `TEXT` / `LONGTEXT`
  - `INTEGER`
  - `DECIMAL`
  - `DATE` / `DATETIME`

Only use more exotic types when absolutely warranted (eg. `GEOMETRY`, for performance reasons).

When storing boolean data use the `INTEGER(1)` type. If the data represents an action ("true" when task is complete) consider if a nullable-datetime field would be suitable. If so, simply save the datetime when that action occurs. In this case a `null` value represents `false`, and a datetime represents `true`.


## Indexes

Wherever possible, set a primary key (eg. `id`).

Fields which are frequently used in `WHERE`, `JOIN` and `GROUP BY` statements and contain recurring values should be indexed (eg. `client_id` in `tasks` table). This will increase performance.

Do not index columns with unique data (eg. text input from users).

You may use foreign key constraints as needed.
