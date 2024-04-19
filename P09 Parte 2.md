## Parte 2

Primero instalamos el servicio web en mi VPS, en mi caso usare nginx. Para ello, dentro de mi VPS, ponemos los comandos: “sudo apt update” y “sudo apt install nginx”.

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.008.png)

Crearemos una pagina de prueba dentro de nginx en html para visualizarla en nuestro servidor.

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.009.png)

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.010.png)



Creamos el nombre de dominio mediante la página web “www.duckdns.org”.

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.011.png)

Ahora solo tendremos que indicarlo en digitalocean, donde también añadiremos los dominios hacia donde apuntará la aplicación, www y @.

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.012.png)

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.013.png)

Tras realizar estas configuraciónes, podemos acceder a la pagina del servidor creado con nginx mediante el dns <http://proyecto9bastionado.duckdns.org/>.

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.014.png)

Para configurar HTTPS con un certificado válido, vamos a realizar la siguiente configuración en el servidor:

Primero, ejecutamos este comando para instalar Certbot “sudo snap install --classic certbot”.

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.015.png)

Luego, ejecutamos la siguiente instrucción en la línea de comando para asegurarnos de que el certbot comando se pueda ejecutar, ”sudo ln -s /snap/bin/certbot /usr/bin/certbot”.

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.016.png)



Después, ejecutamos este comando para obtener un certificado y haga que Certbot edite su configuración de nginx automáticamente para entregarlo, activando el acceso HTTPS en un solo paso, “sudo certbot –nginx”.

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.018.png)

A continuación, probamos la renovación automática de sus certificados ejecutando este comando “sudo certbot renew --dry-run”.

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.019.png)

Captura de pantalla certificado.

![](Aspose.Words.01340cf9-db5d-4ef9-9298-1e3d7311ed00.020.png)

