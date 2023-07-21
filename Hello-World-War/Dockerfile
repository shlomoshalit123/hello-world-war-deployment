FROM maven as build 
WORKDIR /app
COPY ..\..\app .
RUN hostname
RUN pwd
RUN ls -R
RUN mvn clean package


FROM tomcat:9.0 
COPY --from=build /app/target/*.war /usr/local/tomcat/webapps/
ENTRYPOINT ["catalina.sh", "run"]

