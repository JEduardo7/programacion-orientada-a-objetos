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