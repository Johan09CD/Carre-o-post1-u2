# Reporte de Auditoría Heurística — Instagram (iOS)

**Estudiante:** Johan Carreño
**App evaluada:** Instagram
**Versión:** Versión 421.1.0
**Plataforma:** iOS

## 1. Resumen Ejecutivo
Se realizó una auditoría heurística de usabilidad sobre Instagram (iOS) aplicando las 10 heurísticas de Nielsen. La evaluación cubrió tres flujos críticos: el registro y onboarding de nuevos usuarios, la búsqueda y exploración de contenido, y la publicación de historias (Stories). Se identificaron 10 hallazgos distribuidos entre los tres flujos, cubriendo 7 de las 10 heurísticas evaluadas. El hallazgo más crítico corresponde a la ausencia de una salida de emergencia durante el flujo de registro (H3-A, severidad 3), que puede generar abandono permanente del proceso de incorporación. La recomendación principal es incorporar un botón de cancelación explícito en todos los pasos del onboarding, y estandarizar la ubicación de los botones de acción entre los diferentes tipos de contenido (posts y Reels) para reducir la carga cognitiva del usuario.

## 2. Metodología
La evaluación se realizó siguiendo el método de inspección heurística propuesto por Jakob Nielsen. Cada flujo fue recorrido dos veces: la primera como usuario normal para capturar la experiencia natural, y la segunda con inspección activa pantalla a pantalla contrastando contra la lista de las 10 heurísticas. Las herramientas utilizadas fueron: iPhone con iOS, función nativa de captura de pantalla del sistema, y VS Code para la documentación en Markdown. El alcance evaluado incluyó tres flujos: Flujo A (registro/onboarding), Flujo B (búsqueda y exploración), y Flujo C (publicación de Stories). No se evaluaron funciones de mensajería directa ni configuración avanzada de cuenta.

## 3. Hallazgos por Flujo

### Flujo A: Registro y Onboarding

**H1-A** — Al abrir la app con conexión lenta, el feed carga sin ningún indicador de progreso visible.
*(Evidencia: evidencias/flujoA_login.png)*

**H3-A** — Durante la verificación por SMS en el registro, no existe botón de cancelar ni salida de emergencia clara.
*(Evidencia: evidencias/flujoA_verificacion_sms.png)*

**H5-A** — El formulario permite avanzar con un email de formato inválido; el error solo aparece después de intentar continuar.
*(Evidencia: evidencias/flujoA_registro.png)*

### Flujo B: Búsqueda y Exploración

**H2-B** — El ícono de lupa representa una sección que no es solo búsqueda sino exploración algorítmica, lo que confunde la expectativa del usuario.
*(Evidencia: evidencias/flujoB_barra_navegacion.png)*

**H4-B** — Los botones de Like, Comentar y Compartir tienen posición diferente en posts vs Reels, rompiendo la consistencia de la interfaz.
*(Evidencia: evidencias/flujoB_reel.png)*

**H7-B** — Los filtros de búsqueda desaparecen al hacer scroll, eliminando la eficiencia para usuarios avanzados.
*(Evidencia: evidencias/flujoB_explorar.png)*

**H8-B** — La pantalla Explorar mezcla contenidos de distintos tamaños y videos con reproducción automática generando sobrecarga visual.
*(Evidencia: evidencias/flujoB_explorar.png)*

### Flujo C: Publicación de Story

**H4-C** — Los íconos de edición de Stories carecen de etiquetas, dificultando su uso para usuarios nuevos.
*(Evidencia: evidencias/flujoC_edicion_story.png)*

**H6-C** — Las opciones avanzadas de privacidad de la Story están ocultas sin ninguna señal visual que indique su existencia.
*(Evidencia: evidencias/flujoC_opciones_publicar.png)*

**H9-C** — El mensaje de error al fallar la publicación es genérico y no informa si el contenido se conservó.
*(Evidencia: evidencias/flujoC_opciones_publicar.png)*

## 4. Tabla de Priorización Consolidada

| Prioridad | ID | Heurística | Severidad | Impacto en usuario | Recomendación |
|-----------|-----|-----------|-----------|-------------------|---------------|
| 1 | H3-A | Control y libertad | 3 | El usuario queda atrapado en el registro sin poder salir fácilmente, generando abandono. | Agregar botón "Cancelar registro" visible en todos los pasos del onboarding. |
| 2 | H4-B | Consistencia y estándares | 3 | El usuario debe reaprender la ubicación de acciones según el tipo de contenido. | Unificar posición de botones de acción en posts y Reels. |
| 3 | H4-C | Consistencia y estándares | 3 | Usuarios nuevos no comprenden las herramientas de edición de Stories. | Agregar etiquetas de texto bajo cada ícono de la barra de edición. |
| 4 | H8-B | Diseño minimalista | 3 | La sobrecarga visual en Explorar dificulta enfocar la atención y genera fatiga. | Limitar reproducción automática a un video a la vez y estandarizar tamaños. |
| 5 | H1-A | Visibilidad del estado | 2 | El usuario no sabe si la app está cargando o congelada. | Implementar skeleton screens o spinner durante la carga del feed. |
| 6 | H5-A | Prevención de errores | 2 | El usuario descubre el error de email solo después de intentar avanzar. | Activar validación de formato de email en tiempo real. |
| 7 | H6-C | Reconocimiento antes que recuerdo | 2 | El usuario desconoce la existencia de opciones de privacidad de Stories. | Mostrar tooltip visible en la pantalla de configuración previa a publicar. |
| 8 | H7-B | Flexibilidad y eficiencia | 2 | Usuarios avanzados deben reseleccionar filtros repetidamente al hacer scroll. | Fijar el filtro activo en la parte superior aunque el usuario haga scroll. |
| 9 | H9-C | Recuperación ante errores | 2 | El usuario no sabe si perdió su Story editada al fallar la publicación. | Mejorar mensaje de error indicando si el borrador fue guardado. |
| 10 | H2-B | Coincidencia mundo real | 1 | Usuarios nuevos esperan solo búsqueda al ver la lupa, no contenido sugerido. | Agregar label "Explorar" bajo el ícono en la barra de navegación. |

## 5. Análisis de Patrones

**Patrón 1 — Inconsistencia sistemática en la interfaz (H4)**
La heurística H4 (Consistencia y estándares) es violada en dos flujos diferentes (Flujo B y Flujo C) con dos manifestaciones distintas: la posición variable de los botones de acción según el tipo de contenido, y la ausencia de etiquetas en los íconos de edición. Esto sugiere que Instagram prioriza la diferenciación visual entre formatos de contenido sobre la coherencia de la interfaz, generando una curva de aprendizaje innecesaria para el usuario.

**Patrón 2 — Funciones ocultas sin señalización (H6 y H7)**
Tanto las opciones avanzadas de Stories (H6-C) como los filtros de búsqueda que desaparecen (H7-B) responden al mismo patrón: la app oculta funcionalidad útil para mantener una apariencia limpia, pero sin proveer al usuario señales de que esa funcionalidad existe. Esto penaliza especialmente a usuarios intermedios que podrían aprovechar estas funciones si supieran que están disponibles.

## 6. Conclusiones
Instagram presenta una usabilidad general aceptable para usuarios frecuentes, pero muestra debilidades significativas en tres áreas: la consistencia visual entre formatos de contenido, la comunicación del estado del sistema durante cargas y errores, y la visibilidad de funciones avanzadas. Los hallazgos de mayor severidad (3) se concentran en inconsistencias de interfaz que afectan a todos los perfiles de usuario.

Las recomendaciones prioritarias son: estandarizar la posición de los controles de interacción en todos los formatos de contenido, incorporar indicadores de carga en momentos de espera, y añadir etiquetas de texto a los íconos de la barra de edición de Stories. Estas tres correcciones impactarían positivamente la experiencia de usuarios nuevos e intermedios sin alterar la experiencia de usuarios avanzados.