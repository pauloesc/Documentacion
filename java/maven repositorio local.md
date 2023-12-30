Crear en la carpeta (root) del proyecto maven, una carpeta llamada local-maven-repo

Agregamos lo siguiente al pom.xml:

```
<repositories>
    <repository>
        <id>local-maven-repo</id>
        <url>${project.basedir}/local-maven-repo</url>
    </repository>
</repositories>
```

para cada jar externo que queramos instalar hacemos lo siguiente

IMPORTANTE: BORRAR LOS [].

mvn deploy:deploy-file -DgroupId=[GROUP] -DartifactId=[ARTIFACT] -Dversion=[VERS] -Durl=file:./local-maven-repo/ -DrepositoryId=local-maven-repo -DupdateReleaseInfo=true -Dfile=[FILE_PATH]

En el pom ponemos:

```
<dependency>
    <groupId>GROUP</groupId>
    <artifactId>ARTIFACT</artifactId>
    <version>VERSION</version>
</dependency>
```
