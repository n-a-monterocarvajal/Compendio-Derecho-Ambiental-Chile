# 🌱 Compendio Normas Ambientales Chile

Este repositorio genera semanalmente, mediante GitHub Actions, un compendio PDF de normas ambientales chilenas disponibles en LeyChile. El archivo resultante queda disponible como *artifact* de la ejecución por 30 días.

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

## 📄 PDF generado

El *workflow* produce un archivo PDF con nombre versionado por fecha y hora UTC:

```text
CompendioNormasAmbientalesChile_YYYYMMDD_HHMM_UTC.pdf
```

## 📥 Descarga del compendio

El último compendio generado y el histórico reciente se encuentran en la página del *workflow*:

[Ver ejecuciones y *artifacts* del compendio](https://github.com/n-a-monterocarvajal/CompendioNormasAmbientalesChile/actions/workflows/generar-compendio.yml)

Para descargar el PDF más reciente:

1. abrir el enlace anterior;
2. entrar en la ejecución exitosa más reciente;
3. bajar hasta la sección ***Artifacts***;
4. descargar el *artifact* `CompendioNormasAmbientalesChile`.

El histórico disponible corresponde a las ejecuciones de GitHub Actions. Los *artifacts* se eliminan automáticamente después de 30 días.

## 🔐 Licencia

El código de este repositorio se publica bajo licencia MIT. Las normas descargadas pertenecen a sus respectivas fuentes oficiales y se obtienen desde sitios públicos al momento de cada ejecución.
