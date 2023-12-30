```
<plugin>
<groupId>org.codehaus.mojo</groupId>
<artifactId>jaxws-maven-plugin</artifactId>
<version>2.6</version>
<executions>
<execution>
<goals>
<goal>wsimport</goal>
</goals>
<configuration>
<wsdlUrls>
<wsdlUrl>http://localhost:8080/servidor/img?wsdl</wsdlUrl>
</wsdlUrls>
<packageName>com.example.generated</packageName>
<sourceDestDir>${project.build.directory}/generated-sources/jaxws-wsimport</sourceDestDir>
</configuration>
</execution>
</executions>
<dependencies>
<dependency>
<groupId>com.sun.xml.ws</groupId>
<artifactId>jaxws-tools</artifactId>
<version>2.3.5</version>
</dependency>
</dependencies>
</plugin>
```

Las 2 lineas siguientes generaron lo siguiente directorios y archivos.

+ <packageName>com.example.generated</packageName>
+ <sourceDestDir>${project.build.directory}/generated-sources/jaxws-wsimport</sourceDestDir>

dentro del jar quedo: com/example/generated/{los clases java}

dentro dee la capeta del proyecto quedo (dentro de target): /target/generated-sources/jaxws-wsimport/com/example/generated/{los archivos java}

dentro de src no genero nada

-----------------------------------------------------------------------

Las 2 lineas siguientes generaron lo siguiente directorios y archivos.

+ <packageName>com.example.generated</packageName>
+ <sourceDestDir>src/generated-sources/jaxws-wsimport</sourceDestDir>

dentro del jar quedo: com/example/generated/{los clases java}

dentro dee la capeta del proyecto quedo /src/generated-sources/jaxws-wsimport/com/example/generated/{los clases java}

los archivos generados quedaron con la siguiente linea "package com.example.generated;"
