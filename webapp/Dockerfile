FROM openjdk:8-jdk-alpine as build-env
WORKDIR /app
COPY app ./
RUN ./gradlew bootRepackage


FROM openjdk:8-jre-alpine
WORKDIR /app
COPY --from=build-env /app/build/libs/app*.jar app.jar
# ENTRYPOINT ["java", "-jar", "app.jar"]
CMD ["java", "-jar", "app.jar"]
