# Proyecto OOP en Java — Guía práctica de Git - Github

> Repositorio de práctica colaborativa: 3 integrantes, mínimo **1 commit por persona**, con cambios **relacionados al README** y a la configuración inicial.

## Objetivos

- Practicar flujo de trabajo con Git/GitHub en equipo.
- Establecer convenciones de ramas y *commits*.
- Dejar listo el esqueleto del proyecto OOP en Java (sin código al inicio).

## Requisitos

- **Java JDK 17+**  
- **Git 2.x+**  
- (Opcional) **IDE**: IntelliJ IDEA / VS Code / Eclipse  
- Cuenta en **GitHub**

## Estructura propuesta (inicial)
```
.
├─ README.md
├─ .gitignore
└─ src/
   └─ main/
      └─ java/
```
> El directorio `src/` puede quedar vacío durante la práctica de Git.

## .gitignore recomendado (Java + IntelliJ + VS Code)

Crea un archivo `.gitignore` con el siguiente contenido:

```
# Java
*.class
*.jar
*.war
*.ear
hs_err_pid*

# Maven/Gradle (si luego se usa)
target/
build/
.gradle/
!gradle/wrapper/gradle-wrapper.jar

# IntelliJ
.idea/
*.iml
out/

# VS Code
.vscode/

# OS
.DS_Store
Thumbs.db
```

---

## Flujo de trabajo (resumen)

1. **Fork** (si aplica) y **clone**:
   ```bash
   git clone <URL-del-repo>
   cd <carpeta-repo>
   ```
2. Configura tu identidad:
   ```bash
   git config user.name "Tu Nombre"
   git config user.email "tu@email.com"
   ```
3. Crea rama para tu aporte:
   ```bash
   git checkout -b docs/<tu-alias>/readme
   ```
4. Edita el `README.md` (agrega secciones, corrige, ejemplos, etc.).
5. *Commit* atómico con convención (ver abajo):
   ```bash
   git add README.md
   git commit -m "docs(readme): añade sección de flujo de trabajo y .gitignore"
   ```
6. Sube tu rama:
   ```bash
   git push -u origin docs/<tu-alias>/readme
   ```
7. Abre un **Pull Request** (PR) y solicita revisión de 1 compañero.
8. *Merge* a `main` cuando el PR esté aprobado y pase las revisiones.

---

## Convenciones de ramas y *commits*

**Ramas:**
- `main` — rama estable
- `docs/<alias>/readme` — cambios al README por cada integrante
- (más adelante) `feat/<alias>/<feature>`, `chore/<alias>/<tarea>`

**Formato de *commit* (tipo(scope): mensaje)**
- `docs(readme): …` — cambios de documentación
- `chore(repo): …` — tareas del repo (gitignore, linters)
- `ci(build): …` — configuración de build/CI (si aplica)

**Ejemplos:**
- `docs(readme): agrega objetivos y requisitos`
- `docs(readme): corrige pasos de push y PR`
- `chore(repo): añade .gitignore para Java/IntelliJ`

> Mantén los *commits* **pequeños, claros y temáticos**.

---

## Guía rápida de comandos útiles

**Clonar y crear rama**
```bash
git clone <URL>
cd <repo>
git checkout -b docs/<alias>/readme
```

**Agregar y *commitear***
```bash
git status
git add README.md
git commit -m "docs(readme): tu mensaje"
```

**Actualizar tu rama con cambios remotos**
```bash
git fetch origin
git pull --rebase origin main
```

**Subir rama y abrir PR**
```bash
git push -u origin docs/<alias>/readme
# Luego abrir PR en GitHub
```

**Resolver conflictos (caso típico en README)**
```bash
# Edita manualmente los conflictos en README.md
git add README.md
git rebase --continue    # o git commit si estabas en merge
```

**Volver a un estado limpio (si te atoras)**
```bash
git stash         # guarda cambios locales sin *commit*
git stash pop     # reaplica más tarde
```

---

## Ejercicio: simular conflicto en el README

1. A y B crean cada uno su rama `docs/<alias>/readme`.
2. Ambos editan la **misma sección** (por ejemplo, “Flujo de trabajo”).
3. A hace PR y se fusiona primero.
4. B intenta *push* y Git le pedirá **actualizar**:
   ```bash
   git fetch origin
   git pull --rebase origin main
   # resolver conflictos en README.md
   git add README.md
   git rebase --continue
   git push
   ```
5. B abre PR luego de resolver el conflicto.
