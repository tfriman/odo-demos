# mongodb-quickstart project

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .


## Generation
mvn io.quarkus:quarkus-maven-plugin:1.9.0.Final:create \
	-DprojectGroupId=org.acme \
	-DprojectArtifactId=mongodb-quickstart \
	-DclassName="org.acme.mongodb.FruitResource" \
	-Dpath="/fruits" \
	-Dextensions="resteasy-jsonb,mongodb-client,resteasy-mutiny,context-propagation"

docker run -ti --rm -p 27017:27017 mongo:4.0


## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```
./mvnw quarkus:dev
```

## Packaging and running the application

The application can be packaged using `./mvnw package`.
It produces the `mongodb-quickstart-1.0-SNAPSHOT-runner.jar` file in the `/target` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/lib` directory.

The application is now runnable using `java -jar target/mongodb-quickstart-1.0-SNAPSHOT-runner.jar`.

## Creating a native executable

You can create a native executable using: `./mvnw package -Pnative`.

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: `./mvnw package -Pnative -Dquarkus.native.container-build=true`.

You can then execute your native executable with: `./target/mongodb-quickstart-1.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/building-native-image.
