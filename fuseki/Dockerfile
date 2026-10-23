FROM eclipse-temurin:21-jre

WORKDIR /fuseki

# Apache Jena Fuseki 6.2.0, published by Apache on Maven Central.
ADD --chmod=0444 --checksum=sha256:2c92c598e65ab69d99820052e05f4277ed1d77980a8845f87545ad35b71a76ee \
    https://repo.maven.apache.org/maven2/org/apache/jena/jena-fuseki-server/6.2.0/jena-fuseki-server-6.2.0.jar \
    /fuseki/fuseki-server.jar

USER 10001:10001
EXPOSE 3030

ENTRYPOINT ["java", "-Xms128m", "-Xmx512m", "-cp", "/fuseki/fuseki-server.jar", "org.apache.jena.fuseki.main.cmds.FusekiMainCmd"]
CMD ["--config=/fuseki/config.ttl"]
