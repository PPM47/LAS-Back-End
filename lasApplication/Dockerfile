FROM maven:3-openjdk-17 AS build
COPY . .
RUN mvn clean package -DskipTests

FROM maven:3.8.1-openjdk-17-slim
COPY --from=build /target/LasApplication-0.0.1-SNAPSHOT.jar LasApplication.jar
ENTRYPOINT ["java", "-jar", "LasApplication.jar"]