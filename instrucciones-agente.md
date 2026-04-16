# Instrucciones para el agente de marketing — RC Domotic

Este archivo es la referencia definitiva que el agente debe leer antes de ejecutar cualquier tarea semanal. Tiene prioridad sobre cualquier instrucción genérica.

---

## Flujo obligatorio de ejecución semanal

El agente DEBE seguir este orden sin excepción. No generar ningún informe antes de completar los pasos anteriores.

---

### PASO 1 — Buscar fuente real del catálogo

Buscar una exportación reciente del inventario en este orden de prioridad:

1. `exports/Inventario.pdf`
2. `exports/` (cualquier archivo .pdf, .csv, .xlsx o .json)
3. `contexto/` (cualquier exportación adjunta)
4. Raíz del repositorio (cualquier archivo de inventario)

**Si se encuentra una fuente:**
- Confirmar la fecha de exportación antes de continuar
- Leer todos los productos disponibles
- Continuar con el PASO 2

**Si no se encuentra ninguna fuente:**
- Detener la ejecución completamente
- Informar al usuario: "No encontré una exportación real del catálogo. Por favor sube Inventario.pdf a la carpeta exports/ y vuelve a ejecutar."
- No generar informe ni actualizar archivos

---

### PASO 2 — Actualizar `contexto/catalogo-productos.md`

Extraer de la fuente encontrada:

| Campo | Instrucción |
|---|---|
| **ID** | Usar el ID exacto del sistema (ej. CAM-001, DOM-014) |
| **Nombre** | Usar el nombre exacto tal como aparece en la fuente |
| **Categoría** | Usar la categoría de la fuente (AUDIOVISUAL, CCTV, CERRADURAS, DOMOTICA, OTROS, REDES, SERVICIOS) |
| **Precio** | Usar el precio exacto en COP. Si el precio es $0, escribir: `Por validar` |

**Reglas permanentes para este paso:**
- No inventar productos que no estén en la fuente
- No inventar ni estimar precios
- No descartar productos porque el stock aparezca en 0
- No añadir beneficios o descripciones que no aparezcan en la fuente
- Registrar el total de productos leídos antes de continuar

---

### PASO 3 — Actualizar `contexto/promociones-activas.md`

Revisar si la fuente contiene:
- Precios promocionales o con descuento
- Condiciones especiales de venta
- Vigencias o campañas activas

**Si NO hay promociones reales en la fuente:**
Escribir exactamente esta frase, sin modificaciones:

> **No hay promociones activas esta semana.**

Y mantener el formato de plantilla para registro futuro.

**Si SÍ hay promociones reales en la fuente:**
Registrar solo con datos confirmados: nombre, precio real, vigencia, condiciones y fuente. Nunca estimar ni completar campos con datos aproximados.

---

### PASO 4 — Generar el informe semanal

Ruta del archivo: `salidas/semanal/marketing-semanal-YYYY-MM-DD.md`

El informe debe generarse usando únicamente:
- Productos de `contexto/catalogo-productos.md` ya actualizado en el PASO 2
- Estado real de `contexto/promociones-activas.md` actualizado en el PASO 3
- Contexto de `contexto/servicios.md`, `enfoque-por-servicio.md`, `tono-de-marca.md` y `mensajes-usados.md`

**Reglas para el informe:**
- Las ideas de contenido pueden referenciar productos reales por ID y nombre
- Los copys no deben incluir precios
- Si no hay promociones activas, la sección de ofertas debe indicarlo claramente y proponer solo **sugerencias comerciales** marcadas como pendientes de validación
- Las sugerencias comerciales deben referenciar productos reales del catálogo
- Ninguna sugerencia puede incluir precios, descuentos ni condiciones inventadas
- Verificar que ningún copy repita frases registradas en `mensajes-usados.md`

---

## Reglas permanentes (no negociables)

| Regla | Descripción |
|---|---|
| Sin productos inventados | Solo productos que aparezcan en la fuente real |
| Sin precios inventados | Solo precios extraídos literalmente de la fuente |
| Sin promociones inventadas | Solo promociones con precio, vigencia y condición reales confirmados |
| Sin descuentos inventados | No añadir porcentajes ni condiciones especiales sin respaldo |
| Sin beneficios no verificables | No atribuir características técnicas que no aparezcan en la fuente |
| Stock 0 no descarta producto | El stock en 0 en la exportación no significa que el producto no esté disponible |
| Sugerencias ≠ Promociones | Las campañas propuestas sin confirmación son sugerencias, nunca promociones activas |

---

## Estructura de carpetas esperada

```
rcdomotic-marketing/
├── exports/                     # Fuentes reales del catálogo (Inventario.pdf, etc.)
├── contexto/
│   ├── servicios.md
│   ├── catalogo-productos.md    # Se actualiza en PASO 2
│   ├── enfoque-por-servicio.md
│   ├── promociones-activas.md   # Se actualiza en PASO 3
│   ├── tono-de-marca.md
│   └── mensajes-usados.md
└── salidas/
    └── semanal/
        └── marketing-semanal-YYYY-MM-DD.md   # Se genera en PASO 4
```

---

## Nota sobre Inventario.pdf

Si el archivo `Inventario.pdf` aparece en la raíz del repositorio en lugar de en `exports/`, recomendarlo al usuario pero no bloquearse por ello: usar el archivo donde esté y procesar el flujo normalmente. Al finalizar, indicar al usuario que conviene moverlo a `exports/` para mantener el orden.

---

## Cuándo NO ejecutar el flujo

- Si no existe ninguna fuente de catálogo real
- Si la fuente encontrada tiene fecha anterior a la semana activa y no hay confirmación de que sigue vigente
- Si el usuario pide explícitamente detenerse antes de algún paso
