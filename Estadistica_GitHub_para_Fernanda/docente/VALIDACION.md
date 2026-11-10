# Verificación de la entrega

Fecha: 9 de noviembre de 2026, UTC.

La prueba se realizó en un entorno Linux de preparación, **no en Landalab**. La verificación con la cuenta `fjbalvino` es el siguiente paso acordado.

- Fuente editable: `repositorio/08.Estadistica.qmd`.
- Compilación de la página: Quarto 1.11.9, con la configuración y el tema del repositorio público del curso.
- Los 22 bloques R extraídos del HTML generado coinciden exactamente con los de la fuente y con el flujo previamente comprobado.
- Ejecución desde una sesión limpia, sin `DISPLAY`, con únicamente `datos/practica.rds` como entrada analítica.
- Siete archivos PNG generados y decodificados correctamente; tabla final y registro de versiones generados.
- Datos iniciales sin cambios; imágenes de referencia extraídas de la versión previa de la práctica.
- R 4.3.3; vegan 2.6-4; ggplot2 3.4.4; sandwich 3.1-0; lmtest 0.9-40; permute 0.9-7; scales 1.3.0.

| Comprobación | Resultado |
| --- | --- |
| Dimensiones de los conteos | 122 × 5323 |
| Profundidad tras rarefacción | 10.000 por muestra |
| Wald HC3 para diagnóstico, Shannon | F = 2,278990; p = 0,107034 |
| p de Holm, Shannon | 0,214068 |
| PERMANOVA, R² de diagnóstico | 0,016116 |
| PERMANOVA, p de diagnóstico | 0,534 |
| p de Holm, composición | 0,534 |
| PERMDISP, p | 0,136 |

Estas comprobaciones verifican el material entregado. La disponibilidad de R, sus paquetes, los permisos y el guardado de PNG en Landalab se comprobarán en la cuenta de prueba antes de repartir los insumos.
