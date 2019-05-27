#ベースはJDK8イメージ
FROM openjdk:8-jdk-alpine

#アプリをjava-app.jarとしてデプロイ
COPY ./sample-es-0.0.1-SNAPSHOT.jar java-app.jar

#アプリ実行
CMD ["java","-jar","/java-app.jar"]

