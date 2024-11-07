# Use OpenJDK 11 as the base image
FROM openjdk:11-jre-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the Spring Boot JAR file into the container
COPY target/cardatabase-0.0.1-SNAPSHOT.jar /app/my-app.jar

# Expose the port your app will run on (default is 8080 for Spring Boot)
EXPOSE 8080

# Run the Spring Boot application
CMD ["java", "-jar", "/app/my-app.jar"]
