FROM eclipse-temurin:17-jdk-jammy

WORKDIR /app

COPY demo/.mvn/ .mvn
COPY demo/mvnw demo/pom.xml ./

RUN ./mvnw dependency:resolve

COPY demo/src ./src

CMD ["./mvnw", "spring-boot:run"]