# NoteBooksExamples
<img align="center" width="270" height="136" src="http://www.gepacv.org/wp-content/uploads/2017/01/EDEM-Logo--540x272.png">

### Master en Data Analytics para la Empresa

#### Asignatura Fundamentos bases de datos, sql, linux

##### 1.1) Docker
  En la carpeta docker, se encuentra un ejemplo de como crear una imagen de docker, utilizando una fichero Dockerfile.
  
    cd Docker
    
 Creamos el fichero Dockerfile
 
    touch Dockerfile
    
 Editamos el contenido de fichero Dockerfile
    
    vi Dockerfile
    
 Creamos una imagen de Docker partiendo de otra imagen.
 
    FROM ubuntu:16.04

    RUN apt-get update && apt-get install -y nginx && apt-get clean && rm -rf /var/lib/apt/lists/*

    EXPOSE 80

    COPY index.html /var/www/html/

    CMD ["nginx", "-g", "daemon off;"]
    
 Guardamos el fichero Dockerfile y compilamos la imagen 
 
    docker build -t first_edem_img .
    
 Corremos la imagen 
 
    docker run -itd --name cont_first_img_edem -p 8080:80 first_edem_img
    
 Comprobramos si la imagen que hemos creado está funcionando correctamente.
 
    docker ps -a
    
##### 1.2) Notebook

 Las carpetas "Ejemplo_utmb" y "IngestaDedatos" contienen dos ejemplos de notebook, donde ingesta de datos para ejecutar el siguiente nos posicionamos en la carpeta y ejecutamos. el siguiente comando.
 
    docker run -p 19999:8080  -v $PWD/logs:/zeppelin/logs -v $PWD/data:/zeppelin/data --rm --name zeppelin_single apache/zeppelin:0.8.1

    
    
