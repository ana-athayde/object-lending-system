# Object Lending Project

This repository contains a Java prototype for a peer-to-peer object lending system. The project explores how people can borrow items they only need occasionally, reducing the need to buy infrequently used tools and other goods. It was developed for the Software Engineering course (SOFT003), with an emphasis on requirements, domain modeling, and unit testing.

## Project Scope

The product concept is a community lending application. Its proposed features include publishing item requests with a distance limit and suggested dates, notifying nearby users, arranging handoffs, confirming returns, and maintaining user profiles and reviews. The requirements also call for safety guidance, prohibited-item rules, and a maximum lending radius.

These are product requirements, not all implemented application features. The current repository is a small Java domain-model and testing prototype: it has no map, notification service, chat interface, persistence layer, or production login system. The `App` entry point currently prints a greeting.

## Current Domain Model

The main source package is `com.example`. Its classes represent users, loans, categories, dates, images, messages, and reviews. The `Emprestimo` (loan) model implements these lifecycle states:

| State | Meaning |
| --- | --- |
| `1` | Requested |
| `2` | In progress |
| `3` | Completed |
| `4` | Cancelled |

A loan starts as requested. It can be started with a lending user and location, confirmed as completed with its confirmation code, or cancelled unless it is already completed or cancelled.

## Tests

JUnit 5 tests cover loan initialization and lifecycle rules, invalid loan transitions, confirmation-code validation, and login validation for incorrect user IDs or passwords.

## Requirements

- Java 8 or later
- Apache Maven 3.6.3 or later

## Build and Run Tests

From the Maven project directory:

```bash
cd SOFT/demo
mvn test
```

To run the current application entry point:

```bash
mvn compile
java -cp target/classes com.example.App
```

## Repository Layout

```text
SOFT/
	demo/
		pom.xml                 Maven configuration and dependencies
		src/main/java/          Application and domain model
		src/test/java/          JUnit tests
	diagrama/                 Project diagram
```

