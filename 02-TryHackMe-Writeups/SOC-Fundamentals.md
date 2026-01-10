# 🛡️ SOC Fundamentals - TryHackMe Write-up

**Fecha:** 06 de Enero, 2026  
**Categoría:** Blue Team / Operaciones de Seguridad  
**Plataforma:** TryHackMe

---

## 🎯 Objetivo del Módulo
Comprender la estructura, roles y procesos dentro de un Centro de Operaciones de Seguridad (SOC). Entender cómo fluye un incidente desde la detección hasta la respuesta.

---

## 🧠 Conceptos Clave Aprendidos

### 1. ¿Qué es un SOC?
Significa **Security Operations Center** (Centro de Operaciones de Seguridad). Es una instalación dedicada donde un equipo especializado trabaja **24/7** para monitorear continuamente la red, identificar actividades sospechosas y prevenir daños.

### 2. Los Niveles de Analistas (Tiers)
* **Analista Nivel 1 (Triage):** Monitoreo y filtrado de falsos positivos.
* **Analista Nivel 2 (Incident Responder):** Investigación profunda de incidentes.
* **Analista Nivel 3 (Threat Hunter):** Búsqueda proactiva de amenazas.

#### Roles de Soporte y Gestión
* **Security Engineer:** Se encarga de que las herramientas (SIEM, EDR) funcionen bien. Configuran e implementan el software.
* **Detection Engineer:** Escribe la "lógica" o reglas específicas para detectar amenazas nuevas.
* **SOC Manager:** Gestiona al equipo, los procesos y reporta directamente al CISO.

### 3. Herramientas Esenciales
* **SIEM:** (Security Information and Event Management).
* **EDR:** (Endpoint Detection and Response).

### 4. Capacidades Principales del SOC
* **Detección (Detection):** Encontrar vulnerabilidades, intrusiones o actividad no autorizada.
* **Respuesta (Response):** Análisis de causa raíz y minimización del impacto.

### 5. Los 3 Pilares del SOC
1. **People (Gente):** El equipo humano disponible 24/7.
2. **Process (Procesos):** Las reglas y procedimientos estandarizados.
3. **Technology (Tecnología):** Las herramientas de hardware y software.

### 6. El Proceso de Triage (Las 5 Ws)
Para investigar una alerta, el Analista Tier 1 debe responder:
* **What (Qué):** ¿Qué actividad activó la alerta? (Ej: Port Scanning).
* **When (Cuándo):** ¿Hora exacta de la actividad? (Ej: 17:24).
* **Where (Dónde):** ¿IP del host de destino? (Ej: 10.0.0.3).
* **Who (Quién):** ¿Nombre de host de origen? (Ej: NESSUS).
* **Why (Por qué):** ¿Motivo de la actividad? (Ej: Intended/Malicious).

### 7. Tecnología y Herramientas Principales
* **SIEM:** Recolecta logs de toda la empresa. Usa reglas de **correlación** para detectar anomalías.
* **EDR:** Se instala en cada dispositivo (**endpoint**). Permite responder y aislar amenazas en tiempo real.
* **Firewall:** Monitorea y filtra el tráfico de **entrada y salida** de la organización.

---

## 🔍 Ejercicio Práctico / Reto
* **Reto:** Identificar componentes del SOC y analizar logs en un SIEM.
* **Análisis:** Se identificó que el monitoreo proactivo reduce el "Dwell Time" (tiempo de permanencia del atacante).

## 🔗 Conexión con mi Biblioteca Teórica
[Defensa en Profundidad](../03-Bibliografia-Teorica/Defensa-en-Profundidad.md)

## 🏁 Resultado del Laboratorio Práctico
* **Actividad:** Port Scanning.
* **Origen:** Host NESSUS (10.0.0.8).
* **Destino:** 10.0.0.3.
* **Clasificación:** Falso Positivo (Actividad autorizada por el equipo de vulnerabilidades).
* **Bandera obtenida:** `THM{000_INTRO_TO_SOC}`

### 💡 Lección Aprendida
Como Analista Tier 1, la comunicación interna es vital. Identificar que el origen era un escáner **NESSUS** y cruzarlo con los avisos del equipo de vulnerabilidades permitió cerrar una alerta de alta severidad como falso positivo rápidamente.

---

## 🏁 Conclusión
El SOC es el cerebro de la ciberseguridad defensiva. Mi rol como Junior será ser los "ojos" que filtran el ruido para encontrar las amenazas reales.
