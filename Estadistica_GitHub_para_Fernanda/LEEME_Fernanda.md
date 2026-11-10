# Incorporar Estadística a reads2mags-v1

Este paquete añade la práctica con datos de Baxter, adaptada a R en Landalab desde VS Code y Remote - SSH. La fuente editable es `repositorio/08.Estadistica.qmd`; el HTML publicado se genera a partir de ella.

## Archivos para el repositorio

Copia **el contenido de `repositorio/` a la raíz de `reads2mags-v1`**, conservando las rutas:

| Ruta | Contenido |
| --- | --- |
| `08.Estadistica.qmd` | Texto, tablas y los 22 bloques visibles de R; fuente para futuras ediciones. |
| `estadistica/estadistica.css` | Estilos de esta sección; hereda el tema general del curso. |
| `estadistica/figuras/` | Siete figuras SVG para ilustrar los resultados del código visible. |
| `estadistica/descargas/Estadistica_insumos.zip` | Datos iniciales para preparar cada cuenta de Landalab. |
| `docs/08.Estadistica.html` | Página ya compilada, con imágenes y estilos incorporados. |
| `docs/estadistica/descargas/Estadistica_insumos.zip` | La misma descarga, lista para GitHub Pages. |

La carpeta `docente/` contiene indicaciones de preparación y verificación; se conserva como material de trabajo docente.

## Incorporar el enlace al menú

En `_quarto.yml`, dentro de `website.navbar.left`, agrega estas tres líneas después de la entrada de `07.Global.qmd`, respetando la sangría:

```yaml
      - href: 08.Estadistica.qmd
        text: Estadística
        icon: bar-chart
```

También se incluye `integracion_menu.patch`, que contiene únicamente esa inserción. Puede aplicarse desde la raíz del repositorio con `git apply /ruta/al/paquete/integracion_menu.patch`. El parche se preparó contra la configuración pública consultada el 9 de noviembre de 2026; si esa zona del menú cambió, agrega las tres líneas directamente.

## Compilar y publicar

Desde la raíz del repositorio, con Quarto disponible:

```bash
quarto render 08.Estadistica.qmd
```

El proyecto actual usa `output-dir: docs`, por lo que la salida queda en `docs/08.Estadistica.html`. Los bloques están escritos como código para leer y copiar, y la página tiene `execute.eval: false`: **publicar esta sección no requiere instalar R ni ejecutar los análisis**. Las figuras de la página están incluidas en el paquete. Los alumnos sí generan sus propias figuras al ejecutar el código.

Para propagar el enlace nuevo al menú de las demás páginas y al buscador, sigue el procedimiento habitual de regeneración del sitio. El HTML incluido permite revisar y publicar directamente esta página mientras tanto. El paquete no contiene un índice de búsqueda que sustituya al del curso.

Incluye en el commit `08.Estadistica.qmd`, `estadistica/`, el cambio del menú y los archivos de publicación generados en `docs/`. Publica mediante el procedimiento habitual de este repositorio.

La dirección prevista, una vez publicada, es:

<https://mariafer-florido.github.io/reads2mags-v1/08.Estadistica.html>

Los bloques del temario correspondientes a estadística pueden enlazar a `08.Estadistica.qmd`. La práctica sigue los horarios del curso: jueves 12, 15:00–15:45 y 16:00–17:00; viernes 13, 9:00–10:00, hora de Ciudad de México.

## Preparar las cuentas de Landalab

La descarga `Estadistica_insumos.zip` contiene la carpeta `08_Estadistica_Baxter` con los datos iniciales, su procedencia, licencia y un breve LEEME. Debe quedar en cada cuenta en:

```text
~/reads2mags_pozol/08_Estadistica_Baxter/datos/practica.rds
```

`~` representa la carpeta personal de la cuenta conectada. No se fija el nombre de usuario en la práctica. Las figuras y los resultados se generan durante el recorrido; no forman parte de los insumos del alumno.

**Orden acordado:** primero probar en la cuenta de Fran, `fjbalvino`; después preparar las cuentas de los alumnos con cada alumno como dueño de su carpeta. Si Fran recibe otra cuenta, se conserva exactamente la misma ruta relativa a `~`. La prueba en Landalab sigue pendiente: haber generado el HTML no verifica los paquetes instalados en ese servidor.

Consulta `docente/PRUEBA_EN_LANDALAB.md` para esa comprobación.

## Validación incluida

Se compiló la fuente con Quarto y se extrajeron los 22 bloques del HTML generado. Los bloques coinciden con los de la fuente y se ejecutaron en una sesión limpia de R sin pantalla gráfica, partiendo únicamente de `datos/practica.rds`. Se generaron siete PNG y la tabla final, con los resultados previstos. Los detalles de versión están en `docente/VALIDACION.md`.

Referencias de integración: [repositorio del curso](https://github.com/mariafer-florido/reads2mags-v1), [opciones de ejecución de Quarto](https://quarto.org/docs/computations/execution-options.html) y [HTML autocontenido](https://quarto.org/docs/output-formats/html-basics.html#self-contained).
