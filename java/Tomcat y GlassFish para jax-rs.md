El término "contenedor servlet de Jersey" se refiere a las clases y componentes de Jersey que se encargan de manejar las solicitudes HTTP y las respuestas dentro de un entorno servlet. En otras palabras, Jersey necesita un contenedor servlet para ejecutar sus aplicaciones web.

Esta dependencia proporciona las clases necesarias para integrar Jersey con un contenedor servlet. Y aquí es donde se requiere una aclaración:

Si estás utilizando un servidor de aplicaciones Java EE completo como GlassFish, este servidor ya incluye su propio contenedor servlet. Por lo tanto, en este caso, Jersey se integraría con el contenedor servlet proporcionado por GlassFish.

Si estás utilizando un servidor de servlet independiente como Tomcat, necesitas una dependencia adicional específica de Jersey para integrar Jersey con el contenedor servlet de Tomcat. La dependencia adicional es:
