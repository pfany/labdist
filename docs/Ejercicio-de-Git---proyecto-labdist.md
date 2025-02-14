---
author: Epifanía Peralta López
title: Ejercicio de Git - proyecto labdist
---

# Ejercicio de Git - proyecto labdist

> Documento realizado por **Epifanía Peralta López** para Despliegue de Aplicaciones Web- distancia

[TOC]

## Trabajo en local

> Esta parte se realiza con comandos.

### Cuestión 1

Inicializa un nuevo repositorio Git en una carpeta llamada `"labdist"` y agrega los archivos proporcionados en el aula virtual. Renombra la rama master a `main`, si es necesario. Realiza el primer commit. Muestra el log del repositorio.



Primeramente abro GitBash desde la carpeta Labdist y compruebo mi user.name y user.email:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204171254969.png" alt="image-20250204171254969" style="zoom:50%;" />

Mi editor de textos por defecto es el VSCode.

Como se indica en el enunciado, antes de comenzar el trabajo, escribo el comando para que el historial de ramas de Git se mantenga como un árbol:

```bash
git config --global merge.ff false
git config --global -e	//para verificar que tengo los archivos 							en la carpeta
git init		//para inicializar el repositorio	
git add .		//para indicar los archivos que quiero seguir
git status -s	//me indica lo que hay en el staging area
git commit -m "Primer commit con archivos iniciales"
git log --oneline	
```



En GitBash:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204172624255.png" alt="image-20250204172624255" style="zoom:50%;" />



El primer commit y el log:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204180306074.png" alt="image-20250204180306074" style="zoom:50%;" />



### Cuestion 2

Incluye un fichero `.gitignore` para que los ficheros `README.md`, `LICENSE.txt` y `passwords.txt` sean ignorados por el control de versiones. Realiza el commit y muestra los logs del repositorio en una línea.

Lo primero es crear los 3 archivos: README.md, LICENSE.txt y passwords.txt. Lo realizo en el explorador de Windows.

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204183333489.png" alt="image-20250204183333489" style="zoom:50%;" />

También he creado el archivo `.gitignore` en el VSCode e incorporo esos 3 archivos para que sean ignorados por el control de versiones.

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204183516556.png" alt="image-20250204183516556" style="zoom:50%;" />

Incluyo los archivos en el VSCode:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204183628046.png" alt="image-20250204183628046" style="zoom:50%;" />

```bash
git status -s
git add .gitignore
git commit -m "Agregado el archivo .gitignore"
git log --oneline
```



<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204184140466.png" alt="image-20250204184140466" style="zoom:50%;" />



### Cuestion 3

En el repositorio, crea los archivos `README.md`, `LICENSE.txt` y `passwords.txt` con algún contenido. Muestra el estado del repositorio. Muestra el estado de archivos ignorados.



Creo contenido en los 3 archivos indicados:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204184429118.png" alt="image-20250204184429118" style="zoom: 50%;" />

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204184517947.png" alt="image-20250204184517947" style="zoom:50%;" />

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204184617938.png" alt="image-20250204184617938" style="zoom:50%;" />



Para mostrar el estado del repositorio y el listado de archivos ignorados:

```bash
git status -s
git cat .gitignore
```

En `git status -s` no sale nada ya que ese archivo y su contenido he indicado que precisamente no sea controlado por **Git**.

Como `.gitignore` es un archivo, hice un `cat` para que me muestre lo que contiene.

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204185345142.png" alt="image-20250204185345142" style="zoom:50%;" />

También con:

```bash
git ls-files --other --ignored --exclude-standard
```



<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204192913275.png" alt="image-20250204192913275" style="zoom:50%;" />

### Cuestión 4

Crea una rama `feature-estilos`. Cámbiate a ella.

* Modifica el archivo `estilos.css`:
  * propiedad color del `body` y de `h2`:`#2a2a2a`
  * propiedad `background-color` de `header`y `footer: #2a75ff`
* Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje "actualizados estilos a azules"



Bien, en este punto me he dado cuenta que no cambié el nombre a `master`:

```bash
git branch -m main
```



<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204190606657.png" alt="image-20250204190606657" style="zoom:50%;" />



Para crear la rama `feature-estilos` y cambiarme a ella:

```bash
git branch feature-estilos
git checkout feature-estilos
//realizo los cambios en el archivo CSS
git status -s		//para ver los cambios en el repositorio
git add .
git commit -m "Actualizados estilos a azules"
```



En el CSS:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204193702343.png" alt="image-20250204193702343" style="zoom: 33%;" /><img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204193740450.png" alt="image-20250204193740450" style="zoom: 50%;" />

En GitBash:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204194107383.png" alt="image-20250204194107383" style="zoom:50%;" />



### Cuestión 5

Vuelve a la rama `main`. En el archivo `index.html` añade un comentario donde se indique tu nombre como autor de la página. Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje 'añadido autor en index'. Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'



```bash
git checkout main
//añado un comentario en el index.html con mi nombre como autor
git status -s
git add index.html
git commit -m "Añadido autor en index"
git log --oneline --all --decorate --graph
```





En `index.html`:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204194701274.png" alt="image-20250204194701274" style="zoom:50%;" />

En GitBash:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204195333050.png" alt="image-20250204195333050" style="zoom:50%;" />



### Cuestión 6

Fusiona la rama `feature-estilos` en la rama `main`. Muestra los logs del repositorio en una línea, gráficamente y con decoración.

```bash
git merge feature-estilos	//ya estaba en la main
git log --oneline --all --decorate --graph
```



En GitBash:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204200034748.png" alt="image-20250204200034748" style="zoom:50%;" />





## Trabajo en remoto

> Esta parte se realizará con la herramienta gráfica ***Sourcetree*** y con ***GitHub***.

Primeramente compruebo que la opciones de SourceTree estén de la siguiente forma:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204201520256.png" alt="image-20250204201520256" style="zoom:50%;" />

### Cuestión 1

Continúa con el repositorio `labdist`. Añade el repositorio a **SourceTree**.

En SourceTree, añado el repositorio:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204202753827.png" alt="image-20250204202753827" style="zoom: 33%;" />

Y el resultado es éste:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204202915179.png" alt="image-20250204202915179" style="zoom:33%;" />



### Cuestión 2

En tu cuenta de GitHub, crea un repositorio remoto y sube al remoto los ficheros de tu repositorio local. Debes subir <u>todas</u> las ramas. Muestra, además, la captura de pantalla donde se vean en GitHub.



En mi cuenta de GitHub creé un nuevo repositorio llamado **Labdist**.

En **SourceTree** configuré el repositorio para que se vinculara:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204210733651.png" alt="image-20250204210733651" style="zoom:50%;" />

Y subo todas las ramas:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204210945637.png" alt="image-20250204210945637" style="zoom:50%;" />



Compruebo en GitHub que han subido las 2 ramas:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250204211158252.png" alt="image-20250204211158252" style="zoom: 50%;" />



### Cuestión 3

No existe: salto a la número 4.

### Cuestión 4

En el repositorio <u>local</u>, crea una rama `feature-index`. Añade el siguiente código dentro de la `<section class="about">`. Añade los cambios y crea un commit con el mensaje "Añadido párrafo equipo en index.html". Sube los cambios al remoto. (Recuerda que debes usar el SourceTree en todo este apartado).



El código a añadir dentro de la section indicada es el sg:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209165313614.png" alt="image-20250209165313614" style="zoom:50%;" />

Me encuentro en la rama **main** en el **SourceTree** y desde ahí creo la rama `feature-index`. Dejo marcado **Checkout New Branch**, para ya quedarme en esa rama:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209165525048.png" alt="image-20250209165525048" style="zoom: 33%;" />

Una vez que incorporé el texto a `index.html` en VSCode, al volver a SourceTree, me aparece:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209170450150.png" alt="image-20250209170450150" style="zoom:33%;" />

Y el archivo figura en el Unstaged area:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209170849099.png" alt="image-20250209170849099" style="zoom:50%;" />

Le doy al símbolo + y los cambios pasan al Staging area:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209171104961.png" alt="image-20250209171104961" style="zoom:33%;" />

Para hacer el commit, simplemente en el workspace, aparece abajo una zona para escribir el mensaje.

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209171422432.png" alt="image-20250209171422432" style="zoom:33%;" />



Subo los cambios al remoto:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209172116986.png" alt="image-20250209172116986" style="zoom:33%;" />

En GitHub compruebo que ha subido la nueva rama:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209172254939.png" alt="image-20250209172254939" style="zoom: 50%;" />



### Cuestión 5

En el repositorio local, fusiona la rama `feature-index` en la rama `main`.



Aquí me parece que el ejercicio anterior algo no funcionó.

* borró la rama en GitHub:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209175644182.png" alt="image-20250209175644182" style="zoom:50%;" />

* renombro la rama a `feature-index` que la había escrito antes mal.

* Subo los cambios a GitHub

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209180443541.png" alt="image-20250209180443541" style="zoom:33%;" />

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209180524378.png" alt="image-20250209180524378" style="zoom:33%;" />

  En GitHub compruebo que el cambio en el `index.html` se realizó en la rama correcta: `feature-index`.

Fusiono entonces en el repo local con el SourceTree la rama `feature-index` en la rama `main`.

![image-20250209181243154](./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209181243154.png)



### Cuestion 6

Edita el fichero `contacto.html`. Borra unas líneas. Muestra los ficheros con cambios pendientes y las diferencias. Añade los cambios y haz un commit.

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209181706889.png" alt="image-20250209181706889" style="zoom:33%;" />



Añado los cambios y realizo un commit:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209181902473.png" alt="image-20250209181902473" style="zoom:33%;" />



### Cuestión 7

Te das cuenta del error. Deshaz TOTALMENTE el commit anterior. Captura el estado actual del repositorio. (Asegúrate de que el fichero `contacto.html` ha recuperado todas las líneas borradas y no hay cambios pendientes en el repositorio.)



En el workspace --> history, hago click-dcho sobre el último commit que quiero deshacer:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209183225371.png" alt="image-20250209183225371" style="zoom:33%;" />

Y ahora hago un **Reverse hunk**:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209183518365.png" alt="image-20250209183518365" style="zoom:33%;" />



### Cuestión 8

Crea una rama `feature-mapa` y cámbiate a ella. Incluye este código en el archivo `contacto.html`. Añade los cambios. Realiza un commit.

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209184342314.png" alt="image-20250209184342314" style="zoom: 50%;" />



Una vez añadido código en VSCode del archivo `contacto.html`, en el **SourceTree** se muestra así:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209184603827.png" alt="image-20250209184603827" style="zoom:33%;" />



Añado los cambios:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209184635381.png" alt="image-20250209184635381" style="zoom:33%;" />

Y realizo un commit.

El resultado es el siguiente:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209184756534.png" alt="image-20250209184756534" style="zoom:50%;" />



### Cuestión 9

Sube los cambios al remoto -los de todas las ramas. Muestra en el remoto los cambios del archivo `contacto.html` en la rama `feature-mapa`.

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209184949918.png" alt="image-20250209184949918" style="zoom: 33%;" />



En el remoto:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209185130875.png" alt="image-20250209185130875" style="zoom: 50%;" />

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209185220170.png" alt="image-20250209185220170" style="zoom:50%;" />



### Cuestión 10

En GitHub, en la rama `main`, fusiona la rama `feature-mapa`. Baja los cambios del remoto a local. Deja los dos repositorios sincronizados. Muestra una captura de pantalla donde se vea la página principal de tu repositorio remoto.



En GitHub se hace con **Pull requests** y **New pull request**:

En el desplegable **base** se indica la rama `main`.

En el desplegable **compare** se indica la rama `feature-mapa`.

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209190546622.png" alt="image-20250209190546622" style="zoom:33%;" />

Y en **Open a pull request**, ya me indica **Able to merge**:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209191543175.png" alt="image-20250209191543175" style="zoom: 50%;" />

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209191805151.png" alt="image-20250209191805151" style="zoom: 50%;" />

Para bajar los cambios del remoto al local, hago un pull desde el SourceTree:



<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209192254201.png" alt="image-20250209192254201" style="zoom:33%;" />

Y así es como queda:

* en GitHub:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209192823554.png" alt="image-20250209192823554" style="zoom: 50%;" />

* en SourceTree:



<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250209192946913.png" alt="image-20250209192946913" style="zoom:33%;" />



## Conflictos

> Esta parte se realiza con SourceTree y GitHub.

### Cuestión 1

<u>Enunciado:</u>

Crea una rama `hotfix-js`. Cámbiate a ella. Añade este código en el fichero `script.js`.

```javascript
if (mensaje.value.trim() === "") {
			alert("Por favor, ingrese un mensaje.");
			valid = false;
		}
```



Confirma el cambio y haz un commit con el mensaje "corregido problema en script.js". (Fíjate en los números de línea de tu editor...)

<u>Solución:</u>

Creo una nueva rama llamada `hotfix-js` y me cambio a ella:

![image-20250214114714997](./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214114714997.png)

Me aseguro de estar efectivamente en la rama `hotfix-js` para añadir código en el fichero `script.js`:



<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214115501318.png" alt="image-20250214115501318" style="zoom:50%;" />

Fueron añadidas 4 líneas (25-28).

Añado los cambios:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214115734535.png" alt="image-20250214115734535" style="zoom: 33%;" />

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214115924984.png" alt="image-20250214115924984" style="zoom:50%;" />

Y realizo el commit con el texto indicado:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214120101787.png" alt="image-20250214120101787" style="zoom:50%;" />



### Cuestión 2

<u>Enunciado</u>:

Vuelve a la rama `main`. En el fichero `script.js`en las mismas líneas que en la cuestión anterior, añade el código siguiente.

```javascript
if (mensaje.value.trim() === "") {
			alert("Ingrese un mensaje, por favor.");
			valid = false;
		}
```



Confirma el cambio y haz un commit con el mensaje "corregido problema en script.js rama main".

<u>Solución</u>:

Estoy en la rama `main`:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214120908369.png" alt="image-20250214120908369" style="zoom:50%;" />



No tenía cerrado el archivo `script.js` en el VSCode y al volver a él, veo que NO FIGURAN LOS CAMBIOS QUE HICE ANTES porque eran de la otra rama (¡fantástico!).

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214121246560.png" alt="image-20250214121246560" style="zoom:33%;" />

Entonces añado el texto indicado en el fichero `script.js`, en la misma línea de antes (25-28):

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214121450552.png" alt="image-20250214121450552" style="zoom:50%;" />

En el SourceTree confirmo el cambio y realizo el commit con el mensaje indicado:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214121700781.png" alt="image-20250214121700781" style="zoom: 33%;" />

Queda así:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214121757256.png" alt="image-20250214121757256" style="zoom:50%;" />

Hasta aquí, no salta ningún conflicto.



### Cuestión 3

<u>Enunciado</u>:

Fusiona la rama `hotfix-js` en `main`. Debe producirse un conflicto. Resuélvelo como consideres oportuno. Cuando termines la resolución del conflicto sube los cambios al remoto.



<u>Solución</u>:

Para fusionar la rama `hotfix-js` en `main`:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214122600057.png" alt="image-20250214122600057" style="zoom:50%;" />

Y me sale la siguiente pantalla:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214122658743.png" alt="image-20250214122658743" style="zoom:50%;" />

En el pantallazo no sale que en la esquina inferior derecha hay un OK para hacer click.

La ventana se cierra y pasa nada.

Pruebo de esta otra forma: estoy en la rama `main` y hago click-dcho sobre la rama `hotfix-js`; se abre un desplegable y eligo "Merge hotfix-js en main":

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214123205445.png" alt="image-20250214123205445" style="zoom:50%;" />

Me sale el siguiente aviso:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214123300268.png" alt="image-20250214123300268" style="zoom:50%;" />

Al aceptar, aparece la siguiente ventana:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214123343345.png" alt="image-20250214123343345" style="zoom:50%;" />

Cierro la ventana. 

Voy a resolver el conflicto en la línea utilizando el VSCode:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214123632073.png" alt="image-20250214123632073" style="zoom:50%;" />

Muy fácil, pulso en "Aceptar cambio actual" y automáticamente corrige el código; guardo y me vuelvo al SourceTree, donde le indico que el conflicto ha sido resuelto:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214124403755.png" alt="image-20250214124403755" style="zoom:33%;" />

Y me pide confirmación:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214132836437.png" alt="image-20250214132836437" style="zoom:33%;" />

Estoy en este punto:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214132943539.png" alt="image-20250214132943539" style="zoom:50%;" />

Hago el commit:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214133246594.png" alt="image-20250214133246594" style="zoom: 50%;" />

Y ya me figura la fusión de las ramas:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214133355932.png" alt="image-20250214133355932" style="zoom:50%;" />

Y, por último, subo los cambios al repo remoto en GitHub:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214133605638.png" alt="image-20250214133605638" style="zoom:50%;" />



## Resultado de los ejercicios

* En el SourceTree:

<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214134241309.png" alt="image-20250214134241309" style="zoom:50%;" />



* En GitHub:



<img src="./Ejercicio-de-Git---proyecto-labdist.assets/image-20250214134403303.png" alt="image-20250214134403303" style="zoom:50%;" />



## URL en GitHub

[https://github.com/pfany/labdist.git](https://github.com/pfany/labdist.git)



## Enlace al videoclip

[]()

