# 🛡️ Academia SOC Local: Clase 01 - Ofensiva vs. Defensiva

**Fecha:** 16 de enero de 2026
**Módulo:** Introducción a la Ciberseguridad
**Ruta:** Pre-Security (Analista SOC)
**Estado:** Completado ✅

---

## 📝 Conceptos Teóricos

En esta primera sesión, exploramos la dualidad de la ciberseguridad:

1.  **Red Team (Seguridad Ofensiva):** Se centra en emular adversarios para encontrar vulnerabilidades. Su objetivo es abusar de las funciones del sistema para realizar acciones no autorizadas.
2.  **Blue Team (Seguridad Defensiva):** Se centra en la detección, respuesta y contención. Su objetivo es mantener el principio de menor privilegio y asegurar la continuidad del negocio.

---

## 🧪 Laboratorio Práctico: Ciclo de Vida del Malware y Contención

En este laboratorio simulé un conflicto entre un atacante que intenta ejecutar un script malicioso y un analista defensivo que lo neutraliza mediante la gestión de permisos en Linux.

### Ejecución en Terminal (Logs reales):

```bash
mons@DESKTOP-GRO0BNB:~$ mkdir Laboratorio-01
mons@DESKTOP-GRO0BNB:~$ cd Laboratorio-01
# El atacante crea el código malicioso
mons@DESKTOP-GRO0BNB:~/Laboratorio-01$ echo "Soy un código malicioso ejecutándose" > malware.sh

# Intento 1: Fallido por protección de permisos del sistema
mons@DESKTOP-GRO0BNB:~/Laboratorio-01$ ./malware.sh
-bash: ./malware.sh: Permission denied

# El atacante escala privilegios modificando los metadatos (chmod +x)
mons@DESKTOP-GRO0BNB:~/Laboratorio-01$ chmod +x malware.sh

# Intento 2: Exitoso (El sistema intenta ejecutar el código)
mons@DESKTOP-GRO0BNB:~/Laboratorio-01$ ./malware.sh
./malware.sh: line 1: Soy: command not found

# El Analista SOC aplica medidas de CONTENCIÓN (chmod 000)
mons@DESKTOP-GRO0BNB:~/Laboratorio-01$ chmod 000 malware.sh

# Verificación de la neutralización
mons@DESKTOP-GRO0BNB:~/Laboratorio-01$ cat malware.sh
cat: malware.sh: Permission denied
mons@DESKTOP-GRO0BNB:~/Laboratorio-01$ ./malware.sh
-bash: ./malware.sh: Permission denied

# Evidencia final de los permisos (ls -l)
mons@DESKTOP-GRO0BNB:~/Laboratorio-01$ ls -l malware.sh
---------- 1 mons mons 39 Jan 16 15:16 malware.sh
