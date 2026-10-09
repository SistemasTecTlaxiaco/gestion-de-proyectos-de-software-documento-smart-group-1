# Documento Detallado: Objetivo SMART y Análisis de Viabilidad Multidimensional
**Asignatura:** Gestión de Proyectos de Software (SCG-1009)  
**Unidad 3:** Planificación del Proyecto  
**Iniciativa / Ecosistema:** Open Hub Tec (Instituto Tecnológico de Tlaxiaco)  
**Proyecto:** TisaaSavi / Noble Origen (Trazabilidad y Liquidación Textil)  
**Marco de Trabajo:** eduScrum (Sprint 3)  
**Fecha:** 09 Octubre 2026  

---

## 1. Formulación del Objetivo SMART.

> **Objetivo del Proyecto:**  
> "Desarrollar y validar un Producto Mínimo Viable (MVP) con arquitectura *offline-first* y contratos inteligentes en Soroban (Stellar) para registrar la autoría inmutable de al menos **50 prendas artesanales** y dispersar liquidaciones con costo de gas patrocinado (*fee-bump*) a **15 talleres textiles** de la Mixteca Alta oaxaqueña, alcanzando un tiempo de carga inferior a **3 segundos en redes 2G** y una tasa de éxito transaccional del **98%**, en un periodo de **14 semanas (Sprints 1 al 4)** bajo el marco eduScrum."

### Desglose de Dimensiones SMART:
* **Specific (Específico):** Construcción de un protocolo *phygital* (físico-digital) que combina captura local tolerante a fallos, hashes de certificación en IPFS/Stellar y liquidación ética para artesanos mixtecos.
* **Measurable (Medible):** Certificación de 50 piezas reales, vinculación de 15 talleres, payload web ≤ 25 KB y latencia de respuesta ≤ 3 s en conectividad rural.
* **Achievable (Alcanzable):** Respaldado por el dimensionamiento del backlog (33 horas estimadas de aseguramiento de calidad distribuidas en el semestre).
* **Relevant (Relevante):** Erradica la apropiación cultural no autorizada y mitiga la intermediación abusiva que absorbe hasta el 80% del margen comercial artesanal.
* **Time-bound (Temporalizado):** Ejecución estructurada en 4 Sprints quincenales/mensuales completándose al cierre del semestre académico.

---

## 2. Trazabilidad con Sprints 1 y 2 (Backlog y Costo de la Calidad).

El presente plan de viabilidad se sustenta rigurosamente en las métricas de ingeniería de software obtenidas en los ciclos previos:

### A. Trazabilidad con Historias de Usuario (Sprint 1)
* **HU-01 (Autenticación SMS OTP - 5 pts):** Acceso resiliente para artesanos mediante verificación móvil sin dependencia de cuentas de correo tradicionales.
* **HU-02 (Registro Fotográfico Offline - 8 pts):** Almacenamiento local mediante Canvas HTML5 (≤ 400 KB) e IndexedDB tolerante a caídas de red.
* **HU-03 (Certificado IPFS/Web3 Gasless - 8 pts):** Despliegue de transacciones patrocinadas (*Sponsored Reserves / Fee-bump*) para abstraer comisiones en Soroban.
* **HU-04 (Consulta QR en Red 2G - 5 pts):** Interfaz pública ligera con arquitectura HTML-first (≤ 25 KB).
* **HU-05 (Retribución Directa CLABE - 5 pts):** Dispersión transparente protegida con cifrado AES-256-GCM.

### B. Insumos del Costo de la Calidad (Sprint 2 - CoQ)
A partir de la auditoría de calidad realizada a una tarifa estándar de **$150.00 MXN / hora**:
* **Inversión en Prevención (56.06% / 18.5 h):** $2,775.00 MXN destinados a mitigación de fallos, diseño de Service Workers y tipado estático.
* **Inversión en Corrección (43.94% / 14.5 h):** $2,175.00 MXN asignados a gestión de cuotas de almacenamiento en teléfonos básicos y excepciones de red rural.
* **Costo Total de Calidad del Backlog Base:** **$4,950.00 MXN** (33.0 horas hombre), lo cual demuestra realismo operativo sin incurrir en supuestos inviables de "cero defectos".

---

## 3. Análisis de Viabilidad Técnica y Operativa

### A. Viabilidad Técnica en el Entorno Mixteco
1. **Infraestructura de Conectividad Intermitente:** La solución implementa sincronización en segundo plano con Service Workers y persistencia local (IndexedDB). Si la señal 2G/3G colapsa, los datos de las piezas se encolan y firman localmente hasta reconectar con el RPC de Stellar.
2. **Limitaciones de Hardware Local:** El procesamiento de imágenes se comprime en el cliente a ≤ 400 KB para evitar desbordamientos de memoria en dispositivos Android de gama de entrada.
3. **Abstracción Criptográfica (UX Sin Barreras):** Implementación de Passkeys/WebAuthn y transacciones patrocinadas. Los artesanos no compran criptomonedas ni gestionan frases semilla; la plataforma absorbe los costos de red mediante billeteras patrocinadoras.

### B. Viabilidad Operativa en el Marco eduScrum
* **Estructura del Equipo:** Organización de 4 a 5 estudiantes asumiendo roles de desarrollo cruzado (Frontend/Offline, Smart Contracts en Rust, QA/Documentación).
* **Capacidad de Carga:** El equipo cuenta con una disponibilidad de 10 a 12 horas semanales por integrante. La carga restante del backlog (estimada en ~120 horas de desarrollo global + 33 horas de CoQ) es perfectamente absorbible en el calendario escolar.
* **Supervisión y Ritmo:** Sprints de dos semanas con revisiones de Definition of Done (DoD), retrospectivas y validación continua con el Product Owner del Hub.

---

## 4. Análisis de Viabilidad Financiera Web3 y Dictamen Go / No-Go

### A. Estructura de Costos del Proyecto (Estimación a 6 Meses)
* **Desarrollo y Calidad (Horas de Ingeniería):** $18,000.00 MXN (~$950 USD).
* **Infraestructura Cloud, RPCs e IPFS Pinning:** $3,600.00 MXN (~$190 USD).
* **Materiales de Validación en Campo (Etiquetas NFC/QR físicas y traslados):** $5,500.00 MXN (~$290 USD).
* **Costo Total Estimado:** **$27,100.00 MXN (~$1,430 USD)**.

### B. Mecanismos de Financiamiento Web3
1. **Stellar Community Fund (SCF - Build / Activation Award):**  
   * Convocatoria orientada a inclusión financiera e impacto en bienes del mundo real (RWA) bajo licencia de código abierto.
   * Rango de financiamiento accesible: **$5,000 a $15,000 USD** en USDC/XLM tras validación de MVP. El capital cubre holgadamente el 100% de los costos operativos y de desarrollo.
2. **Drips Protocol (Streaming Continuo de Dependencias):**  
   * Financiamiento continuo *on-chain* direccionado al repositorio de GitHub (`SistemasTecTlaxiaco/...`).
   * Permite que los colaboradores activos del Hub y las dependencias de código abierto en Rust reciban micro-flujos de fondos por bloque, asegurando el mantenimiento post-materia.

### C. Dictamen Formal de Viabilidad

| Dimensión | Evaluación | Justificación Resumida |
| :--- | :---: | :--- |
| **Técnica** | **VIABLE** | Arquitectura tolerante a desconexión y abstracción total de gas para comunidades rurales. |
| **Operativa** | **VIABLE** | Backlog dimensionado en 33 h de calidad y distribución factible en el equipo eduScrum. |
| **Financiera** | **VIABLE** | Los costos del proyecto ($1,430 USD) están cubiertos en más de un 300% por los tramos iniciales de SCF y Drips. |

> ### DICTAMEN FINAL: **GO (PROYECTO VIABLE Y APROBADO)**  
> Se autoriza el paso a la fase de ejecución integral del Sprint 3. El proyecto satisface las condiciones de impacto territorial, sostenibilidad económica mediante mecanismos Web3 y factibilidad técnica bajo las restricciones del entorno regional de la Mixteca.

---

## 5. Gestión del Equipo y Gobernanza eduScrum

* **Product Owner:** Supervisión de criterios de aceptación y alineación con el ecosistema Open Hub Tec.
* **eduScrum Master:** Lizeth Nallely López García (Facilitación de impedimentos, monitoreo del tablero de tareas y cumplimiento del DoD).
* **Equipo de Desarrollo:** Autogestión de tareas técnicas, revisiones por pares mediante Pull Requests y auditorías cruzadas de código/documentación.
