    # # Stage 1: Build with Maven and Java 21
    # FROM maven:3.9.6-eclipse-temurin-21 AS build

    # WORKDIR /app
    
    # # Install git to allow repo cloning
    # RUN apt-get update && apt-get install -y git
    
    # # Clone your backend repo
    # RUN git clone https://github.com/KadaliThanojKumar/DigitalWallet_BE.git .

    # RUN mvn clean package -DskipTests

    # # Stage 2: Run with Tomcat
    # FROM tomcat:9.0-jdk17-temurin

    # # Remove default apps
    # RUN rm -rf /usr/local/tomcat/webapps/*

    # # Copy backend WAR to Tomcat
    # COPY --from=build /app/target/*.war /usr/local/tomcat/webapps/back1.war

    # EXPOSE 8088
    # CMD ["catalina.sh", "run"]    

    # Stage 1: Build with Maven and Java 21
# FROM maven:3.9.6-eclipse-temurin-21 AS build
# WORKDIR /app

# # Install git
# RUN apt-get update && apt-get install -y git

# # Clone your backend repo
# RUN git clone https://github.com/KadaliThanojKumar/DigitalWallet_BE.git .

# # Build WAR
# RUN mvn clean package -DskipTests

# # Stage 2: Run with Tomcat
# FROM tomcat:9.0-jdk17-temurin
# RUN rm -rf /usr/local/tomcat/webapps/*

# # Copy WAR
# COPY --from=build /app/target/*.war /usr/local/tomcat/webapps/back1.war

# EXPOSE 8080
# CMD ["catalina.sh", "run"]


# # Stage 1: Build with Maven and Java 21
# FROM maven:3.9.6-eclipse-temurin-21 AS build
# WORKDIR /app

# # Install git
# RUN apt-get update && apt-get install -y git

# # Clone backend repo
# RUN git clone https://github.com/KadaliThanojKumar/DigitalWallet_BE.git .

# # Build WAR
# RUN mvn clean package -DskipTests

# # Stage 2: Run with Tomcat
# FROM tomcat:9.0-jdk17-temurin
# RUN rm -rf /usr/local/tomcat/webapps/*

# # Copy WAR as ROOT for root URL
# COPY --from=build /app/target/*.war /usr/local/tomcat/webapps/ROOT.war

# EXPOSE 8080
# CMD ["catalina.sh", "run"]


# # Stage 1: Build with Maven
# FROM maven:3.9.6-eclipse-temurin-21 AS build
# WORKDIR /app

# # Install git
# RUN apt-get update && apt-get install -y git

# # Clone backend repo
# RUN git clone https://github.com/KadaliThanojKumar/Digital-Wallet-Be.git .

# # Build WAR
# RUN mvn clean package -DskipTests

# # Stage 2: Run with Tomcat
# FROM tomcat:9-jdk17

# # Activate docker profile
# ENV SPRING_PROFILES_ACTIVE=docker

# RUN rm -rf /usr/local/tomcat/webapps/*

# # Copy WAR as ROOT.war
# COPY --from=build /app/target/*.war /usr/local/tomcat/webapps/ROOT.war

# EXPOSE 8088
# CMD ["catalina.sh", "run"]

# Stage 1: Build with Maven
FROM maven:3.9.6-eclipse-temurin-21 AS build
WORKDIR /app

# Install git
RUN apt-get update && apt-get install -y git

# Clone backend repo
#RUN git clone RUN git clone https://github.com/KadaliThanojKumar/Backend-dw.git .
RUN git clone https://github.com/KadaliThanojKumar/Backend-dw.git .


# Build WAR
RUN mvn clean package -DskipTests

# Stage 2: Run with Tomcat
FROM tomcat:9-jdk17

# Disable WAR unpacking (required for Spring Boot WAR)
ENV CATALINA_OPTS="-Dorg.apache.catalina.startup.ExpandWar=false"

# Activate docker profile
ENV SPRING_PROFILES_ACTIVE=docker

# Remove default apps
RUN rm -rf /usr/local/tomcat/webapps/*

# Copy WAR as ROOT
COPY --from=build /app/target/ROOT.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
