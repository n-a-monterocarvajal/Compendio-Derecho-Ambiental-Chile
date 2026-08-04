# Compendio Normas Ambientales Chile

Este repositorio genera semanalmente, mediante GitHub Actions, un compendio PDF de normas ambientales chilenas disponibles en LeyChile. El archivo resultante queda disponible como artifact de la ejecución por 30 días.

El proyecto tiene vocación pública: no contiene datos personales, credenciales ni insumos privados. Las normas se obtienen desde fuentes públicas de la Biblioteca del Congreso Nacional de Chile, base LeyChile.

## PDF generado

El workflow produce un archivo PDF con nombre versionado por fecha y hora UTC:

```text
CompendioNormasAmbientalesChile_YYYYMMDD_HHMM_UTC.pdf
```

Por ejemplo:

```text
CompendioNormasAmbientalesChile_20260804_2033_UTC.pdf
```

El PDF se publica como artifact de GitHub Actions con retención de 30 días.

## Descarga del compendio

El último compendio generado y el histórico reciente se encuentran en la página del workflow:

[Ver ejecuciones y artifacts del compendio](https://github.com/n-a-monterocarvajal/CompendioNormasAmbientalesChile/actions/workflows/generar-compendio.yml)

Para descargar el PDF más reciente:

1. abrir el enlace anterior;
2. entrar en la ejecución exitosa más reciente;
3. bajar hasta la sección **Artifacts**;
4. descargar el artifact `CompendioNormasAmbientalesChile`.

El histórico disponible corresponde a las ejecuciones de GitHub Actions. Los artifacts se eliminan automáticamente después de 30 días.

## Ejecución

El workflow se ejecuta automáticamente una vez por semana y también puede ejecutarse manualmente desde la pestaña **Actions** de GitHub.

Flujo general:

1. prepara Python;
2. instala dependencias;
3. instala Chromium mediante Playwright;
4. descarga las normas configuradas en `app/fuentes.json`;
5. une los PDFs;
6. crea marcadores de navegación;
7. sube el compendio como artifact.

## Normas incluidas

1. Ley N.º 19.300 — Bases Generales del Medio Ambiente.
2. Decreto Supremo N.º 40, de 2012 — Reglamento del Sistema de Evaluación de Impacto Ambiental.
3. Ley N.º 21.770 — Ley Marco de Autorizaciones Sectoriales.
4. Decreto Supremo N.º 32, de 2015 — Reglamento para la Evaluación Ambiental Estratégica.
5. Ley N.º 20.417 — Ministerio, Servicio de Evaluación Ambiental y Superintendencia del Medio Ambiente.
6. Ley N.º 20.600 — Tribunales Ambientales.
7. Ley N.º 21.600 — Servicio de Biodiversidad y Áreas Protegidas.
8. Ley N.º 21.202 — Protección de Humedales Urbanos.
9. Decreto Supremo N.º 15, de 2020 — Reglamento de Humedales Urbanos.
10. Ley N.º 20.920 — Gestión de Residuos y Responsabilidad Extendida del Productor.
11. Ley N.º 21.455 — Ley Marco de Cambio Climático.

## Estructura

```text
.github/workflows/generar-compendio.yml
app/CompendioNormativo.py
app/fuentes.json
app/requirements.txt
.gitignore
LICENSE
README.md
```

## Configuración

Las fuentes se editan en:

```text
app/fuentes.json
```

El campo `salida_base` define el prefijo del nombre del PDF. El script agrega automáticamente la fecha y hora de generación en UTC.

Cada fuente usa una URL pública de LeyChile con su correspondiente `idNorma`.

## Diagnóstico

Si la generación falla, el workflow sube un artifact de diagnóstico con el log y, cuando existan, archivos HTML o capturas de depuración generados durante la navegación.

## Licencia

El código de este repositorio se publica bajo licencia MIT. Las normas descargadas pertenecen a sus respectivas fuentes oficiales y se obtienen desde sitios públicos al momento de cada ejecución.
