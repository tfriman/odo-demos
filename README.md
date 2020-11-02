# ODO examples and demos

## Customized registry

Registry has an xxample devfile containing MongoDB, base copied from [https://github.com/odo-devfiles/registry](https://github.com/odo-devfiles/registry). See [https://odo.dev/docs/secure-registry/](https://odo.dev/docs/secure-registry/) for info how to access secured git repo.

### Adding new registry to odo

```shell script
odo registry add tfriman-registry "https://github.com/tfriman/odo-demos"

```

Check you have it:

```shell script
odo catalog list components
```

```
NAME                   DESCRIPTION                                   REGISTRY
java-maven-mongodb     Upstream Maven and OpenJDK 11 and MongoDB     tfriman-registry
java-maven             Upstream Maven and OpenJDK 11                 DefaultDevfileRegistry
```

#### Using your custom devfile from custom registry

```shell script
cd example-quarkus-mongodb-with-devfile
odo create java-maven-mongodb custom-devfile-example --now
```
