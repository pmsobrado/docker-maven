# docker-maven
Docker image to run your maven command against a defined path

[![](https://images.microbadger.com/badges/image/pasogo/maven-compilator.svg)](http://microbadger.com/images/pasogo/maven-compilator)   [![](https://images.microbadger.com/badges/version/pasogo/maven-compilator.svg)](http://microbadger.com/images/pasogo/maven-compilator)

## Build the image

Use ```docker pull pasogo/maven-compilator``` or build from docker-compose.yml using ```docker-compose build``` if you want to customize build arguments.

## Build arguments

```JAVA_VERSION``` -> Default: 7
```MVN_VERSION``` -> Default: 3.1.1

## Running container

```docker run -v PATH/WHERE/EXEC/COMMAND:/src -e COMMAND=MVN/COMMAND --name maven-compilator pasogo/maven-compilator```

Change ```PATH/WHERE/EXEC/COMMAND``` and ```MVN/COMMAND``` as you need.
