#jdk-11 исходя из README самого проекта
# FROM maven:3.6.3-jdk-11 AS build 

#jdk-21 по требованию из 2 части задания... в любом случае работают оба))
FROM maven:3.9.9-ibm-semeru-21-jammy 

WORKDIR /app

COPY ./src ./src
COPY ./pom.xml ./

RUN mvn clean package

FROM openjdk:11-jre-slim

WORKDIR /app

COPY --from=build /app/target/*.jar ./

ENTRYPOINT ["java", "-jar", "./ipcounter-1.0.1.jar"]
CMD ["ipfile.txt", "false"]