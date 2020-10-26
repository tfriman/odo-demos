# mongodb-quickstart project

Demo project for ODO. Quarkus REST API with MongoDB backend.

## Project generation

```shell script
mvn io.quarkus:quarkus-maven-plugin:1.9.0.Final:create \
	-DprojectGroupId=org.acme \
	-DprojectArtifactId=mongodb-quickstart \
	-DclassName="org.acme.mongodb.FruitResource" \
	-Dpath="/fruits" \
	-Dextensions="resteasy-jsonb,mongodb-client,resteasy-mutiny,context-propagation"
```

## Running locally

```shell script
mvn compile quarkus:dev

docker run -ti --rm -p 27017:27017 mongo:4.0
```

## odo

```shell script
odo project create odo-test-project
odo catalog list components
odo create java-quarkus quark-mongo --now
git add devfile.yaml
oc describe pods quark-mongo-6dcc4c5776-9d896
oc logs -f quark-mongo-6dcc4c5776-9d896 -c mongodb
oc get pods
oc describe pods quark-mongo-8477ff7ddc-8d4hk
odo url create --now
odo log -f

```

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```
mvn quarkus:dev
```

## Packaging and running the application

The application can be packaged using `mvn package`.
It produces the `mongodb-quickstart-1.0-SNAPSHOT-runner.jar` file in the `/target` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/lib` directory.

The application is now runnable using `java -jar target/mongodb-quickstart-1.0-SNAPSHOT-runner.jar`.

## Creating a native executable

You can create a native executable using: `mvn package -Pnative`.

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: `mvn package -Pnative -Dquarkus.native.container-build=true`.

You can then execute your native executable with: `./target/mongodb-quickstart-1.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/building-native-image.
