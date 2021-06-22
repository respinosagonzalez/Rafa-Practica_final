# Rafa-Practica_final
Pregunta 1 - Git y Vscode
Crearemos un proyecto en github (en nuestra parte personal) denominado "<nombre_personal>-Practica_final"

Ejemplo: fernando-Practica_final

En el README copiaremos todas las preguntas de la Practica

Clonaremos el repositorio en nuestros equipos

Abriremos el repositorio con la herramienta Vscode

Todos los archivos y directorio de las siguientes practicas se han de crear en este repo

Pregunta 2 - Instalacion y Configuracion Ansible
Instalamos ansible en el nodo personal

Comprobaremos la version de ansible y la version de python que usara

Crearemos un archivo ansible.cfg con las siguientes caractiristicas

- ruta de inventario --> <Proyecto_github>
- ruta de los roles --> <Proyecto_github>/roles
- usuario remoto --> root
- Compruebe la key del host en --> falso
- Elevarse los privilegios en --> yes
- Elevarse los privilegios con el usuario --> root
- Metodo de elevacion --> sudo
- Pregunte por la password de root --> yes
Crearemos un inventario con los siguetes datos:

- Grupos_hijos: dev, test, proxy, prod
- Grupo_padre: webservers
- Dentro de cada grupo hijo, daremos de alta nuestro nodo personal
Pregunta 3 - Comandos Ad-hoc
Crearemos un archivo denominado install_repo.sh

Dentro del archivo anterior, declararemos un comando ad-hoc para crear un repositorio con las sigueintes caracteristicas:

- Nombre repo --> EPEL-8
- baseurl --> https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rmp
- gpgcheck --> no
- Estara deshabilitado
Pregunta 4 - Condicionales
Crearemos un playbook denominado "instalacion_paqueteria.yml"

Con un solo Play, debemos de hacer las siguientes tareas:

- Actualizaremos todos los paquetes de los nodos del grupo de prod
- Instalaremos la siguiente paqueteria en los nodos del grupo de test
- Instalaremos las herramientas de desarrollo "Developments Tools" en los nodos del grupo dev
Pregunta 5 - Facts
Crearemos el archivo denominado "extraccion_datos.yml"

Insertaremo en el archivo anterior el codigo necesario para implementar los siguientes requisitos en los nodos de prod:

- Se creara un archivo /tmp/extraccion_datos.txt
- El archivo anterio, contendra los siguientes datos del nodo:
	- Nombre_host = <Nombre_asignado_al_nodo>
	- Memoria = <Memoria_total_mb>
	- Espacio disco sda = <Espacio_del_disco_sda>
Pregunta 6 - Roles
Crearemos el role ejemplo-apache en la ruta /root/<Proyecto_github>/roles

El role debe implementar las siguientes funciones:

- Instalacion de apache (httpd)
- Arrancar y habilitar en el arranque el servicio de firewalld
- Permisos en el firewalld para el servicio httpd
- Creacion de un archivo index.html en la ruta /var/www/html/ con el siguiente contenido:
	- FQDN del nodo y la IP del nodo
- Reiniciaremos el servicio httpd cada vez que el fichero anterior se actualice
Crearemos un playbook denominado "ejecucion_role.yml" donde ejecutaremos el role anterior en los servidores de prod

Pregunta 7 - Vault
Crearemos un archivo de variable denominado "password.yml" en el directorio /vars

Dentro contendra las siguientes variable:

- contraseña01: redhat1234
- contraseña02: anubis3434
Cifraremos el fichero anterior y que genere una salida en el fichero password.txt - Le pondremos la contraseña --> Temporal01!

Cambiaremos la contraseña del fichero por --> Temporal02!

Crearemos un playbook denominado "uso_vault.yml" el cual debe implementar las siguientes funcines en el grupo de dev:

- Crea el usuario pepe con la contrarseña01 cifrada en el archivo de vault anterior
- Crear el usuario juan con la contraseña02 cifrada en el archivo de vault anterior
Pregunta 8 - AWX
Crearemos y configuraremos todos los objetos necesarios en AWX para que poder lanzar los ejercicios anteriores con la herramienta de AWX

Los objetos tienen que estar enlacazos a la Organizacion personal creada en el Laboratorio de la sesion 09

Lanzaremos los playbooks con AWX sobre el servidor de laboratorio.
