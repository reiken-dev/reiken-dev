# Manual rapido: uso diario de GitHub, SSH e identidades

## Estructura de carpetas

Base de trabajo:

```bash
~/repositorios-entrenamiento/
```

Cuentas separadas por carpeta:

```bash
~/repositorios-entrenamiento/reiken-dev/
~/repositorios-entrenamiento/vision-st/
```

## Que significa cada carpeta

### reiken-dev
Usa automaticamente:

- GitHub principal: `reiken-dev`
- Email Git: `jo.edu.car@outlook.com`
- SSH alias recomendado: `github-main`

### vision-st
Usa automaticamente:

- GitHub secundaria: `vision-st`
- Email Git: `jorgecarmona1986@icloud.com`
- SSH alias recomendado: `github-second`

## Regla importante

La identidad Git cambia automaticamente segun la carpeta donde viva el repo.

- Si el repo esta dentro de `reiken-dev/`, usa la cuenta principal.
- Si el repo esta dentro de `vision-st/`, usa la cuenta secundaria.

## Donde clonar cada proyecto

### Proyecto de la cuenta principal

```bash
cd ~/repositorios-entrenamiento/reiken-dev
git clone git@github-main:reiken-dev/NOMBRE-REPO.git
```

### Proyecto de la cuenta secundaria

```bash
cd ~/repositorios-entrenamiento/vision-st
git clone git@github-second:vision-st/NOMBRE-REPO.git
```

## Como crear un repo local nuevo

### Para reiken-dev

```bash
cd ~/repositorios-entrenamiento/reiken-dev
mkdir mi-repo
cd mi-repo
git init
git branch -M main
```

### Para vision-st

```bash
cd ~/repositorios-entrenamiento/vision-st
mkdir mi-repo
cd mi-repo
git init
git branch -M main
```

## Como verificar que cuenta esta usando un repo

Dentro del repo:

```bash
git config user.name
git config user.email
git remote -v
```

## Resultado esperado

### En reiken-dev

```bash
Jorge Carmona
jo.edu.car@outlook.com
```

### En vision-st

```bash
Jorge Carmona
jorgecarmona1986@icloud.com
```

## Como probar SSH

### Cuenta principal

```bash
ssh -T git@github-main
```

Debe responder algo como:

```bash
Hi reiken-dev! You've successfully authenticated, but GitHub does not provide shell access.
```

### Cuenta secundaria

```bash
ssh -T git@github-second
```

Debe responder algo como:

```bash
Hi vision-st! You've successfully authenticated, but GitHub does not provide shell access.
```

## Remotos correctos

### Principal

```bash
git remote add origin git@github-main:reiken-dev/NOMBRE-REPO.git
```

### Secundaria

```bash
git remote add origin git@github-second:vision-st/NOMBRE-REPO.git
```

## Repo especial de perfil GitHub

Tu repo de perfil principal esta en:

```bash
~/repositorios-entrenamiento/reiken-dev/intro-github
```

Remote:

```bash
git@github-main:reiken-dev/reiken-dev.git
```

GitHub profile:

```bash
https://github.com/reiken-dev
```

## Acciones de uso diario

### Ver estado

```bash
git status
```

### Agregar cambios

```bash
git add .
```

### Hacer commit

```bash
git commit -m "mensaje claro"
```

### Subir cambios

```bash
git push
```

### Bajar cambios

```bash
git pull
```

## Si algo sale raro

### Verifica primero

```bash
pwd
git config user.email
git remote -v
```

Porque casi siempre el problema sera uno de estos:

- estas parado en la carpeta equivocada
- el repo usa el remoto equivocado
- el repo no esta inicializado con Git
- estas intentando empujar con la cuenta incorrecta

## Regla de oro

Antes de clonar, crear o empujar un repo, revisa en que carpeta estas.

```bash
pwd
```

Si la carpeta esta bien, casi todo lo demas cae por su propio peso.
