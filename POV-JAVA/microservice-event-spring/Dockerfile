FROM maven:3.8.4-openjdk-17 AS builder
WORKDIR /event-app
COPY ./src ./src
COPY ./pom.xml .
RUN mvn clean package

FROM openjdk:17
VOLUME /tmp
ARG JAR_FILE=target/*.jar
COPY ${JAR_FILE} event-app.jar
ENTRYPOINT ["java","-jar","/event-app.jar"]
