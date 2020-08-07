# 01 - CONFIGURAR REPOSITORIO

### 1. Crear repository en Github

### 2. Crear la carpeta .github/workflows en la raíz del proyecto

### 3. Añadir el archivo .github/CODEOWNERS

Por ejemplo:

```txt
* @{github-username}
*.js  @{github-username}
/src/moduleX/ @{github-username}
```

### 4. Asignarlo al proyecto

```bash
git remote add origin https://github.com/{author}/{project-name}.git
git push -u origin master
```

### 5. Crear rama **develop** en github

### 6. Proteger la ramas **master** y **develop**

Github project > Settings > Branches > Branch protection rules > Add rule

Establecer los siguientes valores para cada una de las ramas (master y develop)

![image info](./protect-branch.png)

Ahora, si se intenta subir algo directamente a estas ramas, dará un error:

```bash
➜  workflow-react git:(master) ✗ git push
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (7/7), 202.37 KiB | 22.49 MiB/s, done.
Total 7 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: error: GH006: Protected branch update failed for refs/heads/master.
remote: error: Waiting on code owner review from rober-dev.
To https://github.com/rober-dev/workflow-react.git
 ! [remote rejected] master -> master (protected branch hook declined)
error: failed to push some refs to 'https://github.com/rober-dev/workflow-react.git'
➜  workflow-react git:(master)
```

### 7. Añadir un colaborador (para que apruebe los cambios)

### 8. Crear una rama local para trabajar y poder subir los cambios.
Por ejempo:

```bash
git checkout -b workflow
```
