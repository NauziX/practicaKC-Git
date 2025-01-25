# Practica de KeepCoding 
### Alumno: Nauzet Fernández
### Profesor: Alberto Casero

## ¿Qué comando utilizaste en el paso 11? ¿Por qué?
### 11. Deshacer el último commit (perdiendo los cambios realizados en el working copy)

 Usé el comando: 
```git reset --hard HEAD~1```
Este comando me sirvió para mover el puntero HEAD al commit anterior (por eso el ~1)
el --hard hace que también se borren los cambios que tenía en el staging area y en el working copy.

## ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
### 12. Rehacer el último commit (el que acabamos de deshacer)

Primero hice un: ```git reflog``` esto me dio la lista de commits recientes para ver el hash que necesitaba, en este caso: dcaf08e.

<img width="700" alt="image" src="https://github.com/user-attachments/assets/d4a25f7d-feb7-4ad7-8644-c6e325487936" />
<br>

Luego usé este comando para volver a ese commit: ``` git reset --hard dcaf08e ```

## El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
### 13. Hacer un merge con ‘main’ (styled absorbe a main)

Primero me aseguré de estar en la rama styled con: ```git checkout styled```
después hice el merge: ```git merge main``` no hubo conflictos porque las ramas no tenían cambios en las mismas líneas del archivo git-nuestro.md

## El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
### 19. Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)

Me aseguré de estar en la rama styled con: ```git checkout styled```
después hice el merge con : ```git merge htmlify``` 
Este sí tuvo conflictos porque tanto htmlify como styled modificaron las mismas líneas del archivo git-nuestro.md resolví los conflictos manualmente

## El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
### 21. Desde “main”, hacer un merge con “styled”

Nos aseguramos de estar en la rama main: ```git checkout main``` hice el merge con: ```git merge styled```
Este merge no causó ningún conflicto, la razón es que los cambios realizados en la rama styled ya habían sido fusionados correctamente

## ¿Qué comando o comandos utilizaste en el paso 25? ¿Por qué?
### 25. Dibujar el diagrama

Para ver el diagrama del historial de commits, utilicé:  ```git log --graph```
<br>
<img width="700" alt="image" src="https://github.com/user-attachments/assets/35d52e33-f016-4398-accd-689f2a0264f5" />
<br>
Esto me mostró las ramas y cómo se conectaban

## El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

Sí, el merge podría haber sido fast-forward, porque main no tenía nuevos commits desde que se creó title. Title contenía todo el historial de main
así que el puntero simplemente se habría movido hacia adelante

## ¿Qué comando o comandos utilizaste en el paso 27? ¿Por qué?
### 27. Deshacer el merge (sin perder los cambios del working copy)

Usé el comando: ```git reset HEAD~1``` igual que ejercicio 11 pero como queremos preservar los cambios del working copy sin el --hard.
Este comando deshace el último commit (en este caso, el commit de merge).

## ¿Qué comando o comandos utilizaste en el paso 28? ¿Por qué?
### 28. Descartar los cambios

El comando que utilicé fue: ```git checkout git-nuestro.md``` 
Esto descartó los cambios solo en el archivo git-nuestro.md, restaurándolo al estado del último commit

## ¿Qué comando o comandos utilizaste en el paso 29? ¿Por qué?
### 29. Eliminar la rama “title”

Para este paso, utilicé: ```git branch -D title``` 
Este comando elimina la rama title de forma forzada

## ¿Qué comando o comandos utilizaste en el paso 30? ¿Por qué?
### 30. Rehacer el merge que hemos deshecho

Primero usé git reflog para buscar el commit del merge anterior. En mi caso, el commit es: a813d66.
<img width="700" alt="image" src="https://github.com/user-attachments/assets/d5ce3284-e3b7-406a-9881-530aa617c5b5" />
<br>
luego utilizamos el comando: ```git reset --hard a813d66```
Esto me devolvió al estado exacto donde se había hecho el merge antes.  

## ¿Qué comando o comandos usaste en el paso 32? ¿Por qué?
### 32. Volver al commit inicial cuando se creó el poema

En este caso usé el comando:  ```git log ```
<br>
<img width="700" alt="image" src="https://github.com/user-attachments/assets/6d59af23-c816-4f05-a3da-bc1a866eee42" />
<br>
vemos que el hash del commit inicial es: 4806ade
ahora usamos el comando:  ```git reset --hard 4806ade ```
Esto me devolvió al estado exacto del primer commit.

## ¿Qué comando o comandos usaste en el paso 33? ¿Por qué?
### 33. Volver al estado final, cuando pusimos título al poema

Usé el comando:  ```git reflog ``` 

<img width="700" alt="image" src="https://github.com/user-attachments/assets/b2aa7797-3dc5-410a-8f88-a6bea827085e" />

<br>
vemos que  el hash de cuando añadimos el titulo : b58127c

Usé el comando: ``` git reset --hard b58127c ```
Esto restauró al commit donde se añadió el título al poema.
