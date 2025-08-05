# -Laboratorios-del-Modulo-IX--
Practica 4: Comandos Ad-Hoc (1Pts)
1. sudo dnf install -y epel-release
   - Instala el repositorio EPEL (Extra Packages for Enterprise Linux) necesario para instalar Ansible y otros paquetes adicionales.

2. sudo dnf install -y ansible
   - Instala Ansible junto con todas sus dependencias.

3. ansible --version
   - Muestra la versión instalada de Ansible y la configuración básica.

4. ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_rsa_ansible
   - Genera un par de claves RSA de 4096 bits para autenticación SSH sin contraseña, almacenadas en el archivo especificado.

5. ssh-copy-id -i ~/.ssh/id_rsa_ansible.pub ansible@<ip_maquina_remota>
   - Copia la clave pública generada al usuario remoto para permitir conexión SSH sin contraseña.

6. sudo nano /etc/ansible/hosts
   - Edita el archivo de inventario de Ansible donde se definen los grupos y hosts a administrar.

7. ansible linux -m ping
   - Ejecuta el módulo ping en los hosts del grupo 'linux' para probar conectividad SSH.

8. ansible win -m win_ping
   - Ejecuta el módulo win_ping en los hosts del grupo 'win' para probar conectividad WinRM.

9. pip install pywinrm
   - Instala la librería Python para que Ansible pueda comunicarse con máquinas Windows usando WinRM.

10. winrm quickconfig -q (en Windows)
    - Configura y habilita rápidamente el servicio WinRM para administración remota.

11. Set-Item -Path WSMan:\localhost\Service\Auth\Basic -Value $true (en PowerShell)
    - Habilita autenticación básica en WinRM.

12. Set-Item -Path WSMan:\localhost\Service\AllowUnencrypted -Value $true (en PowerShell)
    - Permite comunicación sin cifrado en WinRM (para pruebas o redes seguras).

13. net localgroup Administradores ansible /add (en Windows)
    - Agrega el usuario 'ansible' al grupo de administradores locales para permisos elevados.

14. ansible win -m win_copy -a "src='<ruta_local>' dest='<ruta_remota>'"
    - Copia un archivo desde el controlador Ansible al host Windows remoto.

15. ansible win -m win_shell -a "Copy-Item -Path '<ruta_origen>' -Destination '<ruta_destino>'"
    - Ejecuta un comando PowerShell para copiar un archivo dentro del host Windows remoto.

16. ansible linux -m reboot
    - Envía el comando para reiniciar un host Linux remoto.

17. ansible win -m win_reboot
    - Envía el comando para reiniciar un host Windows remoto.
