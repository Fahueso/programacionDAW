# Parte 1 Configuración inicial

Abrimos una consola y ejecutamos los siguientes comandos para inicializar el sistema de git. Básicamente estamos estableciendo el usuario que firma los commits.

Si hacemos estos comandos en nuestro home nos valdrá para todas las subcarpetas que vayamos generando.

![](assets/image.png)  

# Generación de token en Github

Nos desplazamos a la siguiente URL
[Personal Access Tokens (Classic)](https://github.com/settings/tokens)

![](assets/image-1.png)  

Generamos un token nuevo de tipo clásico

![](assets/image-2.png)  

En la captura se especifica una duración del token de un mes, es posible establecer una duración superior. Procedemos a genera el token.

![](assets/image-3.png)  

Copiamos el contenido del token y no lo compartimos con nadie. Nos vamos a configurar este token en IntelliJ. Cuando se nos caduque el token, pasados los 30 días podremos repetir este proceso.

Accedemos a las Settings de IntelliJ

![](assets/image-4.png)  

![](assets/image-6.png)  

Introducimos el token, y debe registrar nuestra propia cuenta de github:

![](assets/image-7.png)  

Buscamos la opción de compartir el proyecto en GitHub (el menú puede variar en función de la versión de IntelliJ)

![](assets/image-8.png)  

Ponemos nombre al repositorio remoto:

![](assets/image-9.png)  

Añadimos todos los ficheros y escribimos el mensaje correspondiente:

![](assets/image-10.png)  

Podemos comprobar en el navegador el repositorio desde la web de github o pulsando el enlace:

![](assets/image-11.png)  

![](assets/image-12.png)  

# Parte 2: Adicción de cambios

Los ficheros que vaya modificando aparecerán marcados:

![](assets/image-13.png)  

Buscamos el botón de commit y marcamos los archivos nuevos que queramos guardar en la nube:

![](assets/image-14.png)  

y pulsamos la opción Commit and Push e si tenemos algún mensaje de alerta (se produce porque hay warnings en el código expuesto), podemos hacer el commit o revisar el código.

![](assets/image-15.png)  

Por último, una vez que el commit se ha realizado nos pedirá hacer el push:

![](assets/image-16.png)  

![](assets/image-17.png)  

En función de la versión de IntelliJ y del idioma podemos encontrarnos esta otra forma:

![](assets/image-24.png)  

Aqui buscaremos la opción  de Hacer commit e insertar.

# Parte 3: Poner mi repositorio en otro IntelliJ

En primer lugar nos aseguramos que nuestra cuenta está registrada en ese IntelliJ, en caso contrario tendremos que darlo de alta mediante un token (puede ser el mismo si lo hemos conservado)

En github tomamos la url:

![](assets/image-18.png)  

En la pantalla inicial de IntelliJ, usando Clone Repository:

![](assets/image-19.png)  

O bien desde el menú:

![](assets/image-20.png)  

Copiamos la URL:

![](assets/image-21.png)  

![](assets/image-22.png)  

Si el repositorio es nuestro, podemos buscarlo alternativamente en este otro apartado:

![](assets/image-23.png)  
