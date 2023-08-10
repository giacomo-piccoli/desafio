# Base image
FROM openjdk:17-jdk

# Set working directory
WORKDIR /app

# Copy the application JAR file
COPY target/myapp.jar .

# Set the entrypoint command
ENTRYPOINT ["java", "-jar", "myapp.jar"]
