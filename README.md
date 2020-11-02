# ODO examples and demos

## Customized registry

Registry has an xxample devfile containing MongoDB, base copied from [https://github.com/odo-devfiles/registry](https://github.com/odo-devfiles/registry). See [https://odo.dev/docs/secure-registry/](https://odo.dev/docs/secure-registry/) for info how to access secured git repo.

### Adding new registry to odo

#### Using github and main branch:

```shell script
odo registry add tfriman-registry "https://github.com/tfriman/odo-demos/tree/main"
```

#### Using bitbucket

Find out the raw path

```shell script
odo registry update tfriman-bitbucket-registry https://bitbucket.org/tfriman/odo-devfile-registry/raw/4c04539cfa4700915d446a89474f7edbda14feff
```

#### Smoke check after addition

Check you can access your new registry

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
