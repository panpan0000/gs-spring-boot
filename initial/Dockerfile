FROM maven as builder
COPY . /build
WORKDIR /build
RUN mvn package

FROM openjdk:8-jre
RUN mkdir -p /opt/jre/
COPY --from=builder /build/target/*.jar /opt/jre/
WORKDIR /opt/jre
ENTRYPOINT ["java", "-jar","gs-spring-boot-0.1.0.jar"] 

#https://github.com/spring-guides/gs-spring-boot
