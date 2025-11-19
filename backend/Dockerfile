FROM amazoncorretto:21 AS builder
WORKDIR /app
COPY target/movie-0.0.1-SNAPSHOT.jar app.jar
EXPOSE 80
ENTRYPOINT ["java", "-jar", "/app/app.jar"] 