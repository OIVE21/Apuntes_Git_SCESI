 #Mi trabajo Individual 
Estudiante Oscar Ignacio Velasco Encinas

# Clase 1

###¿Qué es GIT?

GIT es un VCS (Sistema de control de Versiones)

###¿Cómo instalar GIT?
En mi caso, como mi sistema operativo es Windows, busqué en mi navegador git Download, descargué el paquete y lo ejecuté. La mayoria era next, next; pero había que cambiar a Override Main en algún punto

###¿Cómo nació GIT?
Linus Torvalds, el creador de Linux, mientras trabajaba en su proyecto y su comunidad le aportaba, le resultó tedioso y poco práctico. Entonces maneja BitKeeper (otro sistema de control de versiones), con el cual tuvieron problas
entonces, Linus decide crear su propio Sistema de Control de Versiones basado en su ideología de Open Source y desarrolla GIT..

# Clase 2
##States y Commits 
###Estados 
Existen tres: -Directorio de Trabajo (Modificado), Carpeta Local -> Git todavia no tiene asegurado los cambios que haces, Creo, modifico y elimino
- Stage Area (Preparado), Área de espera -> Le dices a git lo que quieres guardar. Preparo los cambios 
- Repositorio Local (Confirmado), El historial -> Los cambios tinen un ID. Grabo los cambios en el repositorio.
##Directorio de Trabajo 
2 tipos de archivos: 
Untracked -> Sin seguimiento, Modified-> Ya se tiene una versión previa 
----
git restore <archivo> Para que el archivo vuelva a su estado original
----
##Stage area 
git add <archivo> Para agregar el archivo
git add . Para agregar todos los archivos observados por git
git restore --staged <archivo> Para sacar un archivo del stage area para volver al estado anterior

##Repositorio Local 
Queremos que el repositorio cree el punto de guardado, los cambios pasan a ser parte del historial
git commit -m "mensaje" -> Para registrar el commit
git reset --soft HEAD-1 -> Para deshacer el último commit

##Buenas Prácticas
Hacer un commit cuando haz modificado algo (aunque pequeño) significativo. commits atómicos en inglés
Buenos commits -> Usar verbos imperativos (Add, change, Fix, remove); no usar puntos suspensivos o simples; Máximo 50 caracteres; usar prefijos 
Lista de prefijos -> feat, fix, perf, build, ci, docs, refactor, style, test
Estructura de los commits -> prefijo (Titulo del commit) luego el cuerpo que lo describe
Es fundamental hacer buenos commits para que al momento de compartir nuestro trabajo, nos entiendan al momento de presentar y trabajar en equipo 

# Clase 3 
###Introducción a GitHub
Hablemos de GitHub, pues es una plataforma en la nube con el ícono de un gato con fondo negro. También es una red social. Sus funciones son principalmente alojar, gestionar y colaborar
en proyectos utilazando git. 
###Git vs GitHub
Git -> Sistema de control integrado 
GitHub -> Servidor que almacena los guardados que genera Git, entonces usa Git pero no es Git. 
###SSH
En SSH configuramos en nuestra pc, para comunicarnos con github, debemos de usar una key para que GitHub no moleste pidiendo la autentificación una y otra vez.
###HTTPS
Cuando usemos o clonemos algún repositorio, HHTTPS nos pide la autentificación siempre que lo intentemos, además que nos pide un token. 
##Crear Repositorios en GitHub
1.- Ir al apartado de repositorios de la cuenta y poner New.
2.- Ponerle nombre al nuevo repositorio, la descripción es opcional 
3.- Click en Create Repository 
##Conectar Repositorio de Git con uno de GitHub 
Comando --> git remote add origin git@github.com: TuUser/TuRepo.git
git branch -M main 
git push -u origin main 
##Clonar Repositorio de Git
Comando-->  git clone "git@github.com: TuUser/TuRepo.git"
Para ver a que repositorio remoto está conectado--> git remote -v
##Comandos para los cambios 
###Subir cambios 
git push origin <rama>
Donde "git push" empuja los commits y "origin" es el servidor al que lo apodamos así, rama es la del código
###Bajar cambios
git pull origin <rama>
Donde "git pull" trae los commits, "origin" es el servidor al que lo apodamos así y "rama" es la del código

