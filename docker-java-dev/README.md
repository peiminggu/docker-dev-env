# Setup a Spring Boot development environment with Docker

No need to install Java or Spring boot in your local environment. Use the java docker image as your development environment. <br/>
With Visual Studio Code Dev Containers extension. VS Code can use the docker container as development environment, the codes can be referenced directly in the container by docker volumn. <br/>
Use Dev Containers remote window function, a VS Code session is connected to docker container environment

## Build Docker image

### build docker image

```
docker build -t my-spring-boot-image .
```

### run docker

```
docker run -d --name my-spring-boot-container -p 8080:8080 -v $(pwd)/demo:/app my-spring-boot-image
```

### docker compose

```
docker compose up -d
```

## Develop with Visual Studo Code

### Spring boot app setup

1. Add dev tool to pom.xml
```
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-devtools</artifactId>
        <optional>true</optional>
    </dependency>
```
2. Enable auto reload in application.properties
```
spring.devtools.livereload.enabled=true  
```

### Development steps

1. Remote Connect to docker container
2. Update java code
3. Recompile after code change
```
./mvnw compile
```
4. Spring dev tool would auto reload to refect the new changes