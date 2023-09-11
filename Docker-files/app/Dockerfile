FROM openjdk:11 AS BUILD1
RUN apt update && apt install maven -y
RUN git clone https://github.com/daiyanrafi/project.git
RUN cd project && git checkout docker && mvn clean install


FROM tomcat:9-jre11
LABEL "Project"="Docker"
LABEL "Author"="pifflox"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD1 /project/target/*.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]