t# COMANDOS GIT FUNDAMENTALES

#### 📢CONFIGURACIÓN INICIAL

```bash

1. git config --global user.name <"username">
2. git config --global user.email <useremail>

//editor de código
3. git config --global core.editor <codeeditor>

//listado completo de la configuración
4. git config --list

//listado de archivos
5. ls 

// ver contenido del archivo
6.cat archivo.txt

//Alias
$ git config --global alias.graph "log --graph --decorate --all --oneline"


```

---

#### 📢INICIAR UN REPOSITORIO

```bash
git init

```
---
#### TRABAJANDO CON LOS ESTADOS

| Stash | Work | Stage | Commited/Repo |

**El stash es para guardar un cambio puntualmente**

```bash
git stash
// Guarda los cambios provisionales en una area denominada stash
git stash list
// Ver el contenido del area de stash
git stash apply
// Aplica los cambios recientes del area stash en el area de trabajo
git stash drop stash@{n}
// Elimina el cambio n del area stash
git stash branch nombre_rama
// Aplica los cambios recientes del area stash creando una rama denominada nombre_rama

```

**Work es tu directorio de trabajo**

**El Stage es donde agregamos los cambios antes de ser commited o comprometidos**

```bash
// agrega todos los archivos al stage
git add .

// agrega un archivo específico al stage
git add archivo.txt

```

**Commited es como confirmar el stage**

**Con TAG asignamos una etiqueta a ese commit**

```bash
git commit -m "mensaje del commit"

git tag nombre_punto_clave
```


---

#### 📢STATUS

```bash
git status

// abreviado
git status -m 

```
---
#### 📢RESTORE UN STAGE

```bash
git restore --staged archivoenstage.txt

```

**Si hemos borrado pero no añadido al stage podemos recuperar el archivo recién eliminado**

```bash
git restore archivoenstage.txt

```
---

#### 📢MOVERNOS POR COMMITS, BORRADO

```bash
git checkout idcommit

//borra los datos del HEAD tanto en indice como en workdirectory y regresa al commit anterior
git reset --hard HEAD~1

//mantiene cambios en el indice y en el workdirectory para ser commiteados
git reset --soft HAED~1

//mantiene cambios en el area de trabajo pero no en indice
git reset --mixed HEAD~1

//ir a un commit y borrar los posteriores. Si se borraron y vovemos a realizarlo
//se generan de nuevo hasta el commit indicado.
//Es decir, es de ida y de vuelta

git reset --hard idcommit
```

```bash
//Ir a un commit e iniciar nueva rama a partir de el para corregir.
//Luego pudemos hacer merge

git checkout 124facf
git checkout -b nueva-rama

```

#### 📢ELIMINAR ARCHIVO

**Tras eliminar un archivo, status nos dira que hay un cambio.**
\n**Por ello tendremos que añadir el archivo al stage y luego commit**


```bash
//Esto junta el add y el commit 
git rm archivo.txt

```
---
#### 📢CAMBIO DE NOMBRE DE ARCHIVO

```bash
mv archivo.txt archivomodificado.txt

```

**Esto da lugar a una eliminación del archivo antiguo y la creación del nuevo por lo que hay que agregar y comitear ambos cambios**
**Usando git añadimos los cambios directamente al stage**

```bash
git mv archivo.txt archivomodificado.txt

```
---
#### 📢VER LOS CAMBIOS REALIZADOS 

```
// no staged
git diff

// staged
git diff --staged

```
---
#### 📢HISTORIAL

```
// se navega con barra espaciadora
git log
git reflog

// resumido
git log --oneline

```

---
#### 📢TRABAJANDO CON RAMAS

**Comprobar la rama actual**

```
git branch

```

**Crear rama**

```
git branch nombre rama
git checkout -b nombrerama

```

**Selección de rama**

```bash
git switch rama
```

**Merge a la rama actual**

1. Nos posicionamos en la rama a la cual queremos traer los cambios

```bash
git merge nombrerama // rama que quieres traer

```

**Borrar rama** 

```bash
git branch -d rama
```
---
#### 📢GITHUB

1. Crea un repositorio
2. Añadimos el repositorio remoto

```bash
git remote add origin https://github.com/user/repositorio.git

```

3. Subimos los cambios a github. Como main no existe usamos -u para crearla

```bash
git push -u origin main 

```


















