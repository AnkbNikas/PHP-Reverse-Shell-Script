# PHP-Reverse-Shell-Script

Necesitas un servidor web donde puedas alojar el archivo PHP. Esto puede ser un servidor local como XAMPP, WAMP, o un servidor remoto.

Necesitarás acceso a la terminal en tu máquina atacante para establecer el listener.

Asegúrate de tener PHP instalado en tu servidor web.

Abre tu editor de texto favorito y copia el siguiente código. Reemplaza attacker_ip = 'ATTACKER_IP' con la dirección IP de tu máquina atacante y reemplaza attacker_port = '4444' con el puerto deseado, guarda el archivo como reverse_shell.php.

Subir el archivo al servidor web:

Sube reverse_shell.php al directorio público de tu servidor web.

Establecer un listener en tu máquina atacante:

Abre una terminal en tu máquina atacante y ejecuta el siguiente comando para iniciar un listener en el puerto 4444:

nc -lvnp 4444

Acceder al archivo PHP desde el navegador:

Abre un navegador web y accede a la URL donde subiste el archivo reverse_shell.php. Por ejemplo, si lo subiste a http://example.com/reverse_shell.php, accede a esa URL.

Firewall y red: Asegúrate de que las configuraciones de firewall y red permitan las conexiones entrantes y salientes en los puertos utilizados.
