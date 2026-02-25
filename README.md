# FINZ · Tu copiloto financiero

FINZ es una **web app tipo dashboard** que actúa como **copiloto del departamento financiero**, especializada en **gestión de facturas de proveedores**: recepción, archivo y preparación para procesos de contabilización y cuentas a pagar.

> Estado actual: implementado el flujo **“Recepcionar y archivar facturas”** en **modo demo**.  
> Las secciones **“Subir facturas a contabilidad”** y **“Gestionar cuentas a pagar”** aparecen como **Próximamente** (deshabilitadas).

---

## Problema que resuelve
En muchos equipos financieros, la recepción y archivo de facturas desde un buzón compartido implica tareas repetitivas:
- revisar emails
- descargar adjuntos
- renombrar archivos con criterios consistentes
- archivar en carpetas correctas
- mantener visibilidad del progreso y de lo pendiente

FINZ centraliza este proceso en un **dashboard** y guía al usuario con **progreso visible**, **resumen diario** y un **chatbot de soporte**, reduciendo fricción operativa y mejorando control y trazabilidad.

---

## Rol del agente (FINZ)
FINZ actúa como **copiloto operativo** del equipo financiero, con estos principios:

- **Ejecución:** si una petición es viable, segura y conocida, FINZ ejecuta y entrega el resultado en el formato esperado.
- **Alternativas:** si hay varias opciones, FINZ las presenta brevemente para que el usuario decida.
- **Preguntas:** si falta un dato para ejecutar, FINZ pregunta (no asume).
- **Detección de fallos:** si el usuario propone una acción incorrecta, FINZ lo indica de forma escueta, explica la causa y propone la alternativa correcta.
- **Prohibido inventar datos:** si no hay certeza, FINZ solicita validación o marca pendiente.

---

## Funcionalidades

### Dashboard
- **Pestañas con contadores** (Recepción, Validación IA, Contabilización, Pago programado).
- **Tarjetas informativas** con resumen de actividad y tareas pendientes.
- **Tabla “Resumen del día”** alimentada dinámicamente desde el estado/base de datos, con **iconos de estado**.

### Menú lateral
- ✅ **Recepcionar y archivar facturas** (activo)
- ⛔ **Subir facturas a contabilidad** (deshabilitado · Próximamente)
- ⛔ **Gestionar cuentas a pagar** (deshabilitado · Próximamente)

### Chatbot integrado (IA)
- Chat flotante en el dashboard.
- Usa el modelo **gpt-4o-mini** mediante la **API de OpenAI**.
- Enfocado en: consultas, ayuda operativa, explicación de estados y guía de uso.
- No ejecuta acciones críticas sin intervención/confirmación del usuario.

---

## Flujo básico de uso

### A) Recepcionar y archivar facturas (modo demo)
1. En el menú lateral, pulsa **“Recepcionar y archivar facturas”**.
2. En el modal, selecciona **Fecha desde** y **Fecha hasta**.
3. Pulsa **Iniciar**.
4. El panel muestra un **estado de progreso** que simula el proceso:
   - Conectando con Outlook
   - Buscando correos
   - Descargando adjuntos
   - Archivando
5. El dashboard actualiza:
   - tarjetas de resumen
   - contadores
   - tabla “Resumen del día”

### B) Consultas con el chatbot
1. Abre el chat flotante.
2. Pregunta, por ejemplo:
   - “¿Qué significa Validación IA?”
   - “¿Qué hago si falta el número de factura?”
3. FINZ responderá sin inventar datos y pidiendo lo necesario si falta información.

---

## Herramientas utilizadas
- **Frontend:** HTML + CSS + JavaScript (vanilla)
- **Backend:** Node.js + Express
- **IA / Chatbot:** OpenAI API (modelo `gpt-4o-mini`)
- **Ejecución/entorno:** Replit
- **Control de versiones:** GitHub

> Integración con Outlook: actualmente simulada (demo). Previsto Microsoft Graph en próximas iteraciones.

---

## Instalación y ejecución

### Requisitos
- Node.js (recomendado 18+)
- API Key de OpenAI (para el chatbot)

### Instalar dependencias
```bash
npm install
