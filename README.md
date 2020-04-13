# nu-bank-authorizer

Note: pdf uploaded was converted to an image to avoid indexation and keep it as private as possible.

## Run
```
cat operations
docker-compose run authorize < operations
```
## Re Build
```
docker-compose up --build authorize
```

## Development
In order to develop this project you will need:
- JDK 8
- Maven 3

```
mvn package
java -jar ./target/authorize.jar < operations
```

## code design choices

- **Language**: I chose Java because it is a language that I use in the company I am working on. It is stable and has great performance along with extensive documentation.
- **Build**: Maven.
- **JSON Analyzer**: I choose Jackson based on some articles I read (for example, https://www.baeldung.com/java-json). In short, Jackson has the best performance when working with large files.
- **Tests**: I choose Junit + Mockito because they are well known.
- **Patterns**: I followed the SOLID patterns , program to an interface instead of an implementation, and dependency injection
- **Domain Logic**: With respect to transactions, I assumed that each transaction is chronologically in order.
- **Domain Logic**: The rules could be executed asynchronously, but I assumed that the authorization of a transaction is a Boolean value, yes or no, therefore, if one rule fails, it is not necessary to verify the rest. The priority of the rule was based on its complexity.

## complete solution (private)

https://gitlab.com/joseboretto/nu-bank-authorizer




