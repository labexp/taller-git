# Taller Git - Guía de pasos a seguir 

### 1. Crear un repositorio: 
Ir a [https://gitlab.com/](https://gitlab.com/), iniciar sesión y presionar el botón New Project. Les pedirá un nombre para su nuevo repositorio, dan a aceptar una vez hayan nombrado el repositorio y  estará creado.

### 2. Hacer copia local en su computadora: 
Para esto deberá copiar el enlace de su repositorio, ir a su terminal e ingresar el siguiente comando: 
```

    $git clone <URLrepositorio>

```
Entre las boquillas <> debe ir el enlace de su repositorio(sin las boquillas).
### 3. Generar código en el repositorio local: 
Debe ingresar en la carpeta local donde se encuentra el repositorio y crear un nuevo archivo nombrado "fibo. py" donde se encuentre un algoritmo que retorne el valor de Fibonacci de cualquier número. 

### 4. Guardar los cambios del repositorio local:
A continuación se van a guardar los cambios del repositorio local.
Para ver todos los cambios sin agregar al repositorio utilizamos:

    $git status
Aparecerá en rojo todos los archivos que no han sido salvados.
Ingrese el siguiente comando estando dentro del repositorio local:

    $git add . 
En este momento sus cambios han sido agregados de manera local. Para verificar que el proceso fue correcto vuelva a utilizar el comando:

    $git status 
Todos los archivos en verdes ya han sido agregados correctamente. 

### 5. Comentar los cambios guardados: 
Se deben comentar los cambios para luego poder actualizar el repositorio remoto. 
Para eso en la misma carpeta del repositorio local ingresar: 

    $git commit -m "se agrega el código de fibonacci"
Entre las comillas(" ") se debe agregar un mensaje significativo que describa en detalle los cambios efectuados. 
 
### 6. Subir los cambios al repositorio remoto:
Para subir los cambios en el repositorio remoto se debe ejecutar el siguiente comando: 

    $git push origin master 
Donde master puede ser el nombre de cualquiera de los branches creados por el usuario. 

### 7. Bajar cambios de otros usuarios: 
Desde el browser, en gitlab se va a crear un archivo READ.me y dentro se va a colocar una descripción del repositorio. Se guardan los cambios en el repositorio remoto y volvemos a la terminal para actualizar el repositorio local.
Ahí se debe insertar el siguiente comando:

    $git pull origin master 
  Con este comando se actualizará nuestro repositorio local con los cambios del repositorio remoto.
  
  **Nota:** Es una buena práctica actualizar el repositorio en cada sesión de trabajo. 

### 8. El uso del branch:
Para crear un nuevo branch se utiliza el siguiente comando: 

    $git branch <nombreBranch>
Donde <> se debe poner el nombre del nuevo branch(sin las boquillas). 
Para este ejemplo utilizaremos el nombre "develop"
Una vez creado para pasar a ese branch se utiliza el siguiente comando: 

    $git checkout develop

Para notar la los cambios entre los branch, cree un archivo estando en el nuevo branch llamado "ejemplo. txt". 
Una vez creado ejecute:

    $git checkout master
 Al pasar a este branch podrá notar que ejemplo. txt no existe en la carpeta. 
### 9. Uso del merge: 
El comando merge nos permite unir los contenidos de un branch con otro, así podemos unir todos los cambios efectuados por varios usuarios una vez no existan conflictos en el repositorio.

Para unificar los branch utilizamos:

    $git merge develop 
Este comando debe ser ejecutado en el branch master, el cual es el que deseamos unificar con develop.

Esto creará una petición en el repositorio remoto en gitlab.com. Uno de los usuarios que formen parte del repositorio deberá aceptar el merge para que surja efecto. Se espera que quien revise la petición no sea el mismo que la generó, esto con el fin de revisar los cambios efectuados e impedir errores en el código o bien código que no se requería. 

Si nos fijamos ahora el branch master tiene ejemplo. txt como un archivo.
