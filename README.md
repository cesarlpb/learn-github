# learn-github

Repositorio para aprender Github paso a paso.

Crea un `Fork` para contribuir, más información: [cómo contribuir a este repositorio](CONTRIBUTING.md).

---

## Índice

- [Ejercicio 1](#ejercicio-1)
- [Ejercicio 2](#ejercicio-2)
- [Ejercicio 3](#ejercicio-3)
- [Ejercicio 4](#ejercicio-4)
- [Ejercicio 5](#ejercicio-5)
- [Ejercicio 6](#ejercicio-6)

---

### Ejercicio 1

1. Vamos a imaginar que trabajamos en un libro sobre Git y queremos hacer algunos temas. Se va a trabajar en ramas para cada capítulo. Implementa las siguientes **ramas** con al menos un archivo y un commit con cualquier contenido:

- `introduccion` -> intro.txt, intro.md...
- `capitulo01` -> capitulo01.txt...
- `capitulo02` -> capitulo02.txt...

Finalmente, vamos a fusionar todos estos contenidos en `libro`. El resultado debe ser algo como:

```
intro.txt
capitulo01.txt
capitulo02.txt
etc.
```

- `git log` debe mostrar los commits de cada rama más el commit de merge.

2. resolución

```bash
git checkout -b introduccion
echo "introduccion" > intro.txt
git add intro.txt
git commit -m "introduccion"
git checkout -b capitulo01
echo "capitulo01" > capitulo01.txt
git add capitulo01.txt
git commit -m "capitulo01"
git checkout -b capitulo02
echo "capitulo02" > capitulo02.txt
git add capitulo02.txt
git commit -m "capitulo02"
git checkout introduccion
git merge capitulo01
git merge capitulo02

```

3. Resultado del `git log --oneline`

   3.1 ![Resultado del git log](./src/img/ejercicio1.png)

---

## Ejercicio 2

### Objetivo:

Aprender a clonar un repositorio remoto en tu máquina local.

### Instrucciones:

1. Busca un repositorio público en GitHub que te interese o usa este repositorio de ejemplo:  
   `[URL_DEL_REPOSITORIO]`
2. Abre tu terminal y ejecuta el siguiente comando para clonar el repositorio en tu máquina local:
   ```bash
   git clone https://github.com/usuario/repo.git
   ```
3. Accede al directorio del repositorio clonado:
   ```bash
   cd repo
   ```
4. Verifica que la clonación fue exitosa listando los archivos del repositorio.

### Resultados:

1. Clonamos el repositorio de `cv_backend`.

   1.1 ```bash
   git clone [cv_backend](https://github.com/cdryampi/curriculum-backend.git)

   ```

   ```

2. Accedemos al directorio del repositorio clonado.

   2.1 ```bash
   cd curriculum-backend

   ```

   ```

3. Listamos los archivos del repositorio.

   3.1 ```bash
   dir

   ```

   ```

4. Resultado de la clonación.
   4.1 ![Resultado de la clonación](./src/img/ejercicio2.png)

---

## Ejercicio 3

### Objetivo:

Practicar cómo sincronizar los cambios entre el repositorio local y el remoto.

### Instrucciones:

1. Abre el repositorio clonado en el ejercicio anterior.
2. Crea un nuevo archivo llamado `mi_archivo.txt` y agrega algo de texto en él.
3. Agrega y confirma los cambios:

   ```bash
   git add mi_archivo.txt
   git commit -m "Agregado mi_archivo.txt"
   ```

4. Envía los cambios al repositorio remoto:

   ```bash
   git push origin main
   ```

5. Si hay nuevos cambios en el repositorio remoto realizados por otros colaboradores, actualiza tu repositorio local con:

   ```bash
   git pull origin main
   ```

6. Verifica que los cambios se han fusionado correctamente.

### Resultados:

1. Vamos a realizar una push hacia el repositorio remoto desde la rama del `libro`.

```bash
git add .
git commit -m "cambios en el libro"
git push origin libro
```

2. Vamos a modificar el fichero desde el repositorio remoto y hacer un pull para traer los cambios.

```bash
git pull origin libro
```

3. Resultado de la modificación y el pull.

   3.1 ![Resultado de la modificación y el pull](./src/img/ejercicio3-1.png)

---

## Ejercicio 4

### Objetivo:

Aprender a hacer un **fork** de un repositorio para trabajar en una copia independiente.

### Instrucciones:

1. Busca un repositorio en GitHub que permita contribuciones y haz un **fork** del mismo.
2. Ve a tu perfil y verifica que el repositorio ahora aparece en tu cuenta.
3. Clona tu fork en tu máquina local con:

   ```bash
   git clone https://github.com/tu_usuario/nombre_del_fork.git
   ```

4. Confirma que has clonado el repositorio correcto verificando su origen con:

   ```bash
   git remote -v
   ```

### Resultados:

1. Hicimos un fork del repositorio `learn-github`.

   1.1 [Fork de learn-github](./src/img/ejercicio3.png)

2. Comprobamos que tenemos el repositorio correctamente y conectado en el remoto.

```bash
   PS C:\codigo\learn-github> git remote -v
   origin  https://github.com/cdryampi/learn-github.git (fetch)
   origin  https://github.com/cdryampi/learn-github.git (push)
```

---

## Ejercicio 5

### Objetivo:

Aprender a proponer cambios en un repositorio original mediante un Pull Request.

### Instrucciones:

1. Clona tu **fork** del repositorio (si no lo hiciste en el ejercicio anterior).
2. Crea una nueva rama para trabajar en una mejora o corrección de código:

   ```bash
   git checkout -b mejora-README
   ```

3. Realiza cambios en el código (por ejemplo, edita el archivo `README.md`).
4. Guarda y confirma los cambios:

   ```bash
   git add README.md
   git commit -m "Mejorado el README con información adicional"
   ```

5. Sube la rama a tu repositorio en GitHub:

   ```bash
   git push origin mejora-README
   ```

6. En GitHub, ve a la página de tu fork y presiona el botón **"Comparar y hacer Pull Request"**.
7. Explica los cambios que hiciste y envía el Pull Request al repositorio original.

### Resultados:

1. Vamos a hacer una PR al la rama `resultados` con los cambios de la rama ``libro` que estamos trabajando.

   1.1 ![Resultado de la PR](./src/img/ejercicio5.png)

2. Cuando se acepte la PR, se fusionarán los cambios en la rama `resultados`.

3. Tenemos que hacer un pull para traer los cambios a la rama `resultados`.

```bash
git pull origin resultados
```

4. Ahora ya podemos trabajar con la rama de `resultados`.
   4.1 ![Resultado del pull](./src/img/ejercicio5-1.png)

## **Importante: Tenemos los Forks de todos compañeros, hay que asegurarse que seleccionamos de origen mi rama de mi repositorio y como compare la rama de cambios**

---

## Ejercicio 6

### Objetivo:

Familiarizarse con la contribución a proyectos Open Source en GitHub.

### Instrucciones:

1. Busca un proyecto Open Source en GitHub que acepte contribuciones y haz un **fork**.
2. Lee las directrices del proyecto (`CONTRIBUTING.md` o `README.md`).
3. Identifica un problema en la sección de **Issues** y asígnatelo si es posible.
4. Crea una nueva rama con un nombre descriptivo y realiza los cambios en el código.
5. Confirma y sube los cambios a tu fork.
6. Abre un **Pull Request** siguiendo las normas del proyecto.
7. Espera la revisión del equipo del proyecto y realiza cambios si es necesario.
8. Una vez aceptado el PR, celebra tu primera contribución Open Source 🎉.

### Resultados:

1. Hicimos un fork del repositorio `learn-github`.

   1.1 [Fork de learn-github](./src/img/ejercicio3.png)

2. Hemos leído las recomendaciones para realizar una contribución.

   2.1 [Recomendaciones para contribuir](./CONTRIBUTING.md)

3. Vamos a crearnos una Issue para asignarnosla en el repositorio de propio.

   3.1 **Importante:** No podemos asignarnos una Issue en un repositorio donde no somos colaboradores.
   3.2 [Issue asignada](./src/img/ejercicio6-1.png)
   3.3 link de la Issue: [Enlace de la Issue](https://github.com/cesarlpb/learn-github/issues/13)

4. Vamos a inviar nuestra rama a la rama `resultados` para que se vea en el repositorio original.

   4.1 Solo vamos a Enviar la PR, no podemos hacerla porque no somos colaboradores del repositorio original.
   4.2 Esperamos que el propietario del repositorio acepte la PR.

---
