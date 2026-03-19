# Checklist Heurístico — Instagram (iOS)

## Tabla resumen por heurística

| # | Heurística | Cumplimiento | Severidad |
|---|-----------|-------------|-----------|
| H1 | Visibilidad del estado del sistema | Cumple parcialmente | 2 |
| H2 | Coincidencia con el mundo real | Cumple parcialmente | 1 |
| H3 | Control y libertad del usuario | No cumple | 3 |
| H4 | Consistencia y estándares | No cumple | 3 |
| H5 | Prevención de errores | Cumple parcialmente | 2 |
| H6 | Reconocimiento antes que recuerdo | Cumple parcialmente | 2 |
| H7 | Flexibilidad y eficiencia de uso | Cumple parcialmente | 2 |
| H8 | Diseño estético y minimalista | No cumple | 3 |
| H9 | Ayuda a reconocer y recuperarse de errores | Cumple parcialmente | 2 |
| H10 | Ayuda y documentación | No cumple | 2 |

## Hallazgos detallados

### H1-A — Carga del feed sin indicador de progreso
- **Heurística violada:** H1 - Visibilidad del estado del sistema
- **Pantalla/Contexto:** Pantalla principal (Home) al abrir la app
- **Descripción:** Al abrir Instagram con conexión lenta, el feed aparece
  en blanco sin ningún spinner ni mensaje de carga. El usuario no sabe si
  la app está cargando o se congeló, lo que genera frustración y cierres
  innecesarios de la app.
- **Evidencia:** `evidencias/flujoA_login.png`
- **Severidad tentativa:** 2

### H2-B — Ícono de Explorar no representa su función real
- **Heurística violada:** H2 - Coincidencia entre el sistema y el mundo real
- **Pantalla/Contexto:** Barra de navegación inferior, pestaña Explorar
- **Descripción:** El ícono de la lupa representa la sección Explorar, pero
  esta sección no solo busca sino que muestra contenido sugerido
  algorítmicamente. El ícono no refleja el concepto real de la función,
  confundiendo a usuarios nuevos que esperan una búsqueda simple.
- **Evidencia:** `evidencias/flujoB_barra_navegacion.png`
- **Severidad tentativa:** 1

### H3-A — Sin salida de emergencia en el registro
- **Heurística violada:** H3 - Control y libertad del usuario
- **Pantalla/Contexto:** Flujo de registro, paso de verificación por SMS
- **Descripción:** Durante el onboarding, una vez que el usuario ingresa su
  número de teléfono y avanza al paso de verificación por SMS, no existe
  un botón claro de "Cancelar" o "Volver al inicio". El usuario queda
  atrapado en el flujo sin salida de emergencia evidente.
- **Evidencia:** `evidencias/flujoA_verificacion_sms.png`
- **Severidad tentativa:** 3

### H4-B — Botones de acción inconsistentes entre Reels y Posts
- **Heurística violada:** H4 - Consistencia y estándares
- **Pantalla/Contexto:** Visualización de Reels vs Posts en Explorar
- **Descripción:** En los posts normales, los botones de Like, Comentar y
  Compartir están debajo del contenido. En los Reels están al lado derecho
  superpuestos sobre el video. Esta inconsistencia obliga al usuario a
  reaprender la ubicación de acciones idénticas según el tipo de contenido.
- **Evidencia:** `evidencias/flujoB_reel.png`
- **Severidad tentativa:** 3

### H4-C — Iconos de edición en Stories sin etiquetas
- **Heurística violada:** H4 - Consistencia y estándares
- **Pantalla/Contexto:** Pantalla de edición al crear una Story
- **Descripción:** La barra de herramientas de edición de Stories muestra
  únicamente íconos sin texto descriptivo. Su significado no es
  autoexplicativo para usuarios nuevos y varía respecto a otras apps
  similares como TikTok o Snapchat.
- **Evidencia:** `evidencias/flujoC_edicion_story.png`
- **Severidad tentativa:** 3

### H5-A — Formulario permite avanzar con email inválido
- **Heurística violada:** H5 - Prevención de errores
- **Pantalla/Contexto:** Formulario de registro, campo de correo electrónico
- **Descripción:** Al escribir un email con formato incorrecto, el botón
  "Siguiente" permanece activo y el error solo se muestra después de
  intentar avanzar. Una validación en tiempo real evitaría que el usuario
  cometa este error.
- **Evidencia:** `evidencias/flujoA_registro.png`
- **Severidad tentativa:** 2

### H6-C — Opciones de privacidad de Story ocultas
- **Heurística violada:** H6 - Reconocimiento antes que recuerdo
- **Pantalla/Contexto:** Pantalla de confirmación antes de publicar Story
- **Descripción:** Opciones como "Ocultar historia a..." están en un menú
  que no tiene señal visual que indique su existencia. El usuario debe
  recordar que existen estas opciones ya que no hay ningún texto ni ícono
  que las sugiera.
- **Evidencia:** `evidencias/flujoC_opciones_publicar.png`
- **Severidad tentativa:** 2

### H7-B — Filtros de búsqueda desaparecen al hacer scroll
- **Heurística violada:** H7 - Flexibilidad y eficiencia de uso
- **Pantalla/Contexto:** Sección Explorar, resultados de búsqueda
- **Descripción:** Al buscar un término, los filtros disponibles desaparecen
  si el usuario hace scroll hacia abajo. No hay forma de fijar un filtro
  activo, obligando al usuario a repetir la selección en cada búsqueda.
- **Evidencia:** `evidencias/flujoB_explorar.png`
- **Severidad tentativa:** 2

### H8-B — Pantalla Explorar sobrecargada visualmente
- **Heurística violada:** H8 - Diseño estético y minimalista
- **Pantalla/Contexto:** Pantalla principal de la sección Explorar
- **Descripción:** La cuadrícula de Explorar mezcla fotos de diferentes
  tamaños, videos con reproducción automática y Reels sin jerarquía visual
  clara. La densidad de información y el movimiento simultáneo de múltiples
  videos genera sobrecarga cognitiva.
- **Evidencia:** `evidencias/flujoB_explorar.png`
- **Severidad tentativa:** 3

### H9-C — Mensaje de error genérico al fallar publicación de Story
- **Heurística violada:** H9 - Ayuda a reconocer, diagnosticar y recuperarse de errores
- **Pantalla/Contexto:** Publicación de Story con conexión inestable
- **Descripción:** Cuando la publicación falla, el mensaje es