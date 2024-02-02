FROM maven:3.8-openjdk-8 as builder

LABEL maintainer="GautierHuver"

WORKDIR /usr/src/app

COPY . .

RUN mvn clean package -DskipTests=true

FROM openjdk:8-jdk

EXPOSE 8448

WORKDIR /usr/src/app

COPY --from=builder usr/src/app/target/*.jar back.jar

CMD ["java", "-jar", "back.jar"]
