# Proyecto: la vamos a liar — Nivel 1

En este primer nivel vamos a aprender lo más básico de Git y GitHub.  
**Todos trabajaremos directamente en el mismo repositorio de GitHub, en la rama `main`.**

---

## 📘 Instrucciones

- Cada uno añadirá un archivo con su nombre en la carpeta `equipo/` desde el **terminal**.
- Ese archivo debe contener una frase corta.
- Todos trabajaremos directamente sobre la rama `main` del repositorio.  

### ✅ Pasos a seguir
1. He creado este repositorio en GitHub:  
     **https://github.com/Mig-Iribas/lavamosaliar**

2. Hay que entrar a ese repositorio y **copiarlo en tu ordenador (clonarlo)**.  
   De esa forma todos empezamos desde el mismo sitio.

3. Dentro de la carpeta `equipo/`, cada uno debe crear un archivo con su nombre.  
   Ejemplo: `equipo/Miguel.txt`.

4. En ese archivo escribe una frase corta.   
   Ejemplo:  
   ```
   Hola, soy Miguel y me aburría esta mañana.
   ```
5. Guarda los cambios en tu repositorio local con un mensaje claro.  

6. Sube los cambios al repositorio en GitHub, en la rama `main`.  

7. Comprueba en GitHub que tu archivo aparece dentro de la carpeta `equipo/`.

**Resultado esperado**:  
La carpeta `equipo/` contendrá un archivo por cada uno de nosotros, cada cual con su frase.  
Como todos trabajamos en archivos diferentes, no deberían aparecer conflictos. Eso lo dejamos para el próximo nivel.

---

## 💻 Comandos básicos (lista breve)

- `git clone <URL>` — Copia el repositorio remoto a tu ordenador (solo la primera vez).
- `git pull origin main` — Trae y combina los últimos cambios de `main` desde GitHub. Actualiza.
- `git add equipo/tu_nombre.txt` — Pasa el archivo al área de preparación (staging) para el próximo commit.
- `git commit -m "mensaje"` — Guarda en tu repositorio local los cambios que están en staging.
- `git push origin main` — Sube tus commits locales a GitHub en la rama `main`.
- `git pull --rebase origin main` — Actualiza tu rama reordenando tus commits encima de los nuevos (útil si el push falla).

### Opcionales útiles
- `git status` — Muestra el estado: qué rama, qué falta por añadir/confirmar.
- `git log --oneline` — Historial de commits en formato corto.
- `git show` — Detalles del último commit (o de uno concreto con `git show <id>`).
- `git restore --staged <archivo>` — Quita un archivo del staging (deshacer `git add`).
- `git rm <archivo>` — Borra un archivo y deja listo el borrado para el próximo commit.
- `git fetch`— Actualiza la "foto" con los archivos del repositorio en ese momento.

---

## 📝 Ejemplo paso a paso — Nivel 1

### Paso 1. Clonar el repositorio de Miguel desde GitHub
```bash
git clone https://github.com/Mig-Iribas/lavamosaliar.git
```

**Salida esperada:**
```
Cloning into 'lavamosaliar'...
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 5 (delta 0), reused 0 (delta 0)
Unpacking objects: 100% (5/5), done.
```

---

### Paso 2. Entrar en la carpeta del proyecto
```bash
cd lavamosaliar
```

(Sin salida, simplemente cambias de carpeta).

---

### Paso 3. Actualizar el repositorio para tener lo último
```bash
git pull origin main
```

**Salida esperada si ya está al día:**
```
Already up to date.
```

Esta parte no quiero que salga

---


### Paso 4. Crear un archivo con tu nombre en la carpeta `equipo/`
```bash
mkdir -p equipo
echo "Hola, soy Laura y esta es mi aportación." > equipo/laura.txt
```

(Sin salida, simplemente se crea el archivo).

Tambié podemos hacer:
```bash
code .
```
Y crear los arhivos en Visual Studio Code

---
Pero esta sí

### Paso 5. Verificar el estado
```bash
git status
```

**Salida esperada:**
```
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        equipo/laura.txt

nothing added to commit but untracked files present (use "git add" to track)
```

---

### Paso 6. Guardar el archivo y decirle a Git que lo incluya
```bash
git add equipo/laura.txt
```

(Sin salida).

Si vuelves a mirar el estado:
```bash
git status
```

**Salida esperada:**
```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   equipo/laura.txt
```

---

### Paso 7. Hacer un commit con un mensaje
```bash
git commit -m "añade archivo de Laura"
```

**Salida esperada:**
```
[main 1a2b3c4] añade archivo de Laura
 1 file changed, 1 insertion(+)
 create mode 100644 equipo/laura.txt
```

---

### Paso 8. Subir tus cambios al repositorio de Miguel
```bash
git push origin main
```

**Salida esperada:**
```
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 325 bytes | 325.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:USUARIO-DE-MIGUEL/lavamosaliar.git
   9e8d7f6..1a2b3c4  main -> main
```
**Si alguien subió antes que tú su archivo y tu push falla, debes actualizar a la ultima versión que haya en el repositorio y volver a hacer el push**  
   ```bash
   git pull --rebase origin main
   git push origin main
   ```
---

### Paso 9. Verificar en GitHub
- Abre el repositorio en GitHub en el navegador.  
- Entra en la carpeta `equipo/`.  
- Deberías ver tu archivo (`laura.txt`) con tu frase.  

---

## 🏁 Resultado final esperado
- La carpeta `equipo/` contiene los archivos de todos los que lo hayan subido.  
- Cada archivo incluye una frase.  
- Todos los cambios están guardados en la rama `main` del repositorio lavamosaliar.  
- No se han usado ramas en este nivel.
