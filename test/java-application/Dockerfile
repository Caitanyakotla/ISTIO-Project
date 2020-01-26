FROM openjdk
EXPOSE 8080
WORKDIR /
COPY java-webserver.jar /java-webserver.jar
CMD ["/usr/bin/java", "-jar", "-Dspring.profiles.active=default", "java-webserver.jar"]