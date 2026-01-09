# 📡 Lab 3: Escaneo de Puertos y Detección de Servicios

**Fecha:** 09 de Enero, 2026
**Herramienta:** `Nmap` (Network Mapper)
**Objetivo:** Scanme.nmap.org (Objetivo autorizado de entrenamiento)

## 📝 Descripción
Realicé un escaneo de puertos TCP contra un objetivo autorizado para identificar la superficie de ataque y los servicios expuestos. Se detectaron problemas de latencia en la red (RTTVAR), lo que extendió el tiempo de escaneo a 10 minutos.

## 🔍 Resultados del Escaneo
Comando ejecutado: `nmap scanme.nmap.org`

| Puerto | Estado | Servicio | Análisis de Seguridad |
| :--- | :--- | :--- | :--- |
| **22** | Open | SSH | Acceso administrativo remoto. Vector común para ataques de Fuerza Bruta. |
| **80** | Open | HTTP | Servidor Web público. Vector potencial para ataques OWASP (SQLi, XSS). |
| **9929** | Open | nping | Servicio de eco para diagnóstico de red. |
| **31337** | Open | Elite | **ALERTA:** Puerto asociado históricamente a Backdoors y cultura hacker (Leet). En un entorno real, indicaría compromiso del servidor (Back Orifice/Trojan). |

## 🧠 Conclusión
El escaneo reveló que el objetivo tiene servicios web y de administración expuestos. Destaca la presencia del puerto 31337, que simula una infección por troyano o backdoor, validando los conceptos estudiados en la teoría de "Troyanos y Backdoors".
