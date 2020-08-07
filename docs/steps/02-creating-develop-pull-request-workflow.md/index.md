# 02 - CREAR EL WORKFLOW DE LOS PULL REQUEST DE LA RAMA DEVELOP

### 1. Crear el archivo de workflow en .github/workflows/ci.yml

Los pasos que se ejecutan en el workflow son:

1. Hacer un checkout de la rama
2. Instala node.js v12.x
3. Instala las dependencias con npm ci (parecido a npm install)
4. Ejecuta la tarea del formato (con prettier)
5. Pasa los test con covertura de código y ENV=CI

```yml
name: CI

on:
  pull_request:
    branches: [develop]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Use NodeJS
        uses: actions/setup-node@v1
        with:
          node-version: '12.x'
      - run: npm ci
      - run: npm run format:check
      - run: npm test -- --coverage
        env:
          CI: true
```

### 2. (Trabajando en la rama workflow) commiteamos los cambios y subimos la rama.

```bash

```
