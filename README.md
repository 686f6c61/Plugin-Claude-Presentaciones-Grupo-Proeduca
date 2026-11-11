# PROEDUCA Presentaciones para Claude

Pide una presentación a Claude y recíbela montada sobre la plantilla oficial de **UNIR** o de **UNIPRO**: con su logotipo, sus colores, sus tipografías y cada elemento en su sitio. Sin copiar y pegar diapositivas ni recolocar cajas.

Se entrega en tres formatos: PowerPoint editable, PDF y HTML.

## Qué resuelve

Preparar una clase, una defensa de TFG o TFM o un informe en diapositivas suele consumir más tiempo en la maquetación que en el contenido. Con este plugin, tú aportas el material y Claude hace el resto:

1. Escribe el guion y lo revisa: una idea por diapositiva y títulos que afirman algo.
2. Elige para cada idea el tipo de diapositiva que le corresponde.
3. Monta la presentación sobre la plantilla de la institución.
4. Comprueba que ningún texto se salga ni se monte sobre otro.
5. Te entrega el `.pptx`, el PDF y el HTML.

## Qué incluye

| | |
|---|---|
| **Dos instituciones** | UNIR, La Universidad en Internet, y UNIPRO, Universitat Digital Europea. Si no dices para cuál es, Claude lo pregunta. |
| **Trece tipos de diapositiva** | Portada, separador de sección, agenda, texto, cita destacada, columnas, gráfico, cifras destacadas, tabla, cronología, figura, referencias y cierre. Agenda y cita, solo en UNIR. |
| **Gráficos y tablas nativos** | De columnas, de líneas y de dispersión. Se editan en PowerPoint como cualquier otro, no son imágenes. |
| **Figuras con los colores corporativos** | Diagramas de proceso, ciclos, jerarquías y matrices dibujados con la paleta de cada institución. |
| **Citas y referencias APA 7** | La cita breve al pie de cada diapositiva que usa una fuente y la lista de referencias al final, ordenada alfabéticamente. |
| **Números en español** | Coma decimal y los mismos decimales en los valores que se comparan. |
| **Datos reales** | Claude no inventa cifras ni referencias: lo que falta, lo pide. |

## Cómo trabaja cada parte

### Guion

Antes de generar nada, Claude escribe el guion y lo critica: cada título tiene que afirmar algo, cada diapositiva lleva una sola idea y el tipo elegido tiene que corresponder a la forma del contenido (una comparación va en columnas, una evolución en un gráfico, unas fases en una cronología). En presentaciones largas te lo enseña para que lo corrijas antes de maquetar.

### Figuras

- Los diagramas y esquemas se dibujan en SVG y se convierten a PNG para insertarlos en la diapositiva, con su pie.
- Solo usan la paleta de la institución. El conversor rechaza la figura si encuentra un color ajeno, así que no puede colarse un azul que no sea el corporativo ni los colores de la otra institución.
- Cada institución trae cuatro figuras modelo con sus colores (proceso, ciclo, jerarquía y matriz), que sirven de punto de partida.
- Una figura es para esquemas. Los datos numéricos van siempre en un gráfico o en una tabla, y un esquema conceptual lo dice en su pie.

### Gráficos y tablas

- Son objetos nativos de PowerPoint: se pueden abrir, cambiar los datos y cambiar el formato.
- Los gráficos se hacen con datos reales, los tuyos o un cálculo sobre ellos. No se dibujan barras ni nubes de puntos con valores puestos para ilustrar.
- El eje arranca en cero y lleva su título. Las series usan los colores de la institución.
- Las tablas admiten fila de total y quedan centradas en el espacio de la diapositiva.

### Citas y referencias

- Cada diapositiva que toma datos, ideas, figuras o citas textuales de una obra lleva al pie la cita breve en formato APA, «Autor (año)».
- Los gráficos, tablas y figuras propios llevan su nota de fuente, por ejemplo «Elaboración propia a partir de datos del INE (2024)».
- Al final, antes del cierre, se añade sola la diapositiva «Referencias» con todas las obras citadas, en APA 7, por orden alfabético y con sangría francesa. Si no caben en una, se reparten en varias.
- Si a una referencia le faltan datos bibliográficos, Claude los pide; no los completa con suposiciones.

### Comprobaciones antes de entregar

- **Auditoría automática**: avisa de textos que se salen de su caja, invaden el pie o se montan sobre otra forma, de celdas de tabla que no caben, de restos de texto de ejemplo de la plantilla y de diapositivas de datos sin fuente.
- **Revisión visual**: Claude genera una hoja con todas las diapositivas en miniatura, la mira y corrige lo que vea mal antes de dártela.

### Formatos de entrega

- **PowerPoint**: el original editable.
- **PDF**: para enviar o imprimir.
- **HTML**: un único archivo que se abre en cualquier navegador, con navegación por teclado, texto alternativo en las imágenes y las notas del orador.

## Instalación

Descarga el archivo que corresponda de la carpeta [`dist/`](dist/).

### claude.ai

1. Descarga [`presentacion-proeduca.zip`](dist/presentacion-proeduca.zip). No lo descomprimas.
2. En claude.ai, abre Personalizar > Skills.
3. Comprueba que está activada la ejecución de código y creación de archivos.
4. Sube el zip y deja la skill activada.

### Claude Cowork

Descarga [`proeduca-presentaciones.plugin`](dist/proeduca-presentaciones.plugin) y súbelo desde el gestor de plugins de la aplicación.

### Claude Code

Descarga [`proeduca-presentaciones.plugin`](dist/proeduca-presentaciones.plugin), que es un zip, descomprímelo en una carpeta y arranca Claude Code indicándola:

```bash
unzip proeduca-presentaciones.plugin -d proeduca-presentaciones
claude --plugin-dir proeduca-presentaciones
```

Las mismas instrucciones están en [`dist/LEEME.txt`](dist/LEEME.txt) y dentro de cada paquete.

## Cómo se usa

En una conversación nueva, pide la presentación diciendo la institución y adjunta el material de partida:

> Hazme una presentación de UNIR sobre el tema 3 de la asignatura, para una clase de 20 minutos. Te adjunto los apuntes.

> Prepara las diapositivas de mi defensa de TFM con la plantilla de UNIPRO. Te adjunto la memoria.

Claude te enseña el guion antes de generar cuando la presentación es larga, y al entregar te dice si queda algún aviso sin resolver.

## Qué conviene saber

- **Tipografía de UNIPRO**: la portada y los separadores usan Proeduca Sans Light, que no va incrustada en el archivo. En un equipo que no la tenga instalada, PowerPoint la sustituye por otra. UNIR va entera en Arial.
- **PDF y HTML**: los dibuja LibreOffice. Si el entorno donde se ejecuta Claude no lo tiene, se entrega solo el `.pptx` y Claude lo dice.
- **La plantilla no se toca**: logotipo, colores, tipografías y posiciones son los de cada institución y no se cambian desde la conversación.
- **Sin fotografías**: los diseños con fotografía de la plantilla de UNIR no están incluidos.

## Contenido del repositorio

| Archivo | Para qué |
|---|---|
| `dist/presentacion-proeduca.zip` | Skill para claude.ai |
| `dist/proeduca-presentaciones.plugin` | Plugin para Claude Cowork y Claude Code |
| `dist/LEEME.txt` | Instrucciones de instalación y uso en texto plano |

Versión 2.0.0.

## Créditos

Creado por [686f6c61.dev](https://686f6c61.dev).

Las plantillas, los logotipos y las marcas UNIR y UNIPRO pertenecen a sus respectivas instituciones.
