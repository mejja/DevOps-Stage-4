# Build stage
FROM maven:3.8.6-openjdk-11 AS builder
WORKDIR /app
COPY pom.xml .
RUN mvn dependency:go-offline
COPY src ./src
RUN mvn package -DskipTests

# Final stage
FROM openjdk:8-jdk-slim
WORKDIR /app
# Copy and rename the JAR for consistency
COPY --from=builder /app/target/*.jar ./users-api.jar
EXPOSE 8083
CMD ["java", "-jar", "users-api.jar"]
