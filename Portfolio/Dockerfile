# Use Eclipse Temurin (Java 17 LTS)
FROM eclipse-temurin:17-jdk

# Set working directory
WORKDIR /app

# Copy Maven wrapper files
COPY .mvn/ .mvn
COPY mvnw pom.xml ./

# Resolve dependencies
RUN ./mvnw dependency:resolve

# Copy the full project
COPY . .

# Build the JAR (skip tests for speed)
RUN ./mvnw clean package -DskipTests

# Run the Spring Boot application
CMD ["java", "-jar", "target/portfolio-0.0.1-SNAPSHOT.jar"]

