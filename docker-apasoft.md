## Comandos
*video 31

docker ps --help => muestra infomacion de ps en este caso

docker ps => muestra los contenedores encendidos

docker ps -a => muestra todos los contenedores

docker run hello-world => crea un contenedor apartir de una imagen local, si no existe descarga la imagen y crea su contenedor

docker images => muestra las imagenes

* no todo lo que esta en docker hub es gratuito, algunas tienes licencias 

*video 34

docker pull ubuntu => descarga la ultima versin de la imagen indicada
 
importante: al ejecutar docker run crea un nuevo contenedor de la imagen

*video 40
docker start container-name => inicia el contenedor indicado
docker start -i container-name => inicia en modo interactivo el contenedor indicado
docker stop container-anem => detiene el contenedor indicado

*video 42
docker run -d nginx => crea el contenedor en modo background, si el contenedor puede trabajar de esta forma
*dos formas de trabajar con contenedores en modo interactivo y en modo background
