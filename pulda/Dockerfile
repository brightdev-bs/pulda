FROM openjdk:17 as build
RUN microdnf install findutils
COPY . /project
WORKDIR /project
RUN chmod 700 gradlew
RUN ./gradlew clean build
ARG JAR_FILE=./build/libs/pulda-0.0.1-SNAPSHOT.jar
RUN cp ${JAR_FILE} /app.jar
ENTRYPOINT ["java", "-jar", "/app.jar"]

