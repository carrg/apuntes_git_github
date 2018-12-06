# apuntes_git_github

* Creamos el repo en github
* Clonamos en el directorio
* Inicializar rama - crea ambiente de desarrollo y producción -> Se tiene que instalar el gitflow
	Comando: git flow init
	
	npm run develop config/production_variables.env -> configuración propia en package.jsons
	
	nodemon es una dependencia de desarrollo de package.jsonss
	
	
	- git checkout rama - Moverte entre ramas
	- git stash - encola cambios
	- git stash pop - Regresar los cambios pendientes
	
	- git add -A -> Agregar todos los cambios
	- git add nombreFila - Agrega solo 1 cambio
	- git commit -m 'Comentario del commit'
	- git push origin rama-develop -> subir los cambios después del commit al repo remoto
	- git pull origin rama -> Obtiene la última versión
	- git diff -> cuales son loas diferencias en el archivos modificados localmente
	- git log -> muestra los logs de los commits
	
JWT		->		
Auth0	->		



================================= USO DE GIT EN GITHUB =========================================
echo "# php-jwt" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/carrg/php-jwt.git
git push -u origin master

Curso Git y GitHub
git config --global user.name "Car RG"				->	Establecer nombre de usuario en git
git config --global user.name						->	Consultar el username actual
git config --global user.email "isc.carrg@gmail"	-> 	"
git config --global color.ui true					-> 	Establecer que nos resalte el color
git config --global --list							-> 	Listado de configuraciones

git init											->	Marca el inicio del proyecto
git status											-> 	Nos da el status de nuestro proyecto 	
git add -A 											-> 	Agrega todos los archivos
git commit -m "Comentario"							-> 
git log 											-> 	
git checkout iddelcommit 							-> 	Nos mueve al último commit
git reset --soft iddelcommit						-> 	Solo quita el commit pero no toca el código
git reset --mixed iddelcommit
git reset --hard iddelcommit						-> 	Elimina todo, commit y código
git log > commits.txt								->	Te crea un txt con los logs de los commits
git branch											-> 	Lista las ramas
git branch nombreRama								->	Crea una rama
git commit --amend -m "Comentario"					-> Arreglamos el último commit
git push origin master -f 							-> Fuerza a subir cambios aún que no haya nuevos

Fusiones
Primero vamos a la rama que va a abserover, ejemplo master
git checkout master
git merge develop									-> 	Master va a abserover a develop

git branch -D nombreRama							-> 	Se elimina una rama
git branch -b nombreRama							->	Creamos rama pero al mismo tiempo nos movemos a ella

git add remote origin URL							-> 	Agrega o vincula directorio remoto						
git remote -v 										-> 	Nos lista el proyecto remoto
git remote remove origin							->	Quita el directorio remoto, o desvincula

Tags
Es par asignar versiones a algún commit en especifico
git tag -a v1.0	-m "Comentario"						-> 	Se crea un tag con comentario
git tag v1.0										-> 	Tag ligera
git tag -a v1.0	-m "Comentario" iddelcommit			->	Se le agrega un tag a un commit anterior al último
git push origin versiondeltag(v1.0)					->	Para subir el tag al gestionador
git push origin --tags								->	Se encarga de subir todos los tags

git branch -a 										-> 	Muestra todas las ramas, hasta la oculta

Workflows
git fetch origin 									-> 	Pasamos los cambios a la rama oculta
git merge origin/nombreRama							->	Pasar los cambios a la rama local

Cuando ambas personas hacen un commit y ninguno se descarga la última versión al primero que haga un push lo dejará sin problemas pero al segundo primero
le pedirá que descargue la última versión y después lo dejará que haga el push, pero antes debe hacer un commit para respaldar sus cambios
git fetch origin 									-> 	Pasamos los cambios a la rama oculta
git merge origin/nombreRama							->	Pasar los cambios a la rama local
Se arregla el conflicto y se vuelven a aplicar los cambios con:
git add -A
git commit -m "Comentario"
git push origin nombreRama

Forks
Haremos fork a un codigo, jQuery por ejemplo, se pasará a nuestra area de trabajo
Cuando querramos trabaja en jQuery tenemos que ejecutar:
git fetch upstream									-> 	Obtiene todas las actualizaciones del proyecto no nuestro
git fetch origin 									-> 	Pasamos los cambios a la rama oculta
git merge origin/nombreRama							->	Pasar los cambios a la rama local

Para hacer un pullrequest
Primero subimos los cambios a nuestra copia hecha con fork
Una vez echo eso, vamos a github y le damos click en new pullrequest para que se realice en automatico la petición a dueño del código

Conectar SSH
en consola usamos el comando: ssh-keygen
Nos crea una carpeta oculta .ssh, entramos y dentro hacemos type id_rsa.pub
y nos dará un código ese codigo lo vamos a meter en github en ssh keys
vamos a configuracion en el github que esta en la parte del perfil, 
seleccionamos SSH and GPG keys y ahí metemos el código rsa.
Después debemos cambiar el directorio remote (git add remote origin URL) pegando en que nos brinca github con seguridad ssh

GitHooks
Hay 17 hooks, son acciones que activan un script para realizar alguna acción
