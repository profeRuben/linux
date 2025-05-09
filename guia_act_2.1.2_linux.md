
# Guía de Comandos Básicos en Linux

## 01. Comandos básicos en Linux

### Sudo y su
**sudo**
: Ejecuta comandos como superusuario
```bash
sudo yum update
```

**su**
: Cambia a otro usuario (por defecto, root)
```bash
su -
```


### Comandos básicos
**ls**
: Lista archivos y directorios
```bash
ls /home/ec2-user
```

**cp**
: Copia archivos o directorios
```bash
cp archivo.txt copia.txt
```

**pwd**
: Muestra el directorio actual
```bash
pwd
```

**cd**
: Cambia de directorio
```bash
cd /var/log
```

**sort**
: Ordena archivos de texto
```bash
sort lista.txt
```

**mkdir**
: Crea directorios
```bash
mkdir nueva_carpeta
```

**touch**
: Crea o actualiza archivos
```bash
touch nuevo.txt
```

**rm**
: Borra archivos o carpetas
```bash
rm archivo.txt
```

**rmdir**
: Borra directorios vacíos
```bash
rmdir vacio/
```

**mv**
: Mueve o renombra archivos
```bash
mv notas.txt respaldo.txt
```

**ln**
: Crea enlaces entre archivos
```bash
ln -s origen.txt enlace.txt
```

**more**
: Muestra contenido página a página
```bash
more log.txt
```

**less**
: Similar a `more`, más flexible
```bash
less log.txt
```

**cat**
: Muestra contenido continuo
```bash
cat archivo.txt
```

**head**
: Muestra primeras líneas
```bash
head -n 10 archivo.txt
```

**tail**
: Muestra últimas líneas
```bash
tail -n 10 archivo.txt
```

**find**
: Busca archivos
```bash
find / -name "resumen.txt"
```

**grep**
: Busca patrones dentro de archivos
```bash
grep "duoc" archivo.txt
```

**wc**
: Cuenta líneas, palabras y caracteres
```bash
wc -l archivo.txt
```


### Gestor de paquetes - YUM
**yum install paquete**
: Instala un paquete con confirmación
```bash
sudo yum install httpd
```

**yum -y install paquete**
: Instala sin pedir confirmación
```bash
sudo yum -y install git
```

**yum -y install paquete1 paquete2**
: Instala múltiples paquetes
```bash
sudo yum -y install git wget
```

**yum -y update**
: Actualiza todo el sistema
```bash
sudo yum -y update
```

**yum -y update httpd**
: Actualiza solo un paquete
```bash
sudo yum -y update httpd
```

**yum check-update**
: Muestra paquetes con actualizaciones
```bash
sudo yum check-update
```

**yum info paquete**
: Muestra descripción de un paquete
```bash
sudo yum info nginx
```

**yum info recent**
: Muestra info de paquetes recientes
```bash
sudo yum info recent
```

**yum list**
: Lista paquetes instalables o instalados
```bash
sudo yum list
```

**yum list | grep mysql**
: Filtra paquetes relacionados con mysql
```bash
sudo yum list | grep mysql
```

**yum list installed**
: Lista paquetes instalados
```bash
sudo yum list installed
```

**yum list available**
: Lista paquetes disponibles para instalar
```bash
sudo yum list available
```

**yum list updates**
: Lista paquetes que tienen actualizaciones
```bash
sudo yum list updates
```

**yum remove paquete**
: Elimina un paquete instalado
```bash
sudo yum remove httpd
```


### Man
**man**
: Muestra el manual de un comando
```bash
man ls
```


### Editor de texto - Nano
**nano**
: Abre y edita un archivo desde la terminal
```bash
nano archivo.txt
```


---

## 02. Administración de usuarios

### Comandos de usuario
**useradd**
: Crea un nuevo usuario
```bash
sudo useradd estudiante
```

**passwd**
: Asigna contraseña a un usuario
```bash
sudo passwd estudiante
```

**userdel**
: Elimina un usuario
```bash
sudo userdel estudiante
```



### Archivos del sistema

- `/etc/passwd`: Registro de usuarios.  
- `/etc/shadow`: Contraseñas cifradas.

#### Visualización

Para revisar el contenido de estos archivos, puedes usar:

```bash
cat /etc/passwd
sudo cat /etc/shadow
```

También puedes editarlos con:

```bash
sudo nano /etc/passwd
sudo nano /etc/shadow
```

> ⚠️ El archivo `/etc/shadow` requiere permisos de superusuario.

### Grupos
**groupadd**
: Crea un nuevo grupo
```bash
sudo groupadd ayudantes
```

**groupdel**
: Elimina un grupo
```bash
sudo groupdel ayudantes
```

**usermod -g**
: Cambia grupo principal
```bash
sudo usermod -g alumnos estudiante
```

**usermod -G**
: Añade a grupos secundarios
```bash
sudo usermod -G ayudantes,ti estudiante
```


---

## 03. Administración de permisos

### Permisos
- Tres niveles: propietario, grupo, otros.  
- Representación: `r` (lectura), `w` (escritura), `x` (ejecución).  

### Cambiar permisos
**chmod**
: Cambia permisos
```bash
chmod 755 carpeta/
```

**chown**
: Cambia propietario
```bash
sudo chown ec2-user archivo.txt
```

**chgrp**
: Cambia grupo
```bash
sudo chgrp alumnos archivo.txt
```

