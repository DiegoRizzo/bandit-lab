## Bandit Level 0
**Objetivo:**
Conectarme al juego usando SSH.  
**Comandos utilizados:**
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
## Explicación:
Se utilizó el comando "ssh" con el usuario "bandit0", contraseña "bandit0", servidor "bandit.labs.overthewire.org" y con el puerto 2220 para conectarme con el servidor de OverTheWire.

## Bandit Level 1
**Objetivo:**
Encontrar la contraseña del siguiente nivel en el archivo readme.  
**Comandos utilizados:**
```bash
ls
cat readme
```
## Explicación:
Se listaron los archivos y se utilizó el comando "cat" para leer el texto contenido en el archivo "readme".

## Contraseña obtenida:
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

## Bandit Level 2
**Objetivo:**
Encontrar la contraseña del siguiente nivel en el archivo -.  
**Comandos utilizados:**
```bash
ls
cat < -
```
## Explicación:
Se listaron los archivos y se utilizó el comando "cat" con el símbolo "<" que se usa para redireccionar el input, ya que el nombre del archivo empieza con un guión, y usar un guión como argumento refiere a STDIN/STDOUT, por lo que no se puede ejecutar "cat -".

## Contraseña obtenida:
263JGJPfgU6LtdEvgfWU1XP5yac29mFx

## Bandit Level 3
**Objetivo:**
Encontrar la contraseña del siguiente nivel en el archivo "--spaces in this filename--".  
**Comandos utilizados:**
```bash
ls
cat < "--spaces in this filename--"
```
## Explicación:
Igual al nivel anterior, se listaron los archivos y se utilizó el comando "cat" con el símbolo "<", pero se usaron también comillas dobles debido a que el nombre del archivo tiene espacios.

## Contraseña obtenida:
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx