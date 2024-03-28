Configuración Remotos

Básicamente, tenemos una copia completa de un repositorio, en cuyo origen no se nos permite hacer cambios.

Veamos cómo se configuran los controles remotos de este Git:

	git remote -v
	origin  https://github.com/w3schools-test/w3schools-test.github.io.git (fetch)
	origin  https://github.com/w3schools-test/w3schools-test.github.io.git (push)

Vemos que el origen está configurado en el repositorio original "w3schools-test", también queremos agregar el nuestro propio fork.

Primero, cambiamos el nombre del original origin remote:

	git remote rename origin upstream
	git remote -v
	upstream        https://github.com/w3schools-test/w3schools-test.github.io.git (fetch)
	upstream        https://github.com/w3schools-test/w3schools-test.github.io.git (push)

Entonces hacer fetch la URL de nuestro fork. Y agrégarlo como origen:

	git remote add origin https://github.com/kaijim/w3schools-test.github.io.git
	git remote -v
origin  https://github.com/kaijim/w3schools-test.github.io.git (fetch)
origin  https://github.com/kaijim/w3schools-test.github.io.git (push)
upstream        https://github.com/w3schools-test/w3schools-test.github.io.git (fetch)
upstream        https://github.com/w3schools-test/w3schools-test.github.io.git (push)
Nota: De acuerdo con las convenciones de nomenclatura de Git, se recomienda nombrar tu propio repositorio como origin, y el forked como upstream

Ahora tenemos 2 remotos:

Ahora vamos a hacer algunos cambios en el código.
