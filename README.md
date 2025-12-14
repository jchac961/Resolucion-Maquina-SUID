# Resolucion-Maquina-SUID

nicialmente una vez ya teniamos la maquina descargada y desplegada hicimos un escaneo basico para verificar los puertos que esta maquina tenia abiertos
I<img width="1920" height="1140" alt="Captura de pantalla 2025-12-13 212011" src="https://github.com/user-attachments/assets/89c53c0c-206f-4e5c-af70-d514814dcfba" />

Luego de hacer el escaneo de puertos procedimos a ingresar mediante el xplorador con el numero ip de la maquina ya que la misma contenia el puerto 8080 abierto el cual esta corriendo un servicio de HTTP, y dentro del codigo pudimos observar que oculto habian credenciales
<img width="1920" height="1140" alt="Captura de pantalla 2025-12-13 211950" src="https://github.com/user-attachments/assets/b6ce5cc8-ea86-47f4-8546-1b1ce36a676d" />

Dentro del escaneo que pudimos hacer con el nmap tambien pudimos encontrar el puerto 22 el cual se aloja un servicio ssh y que aprovechamos para intentar ingresar con las credenciales obtenidas 
<img width="1920" height="1140" alt="Captura de pantalla 2025-12-13 212151" src="https://github.com/user-attachments/assets/2cf809fe-4c4b-46bd-b115-87120b38f491" />

Ya dentro de la maquina vulnerable listamos todos los archivos, incluyendo los ocultos y procedimos a buscar binarios mal configurados utilizando el comando find / -perm -4000 -type f 2>/dev/null
<img width="1920" height="1140" alt="Captura de pantalla 2025-12-13 212228" src="https://github.com/user-attachments/assets/735761be-b876-48a6-b98f-56d752ec9d92" />

Luego buscamos en la pagina de gtfobins.github.io el archivo find y nos arrojo un comando que utilizamos luego de poner la dirección correcta 
<img width="1920" height="1140" alt="Captura de pantalla 2025-12-14 011424" src="https://github.com/user-attachments/assets/aa780cff-99d1-4b91-8874-79b1e365cfbf" />

una vez desplegado este comando como podemos ver utilizamos el comando whoami para verificar que usuario eramos en ese momento y ya habiamos obtenido permisos como root.
<img width="1920" height="1140" alt="Captura de pantalla 2025-12-13 212420" src="https://github.com/user-attachments/assets/801331fe-d884-46eb-9956-03a576451fd3" />

Luego nos movimos lateralmente a la carpeta root para buscar o listar los archivos contenidos en la misma, y encontramos un archivo llamado flag.txt el cual abrimos con el comando cat flag.txt y obtuvimos la flag
<img width="1920" height="1140" alt="Captura de pantalla 2025-12-13 212643" src="https://github.com/user-attachments/assets/10a6ae29-5022-45a9-966d-05f607e1b088" />

Esta flag la utilizamos para ingresar en la pagina de nuestra maquina docker y asi culminamos nuestra pruba de penetración en esta maquina
<img width="1920" height="1140" alt="Captura de pantalla 2025-12-13 212746" src="https://github.com/user-attachments/assets/3bef8229-f86c-4f18-8710-145d89178199" />

