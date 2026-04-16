# RC Domotic — Repositorio de Marketing

Este repositorio centraliza los recursos de planificación y ejecución de marketing para RC Domotic. Su objetivo es mantener coherencia en la comunicación, evitar repetición de mensajes y facilitar la generación de contenido semanal con base en información real y validada.

---

## Estructura del repositorio

```
rcdomotic-marketing/
├── contexto/                    # Archivos de referencia permanente
│   ├── servicios.md             # Catálogo real de servicios de RC Domotic
│   ├── catalogo-productos.md    # Productos reales con precio y disponibilidad
│   ├── enfoque-por-servicio.md  # Beneficios y ángulo de comunicación por servicio
│   ├── promociones-activas.md   # Promociones vigentes (solo datos reales y validados)
│   ├── tono-de-marca.md         # Voz, tono e identidad comunicacional
│   └── mensajes-usados.md       # Registro de copys y frases ya utilizados
│
└── salidas/
    └── semanal/                 # Informes de planificación semanal generados
        └── marketing-semanal-YYYY-MM-DD.md
```

---

## Carpeta `contexto/`

Contiene los archivos que alimentan cada informe semanal. Deben mantenerse actualizados por el equipo de RC Domotic.

| Archivo | Descripción | Quién lo actualiza |
|---|---|---|
| `servicios.md` | Catálogo de servicios reales que ofrece RC Domotic | Equipo técnico / comercial |
| `catalogo-productos.md` | Productos individuales con precio real, disponibilidad y si aplican para promo | Comercial (fuente: Appdomotic) |
| `enfoque-por-servicio.md` | Ángulo de comunicación y beneficios de cada servicio | Marketing |
| `promociones-activas.md` | Promociones vigentes con precio, condiciones y vigencia reales | Comercial (fuente: Appdomotic) |
| `tono-de-marca.md` | Guía de voz, tono y estilo de comunicación | Marketing |
| `mensajes-usados.md` | Registro de copys y frases publicados para evitar repetición | Marketing |

---

## Carpeta `salidas/semanal/`

Contiene los informes de planificación semanal generados. Cada archivo sigue el formato:

```
marketing-semanal-YYYY-MM-DD.md
```

Cada informe incluye:
- Ideas de contenido nuevas
- Copys promocionales
- Ofertas destacadas (o sugerencias si no hay promos activas)
- Revisión de mensajes repetidos
- Enfoque recomendado por servicio
- Prioridad semanal de acciones

---

## Regla crítica: `promociones-activas.md`

> **Este archivo no debe inventarse ni estimarse.**

Solo debe contener promociones confirmadas con:
- Precio o condición real
- Vigencia exacta
- Fuente validada (Appdomotic u acuerdo comercial directo)

Si no hay promociones activas, el archivo debe indicarlo claramente. El informe semanal tomará esa información y propondrá sugerencias de campaña en lugar de promociones reales.

---

## Flujo de trabajo recomendado

```
1. Validar productos y promociones reales en Appdomotic
         ↓
2. Actualizar contexto/promociones-activas.md con datos reales
         ↓
3. Revisar y actualizar los demás archivos de contexto si hubo cambios
         ↓
4. Generar el informe semanal (salidas/semanal/marketing-semanal-YYYY-MM-DD.md)
         ↓
5. Revisar el informe antes de ejecutar cualquier pieza de contenido
```

---

## Flujo real de promociones

Para que el informe semanal contenga promociones reales y no datos inventados, seguir siempre este orden:

```
Paso 1 — Actualizar contexto/catalogo-productos.md
         Revisar Appdomotic y registrar los productos disponibles
         con precio real, disponibilidad y si aplican para promoción.
                  ↓
Paso 2 — Actualizar contexto/promociones-activas.md
         Solo con base en los productos registrados en el catálogo.
         No añadir precios ni condiciones que no estén confirmados.
                  ↓
Paso 3 — Generar el informe semanal
         Con la información validada de los dos archivos anteriores.
                  ↓
Paso 4 — Revisión humana antes de publicar
         El informe es una propuesta. Revisar antes de ejecutar.
```

> Si no hay datos reales suficientes en el catálogo o en promociones-activas.md, el informe debe indicar:
> **"No hay promociones activas esta semana."**
> y proponer sugerencias de campaña pendientes de validar, sin inventar precios ni condiciones.

---

## Importante

- Los informes semanales son propuestas de planificación, no piezas listas para publicar.
- Toda información de precio, promoción o condición comercial debe verificarse antes de comunicarla al cliente.
- Los copys del informe son borradores. Deben revisarse antes de publicarse.
