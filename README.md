# Cartografía Cultural CDMX | Observatorio de Políticas Culturales UACM

Repositorio del ecosistema de mapas interactivos del Observatorio de Políticas Culturales de la Universidad Autónoma de la Ciudad de México (UACM). Este proyecto documenta y analiza la distribución territorial, infraestructura material, dinámicas laborales y el impacto temporal de la contingencia sanitaria en espacios culturales independientes de la capital.

## Arquitectura y Métodos Técnicos
El proyecto opera sobre una arquitectura del lado del cliente en JavaScript nativo (Vanilla), sin dependencias de frameworks externos. Las decisiones de diseño y procesamiento responden a criterios de compatibilidad universal, carga directa en GitHub Pages y desacoplamiento de servicios propietarios.

* **Capa Cartográfica Monocromática Nativa:** Capa base universal de OpenStreetMap procesada dinámicamente mediante filtros CSS directos (`brightness`, `invert`, `grayscale` y `contrast` al 150% en modo oscuro; escala de grises al 100% y opacidad regulada en modo claro), emulando los entornos Positron y Dark Matter sin requerir llaves de acceso o tokens externos.
* **Motor de Temas:** Conmutación de interfaz clara y oscura a través de atributos de datos en el DOM (`data-theme`), sincronizando variables CSS, capas base e iconografía institucional vectorial.
* **Normalización de Geometrías y Escudo de Coordenadas:** Filtro de parsing numérico que resuelve problemas de comas decimales, invierte asignaciones latitud/longitud invertidas y valida coordenadas dentro del rango geográfico de la cuenca de México antes del renderizado.
* **Normalizador de Propiedades:** Rutina que procesa las propiedades del GeoJSON eliminando diacríticos, caracteres especiales y mayúsculas, permitiendo indexar datos con nombres de clave heterogéneos.
* **Estructura Unificada de Contacto:** Parser de cadenas de texto que desglosa registros múltiples de contacto, identifica protocolos web, correos y redes sociales, y los formatea como accesos directos con iconografía SVG en las ventanas emergentes (*pop-ups*).
* **Motores Temporales y Scrollytelling:** Módulos de filtrado cronológico acumulativo basados en sliders de control temporal con playback interactivo, además de visualizaciones vectoriales con interpolación poligonal (Flubber.js y D3.js) acopladas al desplazamiento vertical mediante Scrollama.
* **Widgets de Filtrado Dinámico:** Paneles interactivos con barras proporcionales y contadores numéricos animados que recalculan la distribución del universo visible en función de los filtros activos y la búsqueda textual.
* **Auditoría de Datos:** Modal accesible que documenta y lista las entidades excluidas del renderizado cartográfico por inconsistencias en coordenadas o datos temporales.

---

## Directorio de Mapas

### Artes Vivas
Espacios enfocados en artes escénicas, música y danza; condiciones de equipamiento, estatus operativo y registros temporales de cierre y reapertura.
* `index.html`: Condiciones de equipamiento y estatus general de espacios de Artes Vivas.
* `av-estatuspostpandemia.html`: Clasificación del estatus operativo tras la contingencia (abierto, cerrado, riesgo).
* `av-aperturas-pandemia.html`: Registro cronológico mensual de reaperturas durante 2020 y 2021.
* `cierre-covid-timelapse.html` / `cierre-av.html`: Evolución mensual del impacto de cierres a lo largo de 2020.
* `timelapse-av.html`: Línea de tiempo histórica de aperturas registradas desde 1950 hasta 2021.
* `scrollytelling-cierres.html`: Cartografía deformada y transición proporcional del impacto de clausuras por alcaldía.

### Cineclubes
Infraestructura, equipamiento técnico y características de sostenibilidad de los espacios de exhibición cinematográfica comunitaria e independiente.
* `cc-caracteristicas.html`: Objetivos, periodicidad de exhibición, tipos de espacio y poblaciones atendidas.
* `cc-caracteristicas-timelapse.html`: Evolución histórica y temporal del surgimiento de cineclubes por año de apertura.
* `cc-condiciones.html`: Infraestructura técnica, condición inmobiliaria, videotecas y acervos fílmicos.
* `cc-laborales.html`: Retribución económica, carga horaria semanal, perfiles del equipo y esquemas de sostenibilidad.

### Librerías
Distribución y características estructurales del circuito de librerías en la Ciudad de México.
* `lib-car-110224.html`: Tipología mercantil, perfil de acervo editorial, venta y modelos de operación.
* `lib-cond-110224.html`: Superficie en metros cuadrados, aforos, equipamiento y tenencia del espacio.
* `lib-pand-110224.html`: Reporte de interrupciones de servicio, periodos de cierre y estrategias comerciales adoptadas durante la pandemia.

---

## Ejecución

El proyecto no requiere procesos de compilación ni instalación de paquetes de Node.js. Para ejecutarlo en un entorno local:

1. Clonar el repositorio:
   ```bash
   git clone [https://github.com/JorgeCocompech/mapa-cdmx.git](https://github.com/JorgeCocompech/mapa-cdmx.git)

2. Servir los archivos mediante un servidor web local (por ejemplo, con Python):
   ```bash
   cd mapa-cdmx
   python3 -m http.server 8000

3. Acceder a http://localhost:8000 desde el navegador.




## ✒️ Autoría y Créditos
* **Desarrollo y Diseño UI/UX:** [Jorge Cocompech](https://jorgecocompech.rocks)
* **Investigación y Datos:** [Observatorio de Políticas Culturales - UACM](https://politicasculturales.mx)
* **Tecnologías Aplicadas:** * [HTML5](https://developer.mozilla.org/es/docs/Web/HTML) y [CSS3](https://developer.mozilla.org/es/docs/Web/CSS) (Estructura y diseño)
  * [Vanilla JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript) (Lógica nativa, sin frameworks)
  * [Leaflet.js](https://leafletjs.com/) (Motor cartográfico)
  * [OpenStreetMap](https://www.openstreetmap.org) (Mapas base)
