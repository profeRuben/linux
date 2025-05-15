# 🧩 Actividad práctica: Usuarios, permisos y tareas programadas

Trabaja sobre tu instancia EC2 usando **PuTTY**. Registra con capturas o transcripciones lo que haces.  
Al finalizar, entrega un **PDF simple** que incluya tus resultados y explicaciones breves.  
No se requiere portada ni formato especial.

---

## Parte 1: Acceso y preparación

- Conéctate a tu instancia EC2.
- Cambia la contraseña del usuario `root`.
- Crea un usuario llamado `admin_lab` con la contraseña `Duoc2025`.
- Verifica que el usuario fue creado correctamente.

**💡 Tip:** Para verificar, puedes revisar el archivo `/etc/passwd`.

---

## Parte 2: Directorios y permisos

- En `/home`, crea una carpeta llamada `proyecto_final`.
- Dentro, crea dos subcarpetas: `sistema` y `respaldo`.
- En la raíz (`/`), crea dos archivos:
  - `registro_sistema.txt`: escribe una línea con la descripción de tu instancia.
  - `registro_backup.txt`: escribe una línea sobre la importancia del respaldo.
- Aplica estos permisos:
  - `registro_sistema.txt`: propietario con lectura, escritura y ejecución; grupo con lectura; otros con ejecución.
  - `registro_backup.txt`: propietario con lectura y escritura; grupo sin permisos; otros con ejecución.
- Cambia el propietario de la carpeta `proyecto_final` y sus subcarpetas al usuario `admin_lab`.

**💡 Tip:** Revisa los permisos con `ls -l`. Usa `chmod` para modificar y `chown` para cambiar el dueño.

---

## Parte 3: Introducción a `cron`


**Antes de comenzar:** Verifica si `cron` está instalado. En algunas instancias de Amazon Linux, es necesario instalarlo manualmente.

**1. Verifica si `cron` está disponible:**
```bash
crontab -l
```
Si ves un error como `command not found`, sigue con el paso 2.

**2. Instala y activa `cron` (si es necesario):**
```bash
sudo yum install cronie -y
sudo systemctl start crond
sudo systemctl enable crond
```

**3. Verifica que el servicio esté corriendo:**
```bash
systemctl status crond
```


### ¿Qué es?

`cron` permite programar tareas automáticas en Linux. Se usa para que comandos se ejecuten solos en momentos definidos.

### ¿Cómo se escribe una tarea?

Cada tarea se define en una línea con esta estructura:

```
minuto hora día_mes mes día_semana comando
```

---

### 🧩 Ejemplos para entender `cron`

**Ejemplo 1: Ejecutar un mensaje cada minuto**

```
* * * * * echo "Ejecutado a $(date)" >> /home/ec2-user/cronlog.txt
```

**Ejemplo 2: Copiar un archivo cada lunes a las 14:30**

```
30 14 * * 1 cp /archivo.txt /ruta/destino/
```

**Ejemplo 3: Eliminar un archivo todos los días a las 23:59**

```
59 23 * * * rm /ruta/archivo.txt
```

**💡 Tip:** Usa `crontab -e` para editar y `crontab -l` para revisar.

---

## Parte 4: Tareas programadas

Crea tus propias tareas automáticas. Ajusta la hora para que puedas probarlas durante esta clase.

- **Tarea 1:** Copiar el archivo `registro_backup.txt` al directorio `/home/proyecto_final/respaldo`.
- **Tarea 2:** Mover el archivo `registro_sistema.txt` al directorio `/home/proyecto_final/sistema`.
- **Tarea 3:** Eliminar los archivos dentro del directorio `/home/proyecto_final/respaldo`.

**💡 Tip:** Ajusta los minutos según la hora actual para que puedas comprobarlas antes de terminar.

