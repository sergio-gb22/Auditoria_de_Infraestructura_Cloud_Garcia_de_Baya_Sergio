# Refactorización con Indicadores XSD - TechNova Cloud
---

### a) ¿Cuántas líneas de código habéis ahorrado al usar grupos?

**Antes de la refactorización:**
- Los atributos del servidor (id, rack, estado) se declaraban individualmente dentro de cada `<servidor>`.
- El bloque `<hardware>` se repetía en línea con todos sus elementos hijos.

**Después de la refactorización:**

| Indicador | Líneas ahorradas |
|-----------|------------------|
| `attributeGroup` (AtributosServidor) | Se definen 3 atributos **una sola vez** y se reutilizan. Ahorro aproximado: **3 líneas × número de servidores** (en nuestro caso 4 servidores = 12 líneas evitadas). |
| `group` (ComponentesHardware) | El bloque hardware completo se define una vez y se referencia. Ahorro aproximado: **25 líneas × número de servidores** = **100 líneas evitadas**. |

**Total estimado de ahorro:** más de **110 líneas** de código en el XSD, sin contar la mejora en legibilidad y mantenibilidad.

---

### b) ¿Qué error os da VS Code si intentáis poner dos servidores con el mismo ID?

Al intentar validar un XML donde dos servidores comparten el mismo `id` (por ejemplo, duplicar `srv-web-01`), VS Code (o cualquier validador XSD) muestra un error similar a: Duplicate unique value [srv-web-01] declared for identity constraint "UnicoID" of element "catalogo_cloud".
