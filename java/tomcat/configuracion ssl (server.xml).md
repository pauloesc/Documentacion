La configuración a continuacion corresponde a un conector SSL en un servidor Apache Tomcat.

```
<Connector SSLEnabled="true"
           acceptCount="100"
           clientAuth="false"
           disableUploadTimeout="true"
           enableLookups="false"
           maxThreads="25"
           port="8443"
           keystoreFile="/Users/.keystore"
           keystorePass="password"
           protocol="org.apache.coyote.http11.Http11NioProtocol"
           scheme="https"
           secure="true"
           sslProtocol="TLS" />
```

A continuación, describiré exhaustivamente cada atributo presente en la configuración:

SSLEnabled="true":
Indica que este conector utilizará SSL (Secure Sockets Layer) para conexiones seguras.

acceptCount="100":
Define el número máximo de solicitudes de conexión que se pueden encolar cuando todos los procesadores están ocupados.

clientAuth="false":
Especifica si se requiere autenticación del cliente. En este caso, se establece en false, lo que significa que no se requiere autenticación del cliente.

disableUploadTimeout="true":
Deshabilita el tiempo de espera para la carga de archivos. Esto puede ser útil para conexiones de carga lenta.

enableLookups="false":
Determina si se deben realizar búsquedas DNS inversas para resolver direcciones IP en nombres de host.

maxThreads="25":
Establece el número máximo de hilos de trabajo que el contenedor Tomcat puede usar para procesar solicitudes.

port="8443":
Especifica el puerto en el que escuchará el conector SSL.

keystoreFile="/Users/.keystore":
Indica la ubicación del archivo de keystore que contiene el certificado SSL. En este caso, el archivo se encuentra en el directorio personal del usuario.

keystorePass="password":
Especifica la contraseña que se utilizará para acceder al keystore. Ten en cuenta que almacenar contraseñas en archivos de configuración puede tener implicaciones de seguridad.

protocol="org.apache.coyote.http11.Http11NioProtocol":
Define el protocolo que se utilizará. En este caso, se utiliza el protocolo NIO (New I/O) implementado por Apache Coyote.

scheme="https":
Indica el esquema de URI que se utilizará para este conector. En este caso, es HTTPS.

secure="true":
Indica si este conector debe usar una conexión segura. En este caso, se establece en true.

sslProtocol="TLS":
Especifica el protocolo SSL/TLS que se utilizará para las conexiones seguras. En este caso, se utiliza TLS.

Para mas info leer en https://tomcat.apache.org/tomcat-9.0-doc/config/http.html

-------------------------------------------------------------------

SSLEnabled="true":

Habilitado (true): El conector está configurado para aceptar conexiones seguras a través de SSL/TLS. Se espera que las solicitudes lleguen a través de HTTPS.
Deshabilitado (false): El conector no manejará conexiones seguras y esperará conexiones no seguras (HTTP). El servidor no aceptará solicitudes HTTPS.

-------------------------------------------------------------------

¿qué se logra al tener scheme="https"?

Indicación en las URLs:
Cuando el esquema se establece en "https", las URLs generadas por el servidor y utilizadas en la configuración de red (como redirecciones y enlaces) incluirán el prefijo "https://". Esto ayuda a los clientes (navegadores, aplicaciones) a entender que la conexión debe realizarse a través del protocolo seguro HTTPS.

Interoperabilidad con Proxies y Cachés:
Muchos proxies y cachés web respetan el esquema de las URLs al realizar decisiones sobre la caché y la seguridad. Al utilizar scheme="https", se comunica a estos componentes intermedios que el recurso está disponible a través de una conexión segura, lo que puede influir en su comportamiento de almacenamiento en caché y enrutamiento.

Compatibilidad con Sitios Web que Requieren HTTPS:
Algunos sitios web y servicios requieren conexiones seguras. Al establecer scheme="https", estás indicando claramente que tu aplicación o servicio está disponible a través de HTTPS, cumpliendo con requisitos de seguridad y compatibilidad.

En resumen, establecer scheme="https" no habilita ni deshabilita la seguridad por sí solo; simplemente indica que el conector está diseñado para manejar conexiones seguras. Es una práctica común en la configuración de servidores web para garantizar que las URLs generadas y las interacciones de red reflejen correctamente la intención de utilizar conexiones seguras a través de HTTPS.

-------------------------------------------------------------------
