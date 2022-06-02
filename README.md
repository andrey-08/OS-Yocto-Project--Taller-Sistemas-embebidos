# OS-Yocto-Project--Taller-Sistemas-embebidos
Se crea un Sistema Operativo de propósito especifico con características mínimas que permitan correr PBRT y sintetizar escenas a través de ray tracing.

# Desarrollo
El proyecto consiste en realizar pruebas con PBRT V3, donde se busca sintetizar diferentes escenas en ciertos ambientes (Windows 10, Ubuntu 22.04 y un OS especifico). Estas escenas son las mismas para cada uno de los ambientes. Ademas las pruebas se realizan en igualdad de condiciones a nivel de hardware (misma computadora).

# Creacion de OS de apicacion especifica
Para la creacion de este sistema operativo se utiliza Yocto Project, el cual nos permite crear OS con diferentes caracteristicas segun lo que se necesite. En este caso se crea un OS que utiliza como base uun kernel basado en linux.
- Para el proceso de creacion se trabaja con el manual que otorga la pagina de PBRT, pero para la creacion especifica:
1) Se realizan ciertos cambios al archivo local.conf para obtner ciertas herramientas necesarias para la ejecucion de PBRT (cmake, gcc, make, c++) 
2) utilizamos el bitbake: bitbake core-image-base  // con core-image-base obtendriamos diferentes aspectos basicos necesarios para nuestra apllicacion (conexion a internet por ejemplo)
3) Para la creacion de la imagen iso se utiliza el comando "wic create mkhybridiso -e core-image-base". Igualmente se necesitan realizar ciertos cambios al archivo local.conf.

Lo mencionado anteriormente es un resumen de los pasos mas importantes, para mayor entendimiento consultar a los manuales de PBRT.
