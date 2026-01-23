# Imagen base
FROM ubuntu:22.04

# Instalar JDK por defecto y wget
RUN apt-get update && apt-get install -y \
    default-jdk \
    wget \
 && rm -rf /var/lib/apt/lists/*

# Descargar e instalar Tomcat 9 en /opt/tomcat
RUN wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.115/bin/apache-tomcat-9.0.115.tar.gz \
    && tar -xzf apache-tomcat-9.0.115.tar.gz \
    && rm apache-tomcat-9.0.115.tar.gz \
    && mv apache-tomcat-9.0.115 /opt/tomcat

# Crear carpeta de certificados
RUN mkdir -p /opt/tomcat/certificates

# Variable de entorno (opcional pero habitual)
ENV CATALINA_HOME=/opt/tomcat

# Arrancar Tomcat al iniciar el contenedor
CMD ["/opt/tomcat/bin/catalina.sh", "run"]
