# Primera prueba en Landalab

La primera comprobación se hará en la cuenta `fjbalvino`. Después de verificar el recorrido completo, se prepararán las cuentas de los alumnos. Los comandos utilizan `~` y sirven también si cambia la cuenta asignada.

## 1. Colocar los datos iniciales

La carpeta de trabajo ya creada en la cuenta de Fran es `~/reads2mags_pozol/08_Estadistica_Baxter`.

Extraer `Estadistica_insumos.zip` y colocar el contenido de su carpeta `08_Estadistica_Baxter` dentro de esa carpeta de trabajo. La ubicación final debe ser:

```text
~/reads2mags_pozol/08_Estadistica_Baxter/datos/practica.rds
```

Conservar junto al RDS `procedencia.csv` y `LICENSE_Baxter.md`. Evitar crear una segunda carpeta `08_Estadistica_Baxter` anidada dentro de la primera.

## 2. Revisar el entorno

En la terminal de la ventana de VS Code conectada por SSH:

```bash
whoami
cd ~/reads2mags_pozol/08_Estadistica_Baxter
ls datos
command -v R
```

Para esta primera prueba, `whoami` debe mostrar `fjbalvino`. Si `command -v R` no devuelve una ruta, averiguar qué entorno de R usa Landalab antes de instalar nada: R puede estar disponible mediante un entorno que todavía no esté activado.

Iniciar R:

```bash
R --vanilla
```

En la consola de R, después del símbolo `>`:

```r
R.version.string
paquetes <- c("vegan", "ggplot2", "sandwich", "lmtest", "permute", "scales")
sapply(paquetes, requireNamespace, quietly = TRUE)
capabilities(c("png", "cairo"))
getOption("bitmapType")
file.exists("datos/practica.rds")
```

Todos los paquetes y el archivo deben estar disponibles. Confirmar un dispositivo PNG que funcione sin pantalla, preferentemente Cairo; la prueba efectiva es guardar y abrir la primera figura. Estas consultas no instalan paquetes ni cambian el entorno.

## 3. Seguir el HTML

Ejecutar en orden los bloques 01–22 de `08.Estadistica.html`. Guardarlos en `mi_practica.R` y abrir cada PNG desde el explorador de VS Code. La práctica no depende de una extensión de R para VS Code ni de RStudio.

Comprobar:

- Los conteos tienen 122 filas y 5323 columnas, y la rarefacción deja 10.000 lecturas por persona.
- Se generan siete imágenes en `figuras/` y todas se abren.
- `resultados/resultados_globales.csv` contiene p de Holm aproximadamente 0,214 para Shannon y 0,534 para composición, con las versiones y semillas documentadas.
- `resultados/versiones_R.txt` registra el entorno real de Landalab. Si cambia algún resultado, compararlo con las versiones documentadas antes de distribuir.

## 4. Preparación del resto de cuentas

Después de completar esta prueba, copiar únicamente la carpeta de insumos iniciales a `~/reads2mags_pozol/08_Estadistica_Baxter` de cada alumno. Cada cuenta debe ser dueña de su copia y poder crear allí `mi_practica.R`, `figuras/` y `resultados/`.

Los resultados que Fran produzca al probar la práctica permanecen en su cuenta; el paquete inicial de los alumnos sigue conteniendo solo los datos y la documentación de procedencia.
