Lab 1: Iniciación en Linux y Auditoría de Logs
Fecha: 05 de Enero, 2026 Rol: Estudiante de Analista SOC

🎯 Objetivo
Configurar un entorno de trabajo seguro utilizando WSL (Windows Subsystem for Linux) y realizar una primera práctica de monitoreo de seguridad analizando registros del sistema (logs) en tiempo real.

🛠️ Herramientas Utilizadas
Sistema Operativo: Ubuntu (vía WSL en Windows).

Terminal: PowerShell y Bash.

Comandos Clave: ping, ls, grep, tail, sudo.

Monitoreo: htop.

📝 Pasos Realizados
1. Configuración del Entorno
Instalé Ubuntu dentro de Windows para tener un entorno nativo de Linux sin consumir excesivos recursos (RAM), permitiendo el uso de herramientas de línea de comandos.

2. Análisis de Red Básico
Realicé pruebas de conectividad para entender conceptos de IP y Puertos.

Verifiqué mi IP local.

Comprobé la conexión a internet mediante ping.

Analicé puertos abiertos con netstat para identificar conexiones cifradas (Puerto 443).

3. Gestión de Permisos y Archivos
Aprendí la diferencia entre un usuario estándar y el usuario Root (Administrador).

Creé directorios de trabajo y archivos de bitácora.

Intenté acceder a archivos sensibles (/etc/shadow) verificando que el sistema deniega el acceso a usuarios sin privilegios.

4. Simulación de Incidente y Análisis de Logs
Realicé una prueba de concepto ("Proof of Concept") de un evento de seguridad:

El Evento: Intentos fallidos de inicio de sesión con sudo.

La Detección: Utilicé el comando tail -f /var/log/auth.log para monitorear en tiempo real.

El Hallazgo: Logré capturar la evidencia del fallo de autenticación:

authentication failure; logname= uid=1000 ... ruser=mons

🧠 Conclusión y Aprendizaje
He aprendido que Linux registra cada evento del sistema. Como futuro Analista SOC, mi trabajo consiste en saber filtrar esta información (usando grep) para encontrar anomalías entre el ruido normal del sistema.
