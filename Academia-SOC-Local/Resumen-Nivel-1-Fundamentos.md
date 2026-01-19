# 📝 Resumen Ejecutivo: Fundamentos de Analista SOC (Nivel 1)

**Fecha de Corte:** 19 de enero de 2026
**Estado:** Consolidado ✅
**Objetivo:** Recopilación de comandos, conceptos y estructuras clave aprendidas en los primeros módulos.

---

## 🚀 Módulo 0: Mentalidad y Entorno

### Conceptos Clave
* **Ciberseguridad:** No es solo tecnología, es protección de activos (información).
* **Blue Team (Defensa):** Nuestro rol. Monitorear, detectar y responder. (El "Arquero").
* **Red Team (Ataque):** Simulan amenazas para probar las defensas.
* **SOC (Security Operations Center):** El cuartel general donde se centraliza la vigilancia.

### Entorno de Trabajo
* **WSL (Windows Subsystem for Linux):** Usamos una arquitectura híbrida. Windows como base, Ubuntu (Linux) como herramienta de operación.
* **GitHub:** Nuestro portafolio y bitácora de evidencias.

---

## 🐧 Módulo 1: Dominio de Linux (La Terminal)

El sistema operativo de la seguridad. "En Linux, todo es un archivo".

### Comandos de Supervivencia
| Comando | Acción | Ejemplo |
| :--- | :--- | :--- |
| `pwd` | ¿Dónde estoy? (Ruta actual) | `/home/mons` |
| `ls -la` | Listar todo (incluso ocultos) | Ver archivos `.git` o `.bashrc` |
| `cd` | Cambiar de directorio | `cd Academia-SOC-Local` |
| `mkdir` | Crear carpeta | `mkdir Laboratorios` |
| `touch` | Crear archivo vacío | `touch notas.txt` |
| `cat` | Leer contenido de archivo | `cat /etc/passwd` |
| `rm` | Borrar (¡Cuidado!) | `rm archivo.txt` |
| `man` | Manual de ayuda | `man ls` |

### Permisos y Superusuario
* **Root:** El usuario "Dios". Tiene control total.
* **Sudo:** "SuperUser DO". Pide permisos prestados temporalmente.
    * *Ejemplo:* `sudo apt update` (Actualizar el sistema).
* **Permisos (Chmod):**
    * `r` (Read/Leer), `w` (Write/Escribir), `x` (Execute/Ejecutar).
    * *Peligro:* `chmod 777` (Permisos totales a todo el mundo).
    * *Seguridad:* `chmod +x script.sh` (Hacer un script ejecutable).

---

## 🌐 Módulo 2: Fundamentos de Redes (Networking)

Cómo viajan los datos. Si no entiendes la carretera, no puedes atrapar al ladrón.

### Conceptos de Identidad
* **IP Privada (Local):** Tu dirección dentro de casa/oficina. No accesible desde fuera. (Rango típico: `192.168.x.x` o `172.x.x.x` en WSL).
* **IP Pública (WAN):** Tu cara hacia Internet. Asignada por el ISP.
* **Loopback:** `127.0.0.1` (Localhost). La computadora hablándose a sí misma.

### Herramientas de Diagnóstico
| Comando | Función | Interpretación SOC |
| :--- | :--- | :--- |
| `ping 8.8.8.8` | ¿Estás vivo? | Mide latencia y disponibilidad. Si falla, el host cayó o hay firewall. |
| `traceroute` | ¿Por dónde vas? | Muestra cada salto (router) hasta el destino. Útil para ver cuellos de botella. |
| `hostname -I` | ¿Quién soy? | Muestra mi IP asignada actual. |
| `curl ifconfig.me` | ¿Cómo me ven fuera? | Muestra mi IP Pública real. |

### 📦 Teoría Vital: El Modelo OSI y Encapsulamiento
Los datos viajan dentro de "muñecas rusas" (Encapsulamiento).

1.  **Capa 7 (Datos):** La carta (Lo que quiere el usuario).
2.  **Capa 4 (Segmento):** El sobre acolchado (TCP/UDP - Puertos).
3.  **Capa 3 (Paquete):** La caja de envío (IP Origen/Destino).
4.  **Capa 2 (Trama):** El camión de reparto (MAC Address - Física).
5.  **Capa 1 (Bits):** La carretera (Cables/Luz).

### 🕵️ Herramientas de Sniffing (Instaladas)
* **Tcpdump:** Captura de paquetes en línea de comandos. (El francotirador).
* **Wireshark/Tshark:** Análisis profundo de paquetes. (El microscopio).

---

## 📚 Biblioteca Técnica (Referencia)
Se han incorporado manuales clave sobre:
1.  **Protocolos:** TCP/UDP, DNS, DHCP, SSL/TLS.
2.  **Servicios:** HTTP, FTP vs SFTP, Email (SMTP/IMAP).
3.  **Programación:** Bases de Bash, Python, Ruby y SQL.
