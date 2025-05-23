
# TAS2 - Contenedores servidor web 
## 1. Titulo
Despliegue y Personalizacion de Servidores Web con Nginx en Contenedores Docker
## 2. Tiempo de duración
El tiempo fue de 120 minutos. 
## 3. Fundamentos:

## Contenedor Docker 

Un contenedor de Docker es un entorno de ejecución que tiene todos los componentes necesarios (como el código, las dependencias y las bibliotecas) para ejecutar el código de la aplicación sin utilizar las dependencias de la máquina host. Este tiempo de ejecución del contenedor se ejecuta en el motor de un servidor, una máquina o una instancia en la nube. El motor ejecuta varios contenedores en función de los recursos subyacentes disponibles(Imagen de Docker y Contenedor: Diferencia Entre Tecnologías de Implementación de Aplicaciones - AWS, n.d.). 


- Estándar: Docker creó el estándar de la industria para contenedores, para que pudieran ser portátiles en cualquier lugar
- Ligero: los contenedores comparten el núcleo del sistema operativo de la máquina y, por lo tanto, no requieren un sistema operativo por aplicación, lo que impulsa una mayor eficiencia del servidor y reduce los costos de servidor y licencias.
- Seguro: las aplicaciones son más seguras en contenedores y Docker proporciona las capacidades de aislamiento predeterminadas más sólidas de la industria.

<img src="./docker-img/contenedor.png" alt="drawing0" width="500"/>

## Imagen Docker 

Una imagen de Docker, o una imagen de contenedor, es un archivo ejecutable e independiente que se utiliza para crear un contenedor. Esta imagen de contenedor contiene las bibliotecas, las dependencias y los archivos que el contenedor necesita para ejecutarse. Una imagen de Docker se puede compartir y transportar; por lo tanto, se puede implementar la misma imagen en varias ubicaciones a la vez, como un archivo binario de software.Puede almacenar imágenes en registros para realizar un seguimiento de arquitecturas de software complejas, proyectos, segmentos de negocio y accesos a grupos de usuarios. Por ejemplo, el registro público Docker Hub contiene imágenes como sistemas operativos, marcos de lenguajes de programación, bases de datos y editores de código(Imagen de Docker y Contenedor: Diferencia Entre Tecnologías de Implementación de Aplicaciones - AWS, n.d.). 


<img src="./docker-img/imagen.png" alt="drawing0" width="500"/>

## 4. Conocimientos previos.
   
Para realizar esta practica el estudiante necesita tener claro los siguientes temas:
- Comandos básicos de Docker.
- Edicion de archivos HTML con nano o vi.
- Conocimientos sobre servidores web y puertos.

## 5. Objetivos a alcanzar

- Desplegar dos servidores Nginx en contenedores distintos con Docker.
- Editar y personalizar el contenido HTML por cada contenedor.
- Comprender cómo se gestionan archivos dentro de contenedores Docker.
- Verificar visualmente el contenido de cada servidor desde el navegador.
  
## 6. Equipo necesario:
  
- Computador.
- Docker funcionando.
- Editor de texto como nano o vi.
- Navegador web.

## 7. Material de apoyo.
   
- Documentación de Docker
- Guía de asignatura.
- Cheat Sheet de comandos Docker. 
- Videos tutoriales de Docker.
## 8. Procedimiento

### Pasos 

**Crear una estructura de carpetas:**

1. Crea el primer contenedor Nginx llamado nginx1 exponiendo el puerto 8089: docker run -d --name nginx1 -p 8089:80 nginx.

Figura 8-1 Creación de contenedor nginx1.


<img src="./docker-img/1.PNG" alt="drawing0" width="500"/>


2. Copia el archivo index.html desde el contenedor nginx1 al sistema anfitrión: docker cp nginx1:/usr/share/nginx/html/index.html ./index1.html.

Figura 8-2 Copia del archivo index.html.


<img src="./docker-img/3.PNG" alt="drawing0" width="500"/>

3. Edita el archivo index1.html con un editor como nano o vi, incluyendo información del instituto.

Figura 8-3 Edicion del archivo con informacion del instituto.


<img src="./docker-img/instituto.PNG" alt="drawing0" width="500"/>


4. Copia el archivo editado nuevamente al contenedor nginx1: docker cp index1.html nginx1:/usr/share/nginx/html/index.html.

Figura 8-4 Copia del archivo editado al contenedor. 


<img src="./docker-img/4.PNG" alt="drawing0" width="500"/>

5. Crea el segundo contenedor Nginx llamado nginx2 exponiendo el puerto 8090: docker run -d --name nginx2 -p 8090:80 nginx.

Figura 8-5 Creacion del segundo contenedor nginx2.


<img src="./docker-img/p1.PNG" alt="drawing0" width="500"/>

6. Copia el archivo index.html desde el contenedor nginx2 al sistema anfitrión: docker cp nginx2:/usr/share/nginx/html/index.html ./index2.html.

Figura 8-6 Copia del segundo archivo index.


<img src="./docker-img/p2.PNG" alt="drawing0" width="500"/>

7. Edita el archivo index1.html con un editor como nano o vi, incluyendo información del instituto.

Figura 8-7 Edicion del archivo con informacion del estudiante.


<img src="./docker-img/personal.PNG" alt="drawing0" width="500"/>

8. Copia el archivo editado nuevamente al contenedor nginx1: docker cp index1.html nginx1:/usr/share/nginx/html/index.html.

Figura 8-8 Copia del segundo archivo editado al contenedor.


<img src="./docker-img/p3.PNG" alt="drawing0" width="500"/>


## 9. Resultados esperados:
    
Al finalizar la práctica, se logró cumplir exitosamente cada uno de los objetivos planteados en el procedimiento. En primer lugar, se realizó el despliegue correcto de los contenedores Docker ejecutando el servidor web Nginx, utilizando la imagen oficial disponible en Docker Hub. Cada contenedor fue vinculado a un puerto diferente (8089 y 8090), permitiendo el acceso independiente desde el navegador.

Cada servidor web mostró una página HTML distinta, cumpliendo con la guía. El primer contenedor desplegó una página con información institucional, mientras que el segundo mostró una página personalizada con datos del estudiante. Para lograr esto, se utilizaron comandos como docker ``cp`` para transferir los archivos HTML al interior de los contenedores.

Durante el proceso se emplearon de manera adecuada los comandos ``docker run``, ``docker cp``, ``docker stop``, ``docker start``. Además, se aplicó correctamente el mapeo de puertos con la opción ``-p``, y se trabajó en modo desatendido con ``-d`` para mantener los servicios corriendo en segundo plano.

Todo el desarrollo de la práctica fue documentado con capturas de pantalla que evidencian el funcionamiento de los servidores web, el uso correcto de los comandos Docker y la visualización del contenido personalizado desde el navegador. Esto demuestra una comprensión sólida de los conceptos de virtualización, contenedores y servicios web, alcanzando satisfactoriamente los objetivos de aprendizaje propuestos.

<img src="./docker-img/alex.PNG" alt="drawing0" width="500"/>

<img src="./docker-img/inst.PNG" alt="drawing0" width="500"/>


## 10. Bibliografía
    
- Imagen de Docker y contenedor: diferencia entre tecnologías de implementación de aplicaciones - AWS. (n.d.). Retrieved April 10, 2025, from https://aws.amazon.com/es/compare/the-difference-between-docker-images-and-containers/
- ¿Qué es un contenedor? | Docker. (n.d.). Retrieved April 10, 2025, from https://www.docker.com/resources/what-container/

