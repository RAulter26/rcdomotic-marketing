# RC Domotic — Repositorio de Marketing

Este repositorio centraliza los recursos de planificación y ejecución de marketing para RC Domotic. Su objetivo es mantener coherencia en la comunicación, evitar repetición de mensajes y facilitar la generación de contenido semanal con base en información real y validada.

---

## Estructura del repositorio

```
rcdomotic-marketing/
├── exports/                     # Fuentes reales del catálogo (Inventario.pdf, CSV, XLSX, etc.)
├── contexto/                    # Archivos de referencia permanente
│   ├── servicios.md             # Catálogo real de servicios de RC Domotic
│   ├── catalogo-productos.md    # Productos reales con precio y disponibilidad
│   ├── enfoque-por-servicio.md  # Beneficios y ángulo de comunicación por servicio
│   ├── promociones-activas.md   # Promociones vigentes (solo datos reales y validados)
│   ├── tono-de-marca.md         # Voz, tono e identidad comunicacional
│   └── mensajes-usados.md       # Registro de copys y frases ya utilizados
│
├── instrucciones-agente.md      # Flujo obligatorio para el agente en cada ejecución
│
└── salidas/
    └── semanal/                 # Informes de planificación semanal generados
        └── marketing-semanal-YYYY-MM-DD.md
```

---

## Flujo obligatorio del agente

El agente debe leer `instrucciones-agente.md` antes de ejecutar cualquier tarea semanal. El orden es:

```
PASO 1 — Buscar fuente real del catálogo
         Prioridad: exports/ → contexto/ → raíz del repositorio
         Si no hay fuente → DETENER y avisar al usuario
                  ↓
PASO 2 — Actualizar contexto/catalogo-productos.md
         ID, nombre, categoría y precio exactos de la fuente
         Precio $0 → "Por validar". Stock 0 no descarta el producto.
                  ↓
PASO 3 — Actualizar contexto/promociones-activas.md
         Si no hay promos reales → escribir exactamente:
         "No hay promociones activas esta semana."
                  ↓
PASO 4 — Generar informe semanal
         Solo con productos y datos validados en los pasos anteriores
                  ↓
PASO 5 — Revisión humana antes de publicar
         El informe es una propuesta. No publicar sin revisión.
```

---

## Carpeta `exports/`

Aquí deben depositarse las exportaciones reales del catálogo antes de cada ejecución semanal.

| Formato aceptado | Ejemplo |
|---|---|
| PDF exportado desde Appdomotic | `Inventario.pdf` |
| CSV | `catalogo-YYYY-MM-DD.csv` |
| Excel | `catalogo-YYYY-MM-DD.xlsx` |
| JSON | `catalogo-YYYY-MM-DD.json` |

> Usar siempre la exportación más reciente. Incluir la fecha en el nombre del archivo cuando sea posible.

---

## Carpeta `contexto/`

Contiene los archivos que alimentan cada informe semanal. Deben mantenerse actualizados.

| Archivo | Descripción | Quién lo actualiza |
|---|---|---|
| `servicios.md` | Catálogo de servicios reales que ofrece RC Domotic | Equipo técnico / comercial |
| `catalogo-productos.md` | Productos individuales con precio real — actualizado por el agente desde la fuente | Agente (fuente: exports/) |
| `enfoque-por-servicio.md` | Ángulo de comunicación y beneficios de cada servicio | Marketing |
| `promociones-activas.md` | Promociones vigentes — actualizado por el agente | Agente (fuente: exports/) |
| `tono-de-marca.md` | Guía de voz, tono y estilo de comunicación | Marketing |
| `mensajes-usados.md` | Registro de copys y frases publicados para evitar repetición | Marketing |

---

## Regla crítica: sin datos inventados

> El agente nunca debe inventar productos, precios, promociones, descuentos ni beneficios no verificables.

- Si un precio es $0 en la fuente → `Por validar`
- Si no hay promociones reales → `No hay promociones activas esta semana.`
- Si no hay fuente real → detener y avisar al usuario
- Stock en 0 no descarta ningún producto

---

## Importante

- Los informes semanales son propuestas de planificación, no piezas listas para publicar.
- Toda información de precio, promoción o condición comercial debe verificarse antes de comunicarla al cliente.
- Los copys del informe son borradores. Deben revisarse antes de publicarse.
- Ver `instrucciones-agente.md` para el detalle completo del flujo.
