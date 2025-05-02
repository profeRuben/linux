
# Comandos básicos en Linux – Guía para estudiantes Duoc UC

## 01. Comandos básicos en Linux

### Sudo y su
- `sudo`: Ejecuta comandos como superusuario.  
  ```bash
  sudo yum update
  ```
- `su`: Cambia a otro usuario (por defecto, root).  
  ```bash
  su -
  ```

### Comandos básicos

| Comando | Descripción breve | Ejemplo |
|--------|--------------------|---------|
| `ls` | Lista archivos y directorios | `ls /home/ec2-user` |
| `cp` | Copia archivos o directorios | `cp archivo.txt copia.txt` |
| `pwd` | Muestra el directorio actual | `pwd` |
| `cd` | Cambia de directorio | `cd /var/log` |
| `sort` | Ordena archivos de texto | `sort lista.txt` |
| `mkdir` | Crea directorios | `mkdir nueva_carpeta` |
| `touch` | Crea o actualiza archivos | `touch nuevo.txt` |
| `rm` | Borra archivos o carpetas | `rm archivo.txt` |
| `rmdir` | Borra directorios vacíos | `rmdir vacio/` |
| `mv` | Mueve o renombra archivos | `mv notas.txt respaldo.txt` |
| `ln` | Crea enlaces entre archivos | `ln -s origen.txt enlace.txt` |
| `more` | Muestra contenido página a página | `more log.txt` |
| `less` | Similar a `more`, más flexible | `less log.txt` |
| `cat` | Muestra contenido continuo | `cat archivo.txt` |
| `head` | Muestra primeras líneas | `head -n 10 archivo.txt` |
| `tail` | Muestra últimas líneas | `tail -n 10 archivo.txt` |
| `find` | Busca archivos | `find / -name "resumen.txt"` |
| `grep` | Busca patrones dentro de archivos | `grep "duoc" archivo.txt` |
| `wc` | Cuenta líneas, palabras y caracteres | `wc -l archivo.txt` |

### Gestor de Paquetes – YUM

| Comando | Descripción breve | Ejemplo |
|--------|--------------------|---------|
| `yum install paquete` | Instala un paquete con confirmación | `sudo yum install httpd` |
| `yum -y install paquete` | Instala sin pedir confirmación | `sudo yum -y install git` |
| `yum -y install paquete1 paquete2` | Instala múltiples paquetes | `sudo yum -y install git wget` |
| `yum -y update` | Actualiza todo el sistema | `sudo yum -y update` |
| `yum -y update httpd` | Actualiza solo un paquete | `sudo yum -y update httpd` |
| `yum check-update` | Muestra paquetes con actualizaciones | `sudo yum check-update` |
| `yum info paquete` | Muestra descripción de un paquete | `sudo yum info nginx` |
| `yum info recent` | Muestra info de paquetes recientes | `sudo yum info recent` |
| `yum list` | Lista paquetes instalables o instalados | `sudo yum list` |
| `yum list | grep mysql` | Filtra paquetes relacionados con mysql | `sudo yum list | grep mysql` |
| `yum list installed` | Lista paquetes instalados | `sudo yum list installed` |
| `yum list available` | Lista paquetes disponibles para instalar | `sudo yum list available` |
| `yum list updates` | Lista paquetes que tienen actualizaciones | `sudo yum list updates` |
| `yum remove paquete` | Elimina un paquete instalado | `sudo yum remove httpd` |

### Man

- `man`: Muestra el manual de un comando.  
  ```bash
  man ls
  ```

### Editor de texto – Nano

- `nano`: Abre y edita un archivo desde la terminal.  
  ```bash
  nano archivo.txt
  ```

## 02. Administración de usuarios

### Comandos de usuario

| Comando | Descripción breve | Ejemplo |
|--------|--------------------|---------|
| `useradd` | Crea un nuevo usuario | `sudo useradd estudiante` |
| `passwd` | Asigna contraseña a un usuario | `sudo passwd estudiante` |
| `userdel` | Elimina un usuario | `sudo userdel estudiante` |

### Archivos del sistema

- `/etc/passwd`: Registro de usuarios.  
- `/etc/shadow`: Contraseñas cifradas.

### Grupos

| Comando | Descripción breve | Ejemplo |
|--------|--------------------|---------|
| `groupadd` | Crea un nuevo grupo | `sudo groupadd ayudantes` |
| `groupdel` | Elimina un grupo | `sudo groupdel ayudantes` |
| `usermod -g` | Cambia grupo principal | `sudo usermod -g alumnos estudiante` |
| `usermod -G` | Añade a grupos secundarios | `sudo usermod -G ayudantes,ti estudiante` |

## 03. Administración de permisos

### Permisos

- Tres niveles: propietario, grupo, otros.  
- Representación: `r` (lectura), `w` (escritura), `x` (ejecución).  

### Cambiar permisos

- `chmod`: Cambia permisos.  
  ```bash
  chmod 755 carpeta/
  ```

- `chown`: Cambia propietario.  
  ```bash
  sudo chown ec2-user archivo.txt
  ```

- `chgrp`: Cambia grupo.  
  ```bash
  sudo chgrp alumnos archivo.txt
  ```
