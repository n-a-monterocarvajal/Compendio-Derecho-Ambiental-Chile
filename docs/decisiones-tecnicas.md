# Decisiones técnicas sobre robustez de las descargas

## Contexto

Durante una ejecución manual se produjo un fallo no determinista al intentar descargar una de las normas desde LeyChile. Una ejecución posterior, realizada sin modificar el código, finalizó correctamente.

Este comportamiento sugiere una variación temporal del sitio de origen, de la sesión de navegación o de la respuesta entregada al ejecutor de GitHub Actions. Por ahora no existe evidencia suficiente para atribuir el fallo a una norma específica ni a una modificación reciente del proyecto.

## Mejoras futuras posibles

### Reinicio periódico del contexto de Chromium

Actualmente las normas se descargan dentro de una misma sesión de Chromium.

Una mejora futura podría consistir en:

- cerrar y crear un nuevo contexto después de cierto número de normas;
- limpiar el estado temporal entre grupos de descargas;
- conservar únicamente la información de sesión que resulte indispensable;
- reanudar el proceso desde la norma siguiente sin repetir las descargas ya validadas.

Esta alternativa podría reducir fallos relacionados con cookies, estado acumulado, sesiones prolongadas o variaciones de la interfaz después de múltiples solicitudes consecutivas.

**Estado:** documentada, no implementada.

### Reintentos inteligentes dentro del descargador

Otra mejora futura podría incorporar reintentos específicos por norma dentro del script Python.

El flujo propuesto sería:

1. intentar la descarga normal;
2. si falla, conservar el diagnóstico del primer intento;
3. esperar un intervalo breve y variable;
4. recargar la página o crear una sesión nueva;
5. volver a buscar el enlace real de exportación;
6. intentar después la vía alternativa mediante el cuadro de descarga;
7. declarar el fallo definitivo solo después de agotar los intentos configurados.

El reintento debería aplicarse únicamente a errores plausiblemente transitorios. Los errores de configuración, validación del PDF o estructura de datos deberían seguir fallando de inmediato.

**Estado:** documentada, no implementada.

## Medida operativa adoptada

Mientras los fallos continúen siendo eventuales y difícilmente reproducibles, GitHub Actions realiza un segundo intento completo una hora después del primero cuando la generación inicial falla.

Esta medida no modifica todavía la lógica de descarga ni la sesión de Chromium. Su finalidad es absorber fallos temporales del sitio de origen sin ocultar errores persistentes: si ambos intentos fallan, la ejecución termina con error y publica el diagnóstico disponible.
