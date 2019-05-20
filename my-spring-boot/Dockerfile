#ベースはJDK8イメージ
FROM openjdk:8-jdk-alpine

#アプリをapp.jarとしてデプロイ
COPY ./sample-es-0.0.1-SNAPSHOT.jar app.jar

#アプリ実行
CMD ["java","-jar","/app.jar"]

