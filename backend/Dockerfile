FROM maven:3.8.3-openjdk-17
COPY . /opt/
WORKDIR /opt
RUN mvn clean package 
WORKDIR target/
EXPOSE 8080
ENTRYPOINT ["java","-jar"]
CMD ["student-registration-backend-0.0.1-SNAPSHOT.jar"]

##MULTI-STAGE DOCKERFILE##
#stage-1 building stage
#FROM maven:3.10.2-eclipse-temurin-17-alpine AS bobthebuilder
#WORKDIR /app
#COPY . .
#RUN mvn clean package

#stage-2 application stage
#FROM eclipse-temurin:17-jre-alpine
#COPY --from=bobthebuilder /app/target/*.jar app.jar
#EXPOSE 8080
#CMD ["java","-jar","app.jar"]
