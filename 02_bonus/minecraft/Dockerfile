FROM java:openjdk-8-jdk

RUN apt-get -y install wget

RUN wget https://hub.spigotmc.org/jenkins/job/BuildTools/lastSuccessfulBuild/artifact/target/BuildTools.jar

RUN java -jar BuildTools.jar
RUN echo "eula=true" >> eula.txt

ENTRYPOINT java -Xms1G -Xmx1G -XX:+UseConcMarkSweepGC -jar spigot-1.13.2.jar

EXPOSE 25565