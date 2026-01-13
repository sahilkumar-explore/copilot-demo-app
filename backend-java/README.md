# backend-java ☕

## Overview

A small Spring Boot demo application (Maven). The project is configured to use Java 17 and serves HTTP endpoints via Spring Web. The default server port is `8080` (see `src/main/resources/application.properties`).

## Prerequisites 🔧

- Java JDK 17+ (verify with `java -version`)
- Maven 3.6+ (verify with `mvn -v`)
- Optional: an IDE (IntelliJ IDEA, Eclipse, VS Code + Java extension)

## Project layout 📁

- `pom.xml` — Maven project file (Java 17 is configured)
- `src/main/java` — application source code
- `src/main/resources/application.properties` — configuration (server.port)
- `target/` — artifact output after running `mvn package`

## Build & Run ⚙️

From the `backend-java/` folder:

- Build and package:

```bash
# macOS / Linux (Maven wrapper)
./mvnw clean package
# Windows (cmd)
mvnw.cmd clean package
# or if you have Maven installed
mvn clean package
```

- Run with Maven:

```bash
# macOS / Linux (Maven wrapper)
./mvnw spring-boot:run
# Windows (cmd)
mvnw.cmd spring-boot:run
# or with installed Maven
mvn spring-boot:run
```

- Run the packaged JAR:

```bash
java -jar target/*.jar
```

- Override the server port at runtime:

```bash
# with Spring Boot CLI args
java -jar target/*.jar --server.port=9090
# or with spring-boot:run and passing args
# macOS / Linux (wrapper)
./mvnw spring-boot:run -Dspring-boot.run.arguments=--server.port=9090
# Windows (cmd)
mvnw.cmd spring-boot:run -Dspring-boot.run.arguments=--server.port=9090
# or with installed Maven
mvn spring-boot:run -Dspring-boot.run.arguments=--server.port=9090
```

Default URL: `http://localhost:8080`

Quick check:

```bash
curl http://localhost:8080/
```

## Tests 🧪

If tests are added, run them with:

```bash
# macOS / Linux (wrapper)
./mvnw test
# Windows (cmd)
mvnw.cmd test
# or with installed Maven
mvn test
```

## Docker (optional)

Example Dockerfile you can add for containerized runs:

```dockerfile
FROM eclipse-temurin:17-jdk-jammy
WORKDIR /app
COPY target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/app/app.jar"]
```

Build and run:

```bash
docker build -t backend-java .
docker run -p 8080:8080 backend-java:latest
```

## Troubleshooting & tips ⚠️

- Check Java & Maven versions (`java -version`, `mvn -v`).
- If the port is in use, override with `--server.port` as shown above.
- When changing configuration, restart the app to pick up changes.

---

## Contributing

Add tests, update the README, and consider adding CI (GitHub Actions) or a `docker-compose.yml` if you want to run multiple services together.

---

License: MIT
