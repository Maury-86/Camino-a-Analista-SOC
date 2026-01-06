# 🌐 Lab 2: Análisis de Ruta y Trazabilidad de Red

**Fecha:** 06 de Enero, 2026
**Herramientas:** `ping`, `tracepath`, `ip addr`

## 🎯 Objetivo
Visualizar el camino lógico que recorren los paquetes de datos desde mi estación de trabajo local (WSL) hasta un servidor externo (Google), identificando los saltos (hops) y dispositivos intermedios.

## 🔍 Análisis de Resultados

### 1. Identificación Local
* **Mi IP Privada (WSL):** `172.22.xxx.xx`
* **Mi Puerta de Enlace (Router):** `192.168.1.1`

### 2. Prueba de Latencia (Ping)
Se observó un **TTL de 92**. Esto indica que el paquete original probablemente salió con un TTL de 128 (Windows) o similar y atravesó múltiples routers que decrementaron el contador antes de llegar a mí.
* **Estado:** 0% Packet Loss (Conexión estable).

### 3. Trazado de Ruta (Tracepath)
El comando `tracepath google.com` reveló la siguiente topología:
* **Saltos 1-2:** Red Local (LAN).
* **Saltos 5-16:** **"No Reply"**. Identifiqué que esto se debe a configuraciones de seguridad (Firewalls/Routers) en la red del ISP que bloquean las respuestas ICMP para ocultar la infraestructura, aunque permiten el paso del tráfico.
* **Salto 22:** Llegada a la red de Google (`74.125.x.x`).

## 🧠 Conclusión Técnica
Comprendí que la herramienta `tracepath` permite diagnosticar dónde se detiene el tráfico. La presencia de "no reply" no siempre indica falla, sino a menudo medidas de "seguridad por oscuridad" en los nodos intermedios.
