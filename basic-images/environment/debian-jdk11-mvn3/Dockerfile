FROM samhunt/debian-basic-image:latest

USER root

RUN mkdir -p /usr/local/java && mkdir -p /usr/local/maven 
WORKDIR /usr/local/java/
RUN curl -fsSL -o zulu11.56.19-ca-jdk11.0.15-linux_x64.tar.gz https://cdn.azul.com/zulu/bin/zulu11.56.19-ca-jdk11.0.15-linux_x64.tar.gz && tar -zxvf ./zulu11.56.19-ca-jdk11.0.15-linux_x64.tar.gz
WORKDIR /usr/local/maven
RUN curl -fsSL -o apache-maven-3.8.5-bin.tar.gz https://dlcdn.apache.org/maven/maven-3/3.8.5/binaries/apache-maven-3.8.5-bin.tar.gz && tar -zxvf ./apache-maven-3.8.5-bin.tar.gz && \
sed -i '$aexport JAVA_HOME=/usr/local/java/zulu11.56.19-ca-jdk11.0.15-linux_x64' /etc/profile && \
sed -i '$aexport MAVEN_HOME=/usr/local/maven/apache-maven-3.8.5' /etc/profile && \
sed -i '$aPATH=$PATH:$JAVA_HOME/bin:$MAVEN_HOME/bin' /etc/profile && \
exec bash && source /etc/profile

WORKDIR /root