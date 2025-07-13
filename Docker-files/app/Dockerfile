# This Dockerfile builds a Java web application using Maven and deploys it to a Tomcat server.
# It first clones the project from GitHub, checks out the 'containers' branch, and builds the project using Maven.
# The resulting WAR file is then copied to the Tomcat webapps directory, replacing the default ROOT application.
# The container listens on port 8080 and runs the Tomcat server when started. 

# Étape de build
FROM maven:3.9.9-eclipse-temurin-21-jammy AS build_image
RUN git clone https://github.com/hkhcoder/vprofile-project.git 
RUN cd vprofile-project && git checkout docker && mvn install

# Étape finale
FROM tomcat:10-jdk21
LABEL "Project"="Vprofile"
LABEL "Maintainer"="Jouneid"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=build_image vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
CMD ["catalina.sh", "run"]

      

