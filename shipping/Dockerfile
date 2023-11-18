#multi stage builds
# FROM maven AS build

# RUN apt-get update -y && apt-get -y install maven
FROM maven AS build

WORKDIR /opt/shipping

COPY pom.xml /opt/shipping/
RUN mvn dependency:resolve
COPY src /opt/shipping/src/
RUN mvn package

#here multistage build is the process of reduding the size of the docker image , maven from above build have the JDK which is high storage ,whic
#which is not required in run time , so to build it we use maven , that contains (JDK+JRE) , then automatically , the above container is deleted, thus resulting in reduction of image size.

#Run

FROM openjdk:8-jre-alpine3.9

EXPOSE 8080

WORKDIR /opt/shipping

ENV CART_ENDPOINT=cart:8080
ENV DB_HOST=mysql

COPY --from=build /opt/shipping/target/shipping-1.0.jar shipping.jar

CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]

# FROM maven

# WORKDIR /opt/shipping

# COPY pom.xml /opt/shipping/
# RUN mvn dependency:resolve
# COPY src /opt/shipping/src/
# RUN mvn package
# ENV CART_ENDPOINT=cart:8080
# ENV DB_HOST=mysql
# CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "/opt/shipping/target/shipping-1.0.jar" ]

#here the above commented sections also creates the docker imagee but the size is high (This is single stage build)