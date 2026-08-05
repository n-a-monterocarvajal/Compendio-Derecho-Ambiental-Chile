# 🌱 Compendio de normas de Derecho Ambiental chileno

[![Última versión](https://img.shields.io/github/v/release/n-a-monterocarvajal/Compendio-Derecho-Ambiental-Chile?sort=date&display_name=tag&label=%C3%BAltima%20versi%C3%B3n)](https://github.com/n-a-monterocarvajal/Compendio-Derecho-Ambiental-Chile/releases/latest)
[![Revisión semanal](https://github.com/n-a-monterocarvajal/Compendio-Derecho-Ambiental-Chile/actions/workflows/revisar-versiones.yml/badge.svg?branch=main)](https://github.com/n-a-monterocarvajal/Compendio-Derecho-Ambiental-Chile/actions/workflows/revisar-versiones.yml)
[![Generación](https://github.com/n-a-monterocarvajal/Compendio-Derecho-Ambiental-Chile/actions/workflows/generar-compendio.yml/badge.svg?branch=main)](https://github.com/n-a-monterocarvajal/Compendio-Derecho-Ambiental-Chile/actions/workflows/generar-compendio.yml)
[![Licencia: MIT](https://img.shields.io/github/license/n-a-monterocarvajal/Compendio-Derecho-Ambiental-Chile?label=licencia)](https://github.com/n-a-monterocarvajal/Compendio-Derecho-Ambiental-Chile/blob/main/LICENSE)

Genera y actualiza automáticamente un compendio en PDF de normas ambientales chilenas obtenidas desde el servicio Ley Chile, de la Biblioteca del Congreso Nacional de Chile.

Este repositorio revisa semanalmente las versiones de sus normas y genera un nuevo compendio PDF solo cuando detecta una actualización.

## 📚 Normas incluidas

1. [Ley N.º 19.300, que aprueba Ley sobre Bases Generales del Medio Ambiente.](https://www.bcn.cl/leychile/navegar?idNorma=30667)
2. [Decreto Supremo N.º 40, de 2012, del Ministerio del Medio Ambiente, que aprueba Reglamento del Sistema de Evaluación de Impacto Ambiental.](https://www.bcn.cl/leychile/navegar?idNorma=1053563)
3. [Ley N.º 21.770, que establece una Ley Marco de Autorizaciones Sectoriales e introduce modificaciones a los cuerpos legales que indica.](https://www.bcn.cl/leychile/navegar?idNorma=1216930)
4. [Decreto Supremo N.º 32, de 2015, del Ministerio del Medio Ambiente, que aprueba Reglamento para la Evaluación Ambiental Estratégica.](https://www.bcn.cl/leychile/navegar?idNorma=1083574)
5. [Ley N.º 20.417, que crea el Ministerio, el Servicio de Evaluación Ambiental y la Superintendencia del Medio Ambiente.](https://www.bcn.cl/leychile/navegar?idNorma=1010459)
6. [Ley N.º 20.600, que crea los Tribunales Ambientales.](https://www.bcn.cl/leychile/navegar?idNorma=1041361)
7. [Ley N.º 21.600, que crea el Servicio de Biodiversidad y Áreas Protegidas y el Sistema Nacional de Áreas Protegidas.](https://www.bcn.cl/leychile/navegar?idNorma=1195666)
8. [Ley N.º 21.202, que modifica diversos cuerpos legales con el objetivo de proteger los humedales urbanos.](https://www.bcn.cl/leychile/navegar?idNorma=1141461)
9. [Decreto Supremo N.º 15, de 2020, del Ministerio del Medio Ambiente, que establece Reglamento de la Ley N.º 21.202, que modifica diversos cuerpos legales con el objetivo de proteger los humedales urbanos.](https://www.bcn.cl/leychile/navegar?idNorma=1152029)
10. [Ley N.º 20.920, que establece marco para la gestión de residuos, la responsabilidad extendida del productor y fomento al reciclaje.](https://www.bcn.cl/leychile/navegar?idNorma=1090894)
11. [Ley N.º 21.455, Ley Marco de Cambio Climático.](https://www.bcn.cl/leychile/navegar?idNorma=1177286)

*La selección de las normas está basada en el índice de la publicación [Compendio de Normas Ambientales de Chile (Tirant lo Blanch)](https://editorial.tirant.com/cl/libro/compendio-de-normas-ambientales-de-chile-pavez-torrealba-felipe-ignacio-9791370402808).*

## 📄 PDF generado

El *workflow* produce un archivo PDF con nombre versionado por fecha y hora UTC:

```text
CompendioDerechoAmbientalChile_YYYYMMDD_HHMM_UTC.pdf
```

## 📥 Descarga del compendio

La versión más reciente del compendio se publica como *release* del repositorio:

[Descargar última versión publicada del compendio](https://github.com/n-a-monterocarvajal/Compendio-Derecho-Ambiental-Chile/releases/latest)

El historial de versiones anteriores se encuentra disponible en la sección de *releases* del repositorio.

Cada publicación nueva incluye un archivo `.sha256`, una certificación de procedencia de GitHub y un enlace al *run* que produjo el PDF. Las notas del *release* contienen el comando exacto para verificar la certificación. Las publicaciones futuras son inmutables: una corrección siempre origina una versión nueva.

Los *artifacts* del PDF y su *checksum* se mantienen adicionalmente como respaldo temporal durante 30 días.

## 🔄 Actualización automática

El estado normalizado de las versiones se compara semanalmente con la información vigente de Ley Chile. Una nueva vigencia, un cambio de versión actual, un evento pendiente o una modificación de las alertas de texto diferido dispara una ejecución separada del generador. Las notas del *release* indican qué normas cambiaron.

El obtenedor, el ensamblador PDF, el monitor de versiones y sus decisiones técnicas se mantienen en [GeneradorCompendiosLeyChile](https://github.com/n-a-monterocarvajal/GeneradorCompendiosLeyChile). Este repositorio fija una revisión inmutable de ese motor para que sus actualizaciones sean explícitas y auditables.

## 🔐 Licencia

El código de este repositorio se publica bajo licencia MIT. Las normas descargadas pertenecen a sus respectivas fuentes oficiales y se obtienen desde sitios públicos al momento de cada ejecución.
