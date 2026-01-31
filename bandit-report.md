# Bandit Level 0
**Objetivo:**
Conectarme al juego usando SSH.  
**Comandos utilizados:**
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
## Explicación:
Se utilizó el comando "ssh" con el usuario "bandit0", contraseña "bandit0", servidor "bandit.labs.overthewire.org" y con el puerto 2220 para conectarme con el servidor de OverTheWire.

# Bandit Level 1
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

# Bandit Level 2
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

# Bandit Level 3
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

# Bandit Level 4
**Objetivo:**
Encontrar la contraseña del siguiente nivel en el archivo oculto.  
**Comandos utilizados:**
```bash
ls
cd inhere
ls -a
cat ...Hiding-From-You
```
## Explicación:
Se navegó a la carpeta "inhere", y se usó el comando "ls -a" para mostrar los archivos ocultos dentro del directorio.

## Contraseña obtenida:
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

# Bandit Level 5
**Objetivo:**
Encontrar la contraseña del siguiente nivel en uno de los 10 archivos.  
**Comandos utilizados:**
```bash
ls
cd inhere
cat < -file00
cat < -file01
cat < -file02
cat < -file03
cat < -file04
cat < -file05
cat < -file06
cat < -file07
```
## Explicación:
Se navegó a la carpeta "inhere", y se usó el comando "cat" con el símbolo "<", ya que los nombres de los archivos empiezan con un guión. Se revisó cada archivo en orden hasta encontrar la contraseña.

## Contraseña obtenida:
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

# Bandit Level 6
**Objetivo:**
Encontrar la contraseña del siguiente nivel en un archivo oculto entre varios directorios.  
**Comandos utilizados:**
```bash
ls
cd inhere
file */* | grep "ASCII"
file */* | grep "ASCII" | grep -v "long"
file */* | grep "ASCII" | grep -v "long" | du -ba
du -ba | grep 1033
```
## Explicación:
Se navegó a la carpeta "inhere", la cual tiene 20 carpetas, cada una con varios archivos. Se usó el comando "file */*" para mostrar los tipos de todos los archivos en todos los directorios. Se utilizó un pipe, denotado por el símbolo "|", para ejecutar un segundo comando sobre el output del primer comando. El comando "grep "ASCII"" se usó para mostrar únicamente los archivos que tienen "ASCII text" como tipo de archivo. Se utilizó otro pipe con el argumento "-v "long"" para mostrar únicamente los archivos que tienen "ASCII text" y que no tienen "with very long lines" como tipo de archivo. Luego, se agregó el comando "du -ba" para mostrar el tamaño de los archivos, pero ninguno tenía exactamente 1033 bytes. Finalmente, se utilizó el comando "du -ba | grep 1033" para hallar el tamaño de todos los archivos de todos los directorios, pero mostrar únicamente aquellos que tengan 1033 bytes, el cual solo fue 1 archivo.

## Contraseña obtenida:
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

# Bandit Level 7
**Objetivo:**
Encontrar la contraseña del siguiente nivel en un archivo dentro de un servidor.  
**Comandos utilizados:**
```bash
find / -user bandit7
find / -user bandit7 -group bandit6
find / -user bandit7 -group bandit6 -size 33c
cat /var/lib/dpkg/info/bandit7.password
```
## Explicación:
Se usó el comando "find /" para buscar archivos dentro de todo el servidor. Se usó la opción "-user bandit7" para mostrar únicamente los archivos que pertenecen al usuario "bandit7". Luego, se agregó la opción "-group bandit6" para mostrar la lista de estos archivos que también pertenezcan al grupo "bandit6". Luego, se agregó la opción "-size 33c" para mostrar la lista de estos archivos que también tengan un tamaño de 33 bytes. Finalmente, se encontró en la lista el único archivo que no muestra el error "Permission denied" o "No such file or directory".

## Contraseña obtenida:
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj