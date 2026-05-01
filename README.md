 #Mi trabajo Individual 
Estudiante Oscar Ignacio Velasco Encinas

# Clase 1

### ¿Qué es GIT?

GIT es un VCS (Sistema de control de Versiones)

### ¿Cómo instalar GIT?
En mi caso, como mi sistema operativo es Windows, busqué en mi navegador git Download, descargué el paquete y lo ejecuté. La mayoria era next, next; pero había que cambiar a Override Main en algún punto

### ¿Cómo nació GIT?
Linus Torvalds, el creador de Linux, mientras trabajaba en su proyecto y su comunidad le aportaba, le resultó tedioso y poco práctico. Entonces maneja BitKeeper (otro sistema de control de versiones), con el cual tuvieron problas
entonces, Linus decide crear su propio Sistema de Control de Versiones basado en su ideología de Open Source y desarrolla GIT..

# Clase 2
## States y Commits 
### Estados 
Existen tres: -Directorio de Trabajo (Modificado), Carpeta Local -> Git todavia no tiene asegurado los cambios que haces, Creo, modifico y elimino
- Stage Area (Preparado), Área de espera -> Le dices a git lo que quieres guardar. Preparo los cambios 
- Repositorio Local (Confirmado), El historial -> Los cambios tinen un ID. Grabo los cambios en el repositorio.
## Directorio de Trabajo 
2 tipos de archivos: 
Untracked -> Sin seguimiento, Modified-> Ya se tiene una versión previa 
----
git restore <archivo> Para que el archivo vuelva a su estado original
----
## Stage area 
git add <archivo> Para agregar el archivo
git add . Para agregar todos los archivos observados por git
git restore --staged <archivo> Para sacar un archivo del stage area para volver al estado anterior

## Repositorio Local 
Queremos que el repositorio cree el punto de guardado, los cambios pasan a ser parte del historial
git commit -m "mensaje" -> Para registrar el commit
git reset --soft HEAD-1 -> Para deshacer el último commit

## Buenas Prácticas
Hacer un commit cuando haz modificado algo (aunque pequeño) significativo. commits atómicos en inglés
Buenos commits -> Usar verbos imperativos (Add, change, Fix, remove); no usar puntos suspensivos o simples; Máximo 50 caracteres; usar prefijos 
Lista de prefijos -> feat, fix, perf, build, ci, docs, refactor, style, test
Estructura de los commits -> prefijo (Titulo del commit) luego el cuerpo que lo describe
Es fundamental hacer buenos commits para que al momento de compartir nuestro trabajo, nos entiendan al momento de presentar y trabajar en equipo 

# Clase 3 
### Introducción a GitHub
Hablemos de GitHub, pues es una plataforma en la nube con el ícono de un gato con fondo negro. También es una red social. Sus funciones son principalmente alojar, gestionar y colaborar
en proyectos utilazando git. 
### Git vs GitHub
Git -> Sistema de control integrado 
GitHub -> Servidor que almacena los guardados que genera Git, entonces usa Git pero no es Git. 
### SSH
En SSH configuramos en nuestra pc, para comunicarnos con github, debemos de usar una key para que GitHub no moleste pidiendo la autentificación una y otra vez.
### HTTPS
Cuando usemos o clonemos algún repositorio, HHTTPS nos pide la autentificación siempre que lo intentemos, además que nos pide un token. 
## Crear Repositorios en GitHub
1.- Ir al apartado de repositorios de la cuenta y poner New.
2.- Ponerle nombre al nuevo repositorio, la descripción es opcional 
3.- Click en Create Repository 
## Conectar Repositorio de Git con uno de GitHub 
Comando --> git remote add origin git@github.com: TuUser/TuRepo.git
git branch -M main 
git push -u origin main 
## Clonar Repositorio de Git
Comando-->  git clone "git@github.com: TuUser/TuRepo.git"
Para ver a que repositorio remoto está conectado--> git remote -v
## Comandos para los cambios 
### Subir cambios 
git push origin <rama>
Donde "git push" empuja los commits y "origin" es el servidor al que lo apodamos así, rama es la del código
### Bajar cambios
git pull origin <rama>
Donde "git pull" trae los commits, "origin" es el servidor al que lo apodamos así y "rama" es la del código

# Clase 4 
## GIT REMOTE 
Se trata de un comando de Git que facilita gestionar las conexiones con los repositorios remotos. 
Nos sirve bastante porque le dice a Git Local donde enviar o traer información.
### Comandos Utiles de Git Remote 
git remote -v --> Ver las URLs de donde está el repositorio 
git remote add <apodo> "ur" --> Vinculación de nuestro repositorio local con uno de la nube
git remote set-url <apodo> "url" --> Cambia la url de nuestro repositorio 
## Múltiples SSH
En el caso de que tengamos más de una cuenta o queramos tener otras cuentas de GitHub debemos tener más de una llave SSH por buena práctica.
Cada cuenta necesita su tunel para que estos no choquen
### Configurar SSH
1.- Generamos el sshkey con otro nombre
2.- Creamos un archivo config para no chocar las Keys
3.- Verificación con el comando "ssh -T git @github-miname"
## Configuraciones Locales 
Estas se imponen a las globales, mientras que las globales solo funcionan para el repositorio en el que se aplican.
Tip: Reemplazar las flag --global 
Tip 2: Hacer Git Clone con el Host Correcto
## Git Checkout
Desplaza el HEAD hacia un punto específico de una rama distinta
Este comando es bien útil porque inspecciona, restaura, experimenta y cambia
## Detached HEAD
Eres un espectador en el pasado, es decir puedes ver todo y escribir notas pero no tienes ramas. Asimismo, si te vas al presente sin encarna en una rama, tus cambios se pierden
## Ir y volver de un Commit
atrás --> git checkout <hash antiguo>
ir al último hash --> git checkout <rama>
Tus commits desaparecen a menos que hagas lo siguiente: 
git ckeckout <hash del commit creado>
git checkout -b rama_nueva
## Tips para buenas prácticas del Checkout
1.- No trabajar mucho timepo en Detached HEAD --> En vez de dos lineas, crear directamente una rama
2.- Limpiar directorio de Trabajo --> Antes de ir al pasado, hay que hacer un commit del presente. Caso contrario, git no nos dejará viajar al pasado 
3.- Usarlo para aprender --> Es la mejor forma de entender cómo se crearon los commits de proeyctos grandes.

# Clase 5 
## Ramas 
Definición: Las ramas son simplemente una herramienta que nos permite gestionar mejor el código. Una bifurcación entre el camino original y un camino de la evolución del código
Comandos: 
- git branch --> Nos permite tener control de las ramas. Hace un listado y muestra el posicionamiento del HEAD
- git branch <Rama> --> Crea una rama a partir de la que ya estamos posicionados
- git branch -D <Rama> --> Elimina la Rama
### Git Checkout - Aplicación a ramas
- git checkout <rama> --> Cambiar de ramas (no debe haber nada en modified, untracked, staged)
- git checkout -b <rama> --> Crea la rama y te dirige a ella 
### Git Checkout vs Git Switch 
Git Switch es un comando más nuevo y actualizado, sirve para separar la navegación de ramas del resto de funciones 
Por otro lado, Git Checkout se usa para más elementos: Ramas, Archivos, commits, etc
## GitFlow Básico 
- Flujo de Trabajo --> En inglés Workflow, son normas que nos permiten trabajar de manera ordenada con las ramas, versiones.
### Cómo funciona
- Rama main --> Rama que tenemos por defecto al crear un repositorio, contiene el código que se encuentra en producción
- Rama develop --> Rama de producción, contiene las características que se están probando pero no fueron validadas, sin embargo serán lanzadas pronto.
- Ramas de apoyo --> Tal como se muestra en su nombre, nos permiten escribir código. Ejemplos, Feature, release y hotfix.
## Ramas de apoyo 
### Feature
Ramas creadas a partir de develop. Cuando se finalizan, se fusionan de nuevo con develop y eliminadas.
### Release
Son ramas que se usan normalmente cuando preparas el lanzamiento de una nueva versión de tu producto. Se crean en develop y se fusionan ahí o en main.
### Hotfix 
Ramas que funcionan como áreas de mantenimiento. Se usan para trabajar en parches, corregir bugs, etc. Se crean en main y se fusionan con main o develop.

# Clase 6

## Git merge 
Merge en su traducción al inglés, significa fusion y permite fucionar ramas empezando a escribir sin afectar la rama principal
git checkout develop --> se dirige a la rama develop
## Git fech 
Este comando mira las ramas de develop y todas las rams que tienen cambios.
## Git pull origin develop
Trae todas las rams de develop a el repo local
### Algunos comandos
- git swich --> te mueves a la rama y luego la traes
- git fech --> para checkear si subieron cambios)
- git push origin develop --> subir cambios
- git pull origin develop --> traer todos los cambios para mi)
- git checkout -b feature/name (ejemplo: feature/'update readme') --> Las ramas se crean en feature

# Clase 7

## Pull Request
Básicamente es una manera de trabajar que crea un request en el grupo de repositorio para ir viendo a que se le quiere hacer mergear

## Creación de Pull Request 
Primero que nada se debe hacer previamente el comando -- git push origin rama -- 
El proceso implica crear una rama, realizar cambios, subirla al repositorio y solicitar la revisión para asegurar la calidad antes del merge

## Por qué se usan los Pull Request 
Principalmente para temas de seguridad, no es prudente que cualquiera pueda tocar el repositorio y manipularlo o mergearlo.
Es una forma estratégica para poder trabajar en equipo.

## Cómo proteger el repositorio y limitar la colaboración 
Las estrategias clave incluyen proteger ramas, gestionar permisos de colaboradores y limitar interacciones temporales.
- pull request before merging: Exige que los cambios pasen por una revisión antes de fusionarse.

## Cómo colaboro el proyecto si no soy un colaborador invitado
Si no soy un colaborador invitado en un repositorio de GitHub, aún se puede contribuir utilizando «Fork and Pull Request». 
Este método permite copiar el proyecto, realizar cambios y proponer que sean incluidos en el proyecto original.

