# 🐧 Laboratorio 04: Análisis Forense de Logs (Grep & Cut)

**Fecha:** 10 de Enero, 2026
**Herramientas:** Terminal, grep, pipe (|), wc, cut
**Categoría:** Threat Hunting / Linux Basics

---

## 🎯 Objetivo
Simular la detección manual de un incidente de seguridad (Fuerza Bruta) analizando archivos de log crudos ("raw logs") sin utilizar herramientas gráficas, solo comandos de terminal.

---

## 🔬 Escenario
El equipo de seguridad sospecha de intentos de acceso no autorizado en el servidor SSH. Se ha proporcionado una captura de logs (`simulacion.log`) y mi misión es filtrar el ruido para encontrar al atacante.

---

## 🛠️ Procedimiento y Comandos

### 1. Filtrado de Amenazas (`grep`)
Busqué líneas que indicaran fallos de autenticación. Aprendí que Linux distingue mayúsculas de minúsculas (*Case Sensitive*), por lo que "failed" no funcionó, pero "Failed" sí.
```bash
grep "Failed" simulacion.log
