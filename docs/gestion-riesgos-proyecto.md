# Gestión de Riesgos del Proyecto

**Institución:** Tecnológico Nacional de México (TecNM), Instituto Tecnológico de Tlaxiaco

**Asignatura:** Gestión de Proyectos de Software — SCG-1009

**Unidad 3:** Planificación del Proyecto — Temas 3.5.1 al 3.5.4

**Marco de trabajo:** eduScrum — Sprint 3

**Iniciativa:** Open Hub Tec

**Proyecto:** TisaaSavi — Trazabilidad y Liquidación Textil

**Región de aplicación:** Mixteca de Oaxaca

**Fecha de elaboración:** 21 de octubre de 2026

**Versión:** 1.0 — Línea base de riesgos y plan de respuesta

**Estado:** Evidencia documental de planificación; acciones, pruebas y aceptación residual pendientes de ejecución y validación.

## 1. Propósito, alcance y correspondencia académica

Identificar, analizar, priorizar y atender los riesgos que pueden impedir la validación del MVP con 50 prendas y 15 talleres, comprometer la captura offline, la certificación, la consulta QR o la liquidación directa. El registro comprende las dimensiones técnica, social y operativa, y financiera/Web3 durante el Sprint 3 y su seguimiento posterior.

Para organizar esta evidencia se utiliza la siguiente correspondencia funcional; no se presenta como transcripción de los títulos oficiales del programa:

| Tema | Evidencia incluida | Resultado revisable |
| :--- | :--- | :--- |
| 3.5.1 | Identificación de riesgos, causas y consecuencias | Seis riesgos en tres dimensiones |
| 3.5.2 | Análisis cualitativo de probabilidad e impacto | Escalas y severidad calculada |
| 3.5.3 | Priorización y planificación de respuestas | Matriz ordenada, prevención y contingencia |
| 3.5.4 | Seguimiento y control | Disparadores, responsables, evidencias y revisión eduScrum |

**Base documental:** [Objetivo SMART y análisis de viabilidad multidimensional](planificacion-smart-viabilidad.md), en particular sus secciones 2, 4 y 5. Las valoraciones P/I y las asignaciones específicas de 3.5 h y 4.0 h de corrección son insumos de esta actividad. No representan incidentes observados ni horas ya ejecutadas.

## 2. Marco metodológico

### 2.1. Evaluación cualitativa

**Severidad (S) = Probabilidad (P, escala 1–5) × Impacto (I, escala 1–5).** El resultado varía entre 1 y 25. Se evalúa la exposición inherente, antes de aplicar las respuestas. La escala es ordinal: no equivale a una probabilidad estadística ni a una pérdida monetaria esperada.

| Valor | Probabilidad | Criterio de ocurrencia durante el horizonte del proyecto | Impacto | Criterio sobre los objetivos |
| :---: | :--- | :--- | :--- | :--- |
| 1 | Muy baja | Evento excepcional, sin señales actuales y con controles disponibles | Insignificante | Ajuste local sin afectar entregables ni compromisos |
| 2 | Baja | Evento posible bajo una combinación poco frecuente de condiciones | Menor | Retrabajo acotado dentro de la capacidad del Sprint |
| 3 | Media | Dependencia o condición que puede presentarse durante la ejecución | Moderado | Degrada una funcionalidad o exige replanificar tareas |
| 4 | Alta | Exposición recurrente o condiciones del entorno que favorecen el evento | Grave | Bloquea una HU esencial, un hito o una operación sensible |
| 5 | Muy alta | Evento esperado si no se interviene | Muy grave | Compromete la adopción, la confianza o la continuidad del proyecto |

Se selecciona el impacto más alto entre las consecuencias técnicas, sociales, económicas y de calendario; no se promedian daños que puedan ocultar afectaciones a la comunidad. Las puntuaciones iniciales son juicios de planificación que deben contrastarse con pruebas y validación de campo.

### 2.2. Priorización y criterios de actuación

| Severidad | Prioridad | Tratamiento |
| :---: | :--- | :--- |
| 1–5 | Baja | Aceptación activa posible, responsable y revisión al cierre del Sprint |
| 6–10 | Media (Medio) | Mitigación programada y revisión semanal; escalar al activarse un disparador |
| 11–25 | Alta/Crítica (Crítico) | Incorporar acciones al Sprint Backlog y revisar en cada reunión diaria; bloquear la operación afectada si no hay un control seguro |

El umbral **12 se clasifica como Crítico**, conforme a la convención requerida para esta actividad. La etiqueta Alta/Crítica representa una sola categoría. En empates se atiende primero el riesgo con mayor impacto directo en las personas, después el que amenaza la continuidad financiera. Un disparador materializado puede adelantar la atención de cualquier riesgo.

**Estrategias:** mitigar reduce P o I; evitar retira la condición que genera la exposición; transferir delega una obligación mediante un acuerdo verificable sin eliminar la responsabilidad del proyecto; aceptar reconoce una exposición residual con vigilancia y una respuesta preparada. Contratar un proveedor no transfiere por sí solo todo el riesgo.

## 3. Identificación en las tres dimensiones

### 3.1. Dimensión técnica

**R-TEC-01 — Desbordamiento de cuota de memoria/almacenamiento en IndexedDB en dispositivos móviles de gama baja.** La captura repetida de fotografías, poco espacio libre y límites del navegador pueden causar fallos de escritura, pérdida de capturas no sincronizadas o bloqueo del registro. Se distingue la cuota de almacenamiento persistente de la memoria RAM: esta matriz atiende principalmente la primera. Afecta a **HU-02**, a la evidencia de autoría y a la meta de 50 prendas. **P=4; I=4; S=16 (Crítico).** Referencia de corrección CoQ: **3.5 h = $525 MXN**. Señales: uso estimado de cuota ≥80%, cola que no se vacía o cualquier `QuotaExceededError`. El 80% es un umbral preventivo propuesto, no una garantía del navegador.

**R-TEC-02 — Expiración del almacenamiento on-chain por alquiler de estado (State Rental) en Soroban/Stellar.** La falta de monitoreo o de fondos para extender la vida del estado puede dejar certificados inaccesibles y afectar **HU-03**. El estado persistente o de instancia puede archivarse y requerir restauración; el temporal puede eliminarse al expirar, por lo que no debe albergar la evidencia durable única. **P=2; I=4; S=8 (Medio).** Referencia de corrección CoQ: **4.0 h = $600 MXN**. Señales: TTL restante inferior al margen configurado, saldo insuficiente para mantenimiento o simulación que indica estado archivado. El margen se fijará en ledgers, según la red y la frecuencia real de monitoreo, antes del despliegue.

### 3.2. Dimensión social y operativa — Mixteca

**R-SOC-01 — Desconfianza comunitaria y barrera lingüística en Tu'un Savi.** Interfaces y explicaciones que no correspondan a la variante lingüística local, ausencia de acompañamiento o falta de claridad sobre autoría y uso de datos pueden impedir el acceso y la comprensión del certificado. Afecta a **HU-01 y HU-04** y a la incorporación voluntaria de los 15 talleres. **P=4; I=5; S=20 (Crítico).** Señales: rechazo expreso, imposibilidad de explicar con palabras propias el consentimiento o dificultades repetidas en dos sesiones de validación. No se presume que toda la comunidad comparta una misma lengua, preferencia o nivel de confianza.

**R-SOC-02 — Rechazo o temor fiscal al registrar cuentas bancarias (CLABE) para liquidación directa.** La incertidumbre sobre el destino de los datos, las obligaciones percibidas o la titularidad bancaria puede detener la vinculación y el pago en **HU-05**. **P=3; I=4; S=12 (Crítico).** Señales: negativa a proporcionar CLABE, solicitud de retirar datos o dudas que impiden un consentimiento informado. La respuesta no debe presionar a la persona ni prometer exenciones o resultados fiscales.

### 3.3. Dimensión financiera y Web3

**R-FIN-01 — Demoras en aprobación de tramos del Stellar Community Fund (SCF) o fluctuación cambiaria.** Un desfase entre desembolsos y compromisos, o una menor conversión neta a MXN, puede impedir cubrir desarrollo, infraestructura y validación de campo. Línea base: **$1,430 USD / $27,100 MXN**, equivalencia presupuestal aproximada, no cotización vigente. Afecta transversalmente a HU-01–HU-05. **P=3; I=4; S=12 (Crítico).** Señales: desembolso previsto no confirmado al planear el Sprint, disponibilidad insuficiente para el próximo compromiso o variación desfavorable ≥5% respecto de la conversión presupuestada.

**R-FIN-02 — Interrupción de flujos continuos de streaming en Drips Protocol por dependencias de terceros.** Cambios o cancelaciones del donante, saldo agotado, indisponibilidad de RPC/interfaz o incidencias del protocolo pueden reducir la financiación del mantenimiento. **P=2; I=3; S=6 (Medio).** Afecta al soporte de infraestructura y de las HU de forma transversal, sin constituir una HU independiente documentada. Señales: flujo configurado detenido, saldo insuficiente para el siguiente periodo o imposibilidad persistente de consultar o cobrar por los canales previstos. Un fallo de interfaz no demuestra por sí solo que el flujo on-chain se haya detenido.

## 4. Matriz consolidada de riesgos

| Orden | ID | Dimensión | Riesgo resumido | HU / alcance | P | I | S=P×I | Prioridad |
| :---: | :--- | :--- | :--- | :--- | :---: | :---: | :---: | :--- |
| 1 | R-SOC-01 | Social y operativa | Desconfianza y barrera lingüística | HU-01, HU-04 | 4 | 5 | 20 | Crítico |
| 2 | R-TEC-01 | Técnica | Cuota de IndexedDB excedida | HU-02 | 4 | 4 | 16 | Crítico |
| 3 | R-SOC-02 | Social y operativa | Rechazo al registro de CLABE | HU-05 | 3 | 4 | 12 | Crítico |
| 4 | R-FIN-01 | Financiera y Web3 | Demora SCF o variación cambiaria | HU-01–HU-05 / presupuesto | 3 | 4 | 12 | Crítico |
| 5 | R-TEC-02 | Técnica | Expiración del estado Soroban | HU-03 | 2 | 4 | 8 | Medio |
| 6 | R-FIN-02 | Financiera y Web3 | Interrupción de streaming Drips | Mantenimiento transversal | 2 | 3 | 6 | Medio |

**Balance:** cuatro riesgos críticos, dos medios y ninguno bajo. Todas las respuestas siguientes son propuestas de control; no se atribuye una reducción residual sin evidencia de eficacia.

## 5. Estrategias de respuesta y responsables

### 5.1. Responsabilidad nominal y roles eduScrum

La sección 5 del documento de viabilidad identifica a **Lizeth Nallely López García — eduScrum Master**. No aporta nombres para los roles de especialidad. Por ello, este plan le asigna la responsabilidad nominal propuesta de coordinar y dar seguimiento a los seis riesgos; la aceptación de esta asignación y los nombres de los ejecutores se registrarán en el Sprint Planning. No implica que deba ejecutar personalmente todas las tareas técnicas.

Frontend Offline, Smart Contracts, UX y Seguridad/QA son especialidades del equipo de desarrollo dentro de eduScrum. Las asignaciones por especialidad siguientes permiten planificar el trabajo sin inventar miembros del equipo. La falta de ejecutor nominal se tratará como impedimento antes de comenzar la acción correspondiente.

### 5.2. R-TEC-01 — Mitigar y evitar pérdida de datos

- **Responsable nominal de seguimiento:** Lizeth Nallely López García (eduScrum Master). **Ejecutor:** Frontend Offline; verificación por Seguridad/QA. Nombres pendientes de asignación.
- **Acción preventiva:** comprimir imágenes a ≤400 KB conforme a HU-02, consultar `navigator.storage.estimate()` cuando esté disponible, capturar errores de escritura y probar la saturación en dispositivos representativos. Solicitar persistencia cuando proceda, sin asumir que será concedida. Mantener identificadores únicos y confirmación de sincronización; eliminar únicamente copias locales ya confirmadas y prescindibles.
- **Contingencia operativa:** ante el disparador, suspender nuevas capturas pesadas, conservar la cola pendiente y mostrar un estado comprensible. Sincronizar al recuperar conectividad o realizar una exportación protegida con consentimiento hacia un dispositivo autorizado. Reintentar con deduplicación; verificar conteos y hashes antes de liberar espacio. Nunca borrar capturas pendientes para recuperar cuota.
- **Evidencia de control:** prueba de saturación y reconexión sin pérdida ni duplicación, bitácora sin datos personales y medición de tamaños. Revisar antes del piloto y en cada cambio de persistencia. Registrar el consumo de las 3.5 h de corrección, sin confundir estimación con tiempo real.

### 5.3. R-TEC-02 — Mitigar y evitar almacenamiento temporal para evidencia durable

- **Responsable nominal de seguimiento:** Lizeth Nallely López García (eduScrum Master). **Ejecutor:** Smart Contracts; verificación por Seguridad/QA. Nombres pendientes de asignación.
- **Acción preventiva:** clasificar las entradas por duración, utilizar almacenamiento persistente para el registro durable y monitorear TTL y fondos. Programar extensión antes del margen configurado; validar estimaciones de costo y alertas en testnet. Mantener referencias verificables del certificado e IPFS; extender TTL no reemplaza el pinning de IPFS.
- **Contingencia operativa:** pausar la emisión afectada y mostrar estado de recuperación. Identificar las entradas archivadas, simular y ejecutar la restauración financiada por el proyecto, extender TTL y comprobar integridad antes de reanudar. Si se eliminó estado temporal, reconstruir solo desde evidencia íntegra verificable; de no existir, escalar el incidente y no afirmar recuperación ni autenticidad.
- **Evidencia de control:** ensayo de extensión y restauración en testnet, ledger de referencia y comprobación de certificados. Revisión automatizada con frecuencia menor al margen de TTL y revisión humana semanal. Registrar las 4.0 h de corrección previstas y cualquier desviación.

### 5.4. R-SOC-01 — Mitigar mediante participación comunitaria

- **Responsable nominal de seguimiento:** Lizeth Nallely López García (eduScrum Master). **Ejecutor:** UX con facilitación comunitaria; apoyo de Frontend Offline. Nombres pendientes de asignación.
- **Acción preventiva:** acordar con cada taller el idioma y la variante de Tu'un Savi, validar mensajes con una persona hablante aceptada por la comunidad, explicar autoría y tratamiento de información mediante demostraciones y ofrecer acompañamiento para OTP y QR. Verificar comprensión sin exigir conocimientos Web3.
- **Contingencia operativa:** detener el registro o publicación cuando no haya comprensión o consentimiento; realizar una sesión acompañada, rediseñar mensajes y permitir posponer o rechazar la incorporación. Documentar la decisión de forma mínima y replanificar la validación con el Product Owner sin forzar la meta de 15 talleres.
- **Evidencia de control:** guion validado, resultados anonimizados de tareas HU-01/HU-04 y registro de consentimiento conforme al proceso acordado. Revisar antes de cada visita y en Sprint Review. No publicar datos personales ni materiales culturales sin autorización.

### 5.5. R-SOC-02 — Mitigar, evitar captura no consentida y transferir tareas especializadas

- **Responsable nominal de seguimiento:** Lizeth Nallely López García (eduScrum Master). **Ejecutor:** Seguridad/QA y UX. Nombres pendientes de asignación.
- **Acción preventiva:** explicar finalidad, acceso y conservación de CLABE; minimizar datos y protegerlos según HU-05, separando llaves de cifrado y datos. No registrar CLABE en cadena ni en bitácoras. Coordinar orientación fiscal individual con una persona profesional competente, sin sustituirla con afirmaciones del equipo.
- **Transferencia delimitada:** proponer que un proveedor de pagos asuma validación y dispersión bajo un acuerdo verificable de servicio y tratamiento de datos. La contratación y su costo quedan pendientes de validación; no se presume un convenio existente ni se transfiere la responsabilidad de obtener consentimiento.
- **Contingencia operativa:** suspender la vinculación y la dispersión afectada, conservar un registro protegido de la obligación pendiente, ofrecer aclaración acompañada y reintentar solo con consentimiento y titularidad verificados. Toda alternativa de liquidación requiere validación operativa del Product Owner y aceptación de la persona beneficiaria; no usar cuentas de terceros improvisadas.
- **Evidencia de control:** prueba con datos sintéticos, ausencia de CLABE en logs/on-chain y flujo de pausa, consentimiento y reanudación. Revisar antes de cada alta y en cada incidente; mantener el pago como pendiente hasta confirmación conciliada.

### 5.6. R-FIN-01 — Mitigar, evitar compromisos sin respaldo y aceptar exposición residual acotada

- **Responsable nominal y coordinación ejecutora:** Lizeth Nallely López García (eduScrum Master), con validación de compromisos por el Product Owner, cuyo nombre no consta en la fuente.
- **Acción preventiva:** llevar calendario de solicitud, aprobación y disponibilidad de cada tramo; separar fondos solicitados, aprobados y efectivamente recibidos. Actualizar semanalmente el flujo de caja en MXN con conversión neta y comisiones comprobables. No financiar compromisos obligatorios con adjudicaciones hipotéticas. Proponer una reserva objetivo de 10% ($2,710 MXN), sujeta a identificar una fuente real o repriorizar partidas; no está autorizada ni se suma automáticamente a la línea base.
- **Contingencia operativa:** al activarse el disparador, congelar gastos discrecionales no comprometidos, ordenar pagos esenciales por disponibilidad real, ajustar hitos y alcance con el Product Owner y buscar una fuente institucional o aportación documentada. Detener el siguiente compromiso si no hay cobertura; comunicar el impedimento al equipo y reestimar el Sprint.
- **Aceptación residual:** admitir variaciones menores al umbral solo si el saldo disponible cubre compromisos y se registra la decisión. No asumir que una demora es aceptable si bloquea infraestructura o pagos.
- **Evidencia de control:** flujo de caja semanal, comprobantes de desembolso y registro de decisiones. El presupuesto de referencia permanece en $27,100 MXN; cualquier reserva adicional o cambio se somete a control de cambios.

### 5.7. R-FIN-02 — Mitigar y aceptar únicamente interrupciones tolerables

- **Responsable nominal de seguimiento:** Lizeth Nallely López García (eduScrum Master). **Ejecutor:** Smart Contracts y Seguridad/QA. Nombres pendientes de asignación.
- **Acción preventiva:** verificar configuración, saldo financiador y cantidades efectivamente cobrables; distinguir flujo previsto, acumulado y cobrado. Monitorear diariamente durante el piloto y antes de cualquier gasto dependiente. Documentar red, token y costos de cobro: no asumir interoperabilidad directa con Stellar. Mantener los gastos esenciales fuera de una dependencia exclusiva de donaciones continuas.
- **Contingencia operativa:** comprobar el contrato por un RPC alternativo autorizado para diferenciar un fallo de interfaz de una interrupción real. Si el flujo cesó, registrar el faltante, activar únicamente fondos alternos disponibles y aprobados, suspender servicios no esenciales y reprogramar mantenimiento. Reanudar tras comprobar cobro y conciliación; evitar cobros duplicados o nuevas transferencias sin verificación.
- **Aceptación residual:** tolerar una interrupción temporal solo si no afecta servicios críticos ni compromisos y existe cobertura real documentada. Escalar de inmediato cuando amenace el siguiente pago.
- **Evidencia de control:** consulta verificable de saldo y flujo, prueba de fallo de RPC, conciliación y bitácora del incidente. Usar R-FIN-01 cuando el evento produzca un déficit presupuestal común, evitando duplicar reservas por la misma pérdida.

## 6. Trazabilidad y coherencia entre Sprints

### 6.1. Historias de Usuario — Sprint 1

Las descripciones y puntos proceden de la sección 2.A del [documento de viabilidad](planificacion-smart-viabilidad.md). Los controles son criterios propuestos para la verificación del Sprint 3, no resultados ya alcanzados.

| Historia | Alcance base | Riesgos directos | Evidencia prevista para aceptación |
| :--- | :--- | :--- | :--- |
| HU-01 — 5 pts | Autenticación SMS OTP | R-SOC-01 | Uso acompañado y comprensión del acceso en el idioma acordado |
| HU-02 — 8 pts | Registro fotográfico offline, imágenes ≤400 KB | R-TEC-01 | Saturación, persistencia y sincronización sin pérdidas ni duplicados |
| HU-03 — 8 pts | Certificado IPFS/Web3 con gas patrocinado | R-TEC-02 | TTL monitoreado, restauración y certificado íntegro |
| HU-04 — 5 pts | Consulta QR en red 2G, interfaz ≤25 KB | R-SOC-01 | Consulta comprensible y validación del objetivo de carga ≤3 s |
| HU-05 — 5 pts | Retribución directa CLABE y AES-256-GCM | R-SOC-02 | Consentimiento, protección de datos y conciliación del pago |

R-FIN-01 condiciona la ejecución de todo el backlog; R-FIN-02 condiciona su mantenimiento. No se inventan historias nuevas para justificar su cobertura. La meta global de éxito transaccional del 98% requiere medición independiente y no se deduce de la severidad.

### 6.2. Costo de la Calidad — Sprint 2

| Concepto | Horas | Tarifa | Costo MXN | Relación con riesgos |
| :--- | ---: | ---: | ---: | :--- |
| Prevención | 18.5 | $150/h | $2,775 | Base para acciones preventivas; desglose por riesgo pendiente |
| Corrección | 14.5 | $150/h | $2,175 | Bolsa base de corrección del backlog |
| **CoQ total** | **33.0** | **$150/h** | **$4,950** | **18.5 + 14.5 = 33.0 h** |
| Subconjunto de corrección: R-TEC-01 / HU-02 | 3.5 | $150/h | $525 | Cuota de IndexedDB |
| Subconjunto de corrección: R-TEC-02 / HU-03 | 4.0 | $150/h | $600 | Expiración y recuperación del estado |
| Corrección restante | 7.0 | $150/h | $1,050 | Otros defectos del backlog, sin asignación individual acreditada |

Las últimas tres filas **desglosan** las 14.5 h de corrección; no se suman otra vez al total. Los dos riesgos técnicos concentran 7.5 h ($1,125 MXN), equivalentes al 51.72% de la corrección y al 22.73% del CoQ total. Las 33 h son de calidad, no la duración total del desarrollo. Las acciones sociales, el mantenimiento on-chain y eventuales servicios externos requieren estimación propia si exceden las bolsas existentes; no se declaran gratuitos ni cubiertos sin desglose.

### 6.3. Viabilidad financiera — Sprint 3

| Partida de la línea base | MXN | Riesgos relacionados |
| :--- | ---: | :--- |
| Desarrollo y calidad | $18,000 | R-TEC-01, R-TEC-02 y acciones de UX/QA |
| Infraestructura Cloud, RPC e IPFS | $3,600 | R-TEC-02, R-FIN-01, R-FIN-02 |
| Etiquetas y validación de campo | $5,500 | R-SOC-01, R-SOC-02, R-FIN-01 |
| **Total** | **$27,100** | **Referencia aproximada: $1,430 USD** |

El documento base agrupa desarrollo y calidad en $18,000, pero también menciona ~120 h de desarrollo más 33 h de CoQ. No acredita si los $4,950 de CoQ están íntegramente incluidos: **no se adicionan automáticamente** ni se afirma conciliación completa. Antes de comprometer gastos, el eduScrum Master y el Product Owner deben conciliar horas y partidas. Si el CoQ resultara adicional, el escenario sería $32,050 MXN, sujeto a aprobación de cambio, sin sustituir la línea base solicitada.

La relación $27,100 / $1,430 equivale aproximadamente a **18.951 MXN/USD** como referencia interna. Una reducción de 5% en el valor neto recibido en MXN dejaría $25,745 y una brecha de $1,355, si los costos permanecieran constantes. Es una sensibilidad presupuestal, no una predicción cambiaria.

El dictamen GO del documento previo expresa la decisión de planificación. Esta matriz identifica que el repositorio no aporta comprobantes de adjudicación, desembolso SCF ni cobro Drips: **el financiamiento esperado no prueba disponibilidad efectiva**. Se propone condicionar nuevos compromisos a fondos confirmados y a controles críticos verificados. Esta propuesta no representa una aprobación nueva ni modifica silenciosamente el documento base.

## 7. Seguimiento, control y cierre en eduScrum

1. **Sprint Planning:** confirmar responsables y ejecutores, estimar acciones y trasladarlas al Sprint Backlog con ID de riesgo, HU, evidencia esperada y fecha relativa al piloto. Resolver el desglose presupuestal y el margen de TTL antes de habilitar las operaciones afectadas.
2. **Reunión diaria:** revisar los cuatro riesgos críticos, disparadores e impedimentos. Ante un evento, registrar causa, operación afectada, responsable, respuesta y siguiente revisión; escalar en la misma jornada cualquier bloqueo de datos, pagos o consentimiento.
3. **Revisión semanal:** revisar también los riesgos medios, fondos reales, dependencias y horas consumidas. Recalcular P e I únicamente con evidencia y conservar la valoración anterior con fecha y motivo.
4. **Sprint Review:** presentar pruebas y validaciones al Product Owner. La Definition of Done propuesta exige trazabilidad, controles ejecutados y evidencia de contingencia para la funcionalidad expuesta; un riesgo abierto no se considera mitigado por tener documentación.
5. **Retrospectiva:** comparar estimaciones y resultados, incorporar aprendizajes y ajustar acciones del siguiente Sprint.

| Campo de seguimiento | Registro requerido |
| :--- | :--- |
| Identidad | ID, fecha, versión y responsable nominal |
| Estado | Abierto, en tratamiento, materializado o cerrado |
| Ejecución | Acción, ejecutor nominal confirmado, plazo, horas estimadas/reales |
| Verificación | Enlace a issue, prueba o acta; sin información sensible |
| Riesgo residual | P e I reevaluados, severidad, justificación y fecha |
| Decisión | Aceptación por Product Owner o nueva respuesta; nombre y fecha |

**Estado inicial de los seis riesgos:** abiertos, con controles propuestos y riesgo residual aún no evaluado. El cierre exige comprobar eficacia, completar la contingencia cuando aplique y registrar la aceptación residual. No se incluyen firmas, actas ni resultados ficticios. La confirmación de integrantes, el desglose de costos y la validación de campo son pendientes operativos visibles de esta línea base.

## 8. Fuentes y límites de la evidencia

- [Documento de planificación y viabilidad del proyecto](planificacion-smart-viabilidad.md): fuente interna de HU, CoQ, presupuesto y nombre de la eduScrum Master.
- [MDN — Storage quotas and eviction criteria](https://developer.mozilla.org/en-US/docs/Web/API/Storage_API/Storage_quotas_and_eviction_criteria): cuotas dependientes del navegador y fallo `QuotaExceededError`; fundamenta R-TEC-01.
- [Stellar — Smart contract state archival](https://developers.stellar.org/docs/learn/fundamentals/contract-development/storage/state-archival) y [elección del tipo de almacenamiento](https://developers.stellar.org/docs/build/guides/storage/choosing-the-right-storage): TTL, archivo, restauración y eliminación de estado temporal; fundamentan R-TEC-02.
- [Drips — Overview](https://docs.drips.network/the-protocol/overview/) y [Introduction](https://docs.drips.network/): saldo financiado y configuración modificable de streams; fundamentan R-FIN-02.

Fuentes técnicas consultadas el 21 de octubre de 2026. Los umbrales preventivos, la reserva objetivo y los procedimientos son propuestas del presente plan. Las puntuaciones y relaciones específicas de corrección corresponden al enunciado de la actividad. Este documento acredita planificación de riesgos; no acredita implementación, trabajo de campo, financiamiento obtenido ni aprobación del equipo.
