# 🗺️ Cartografía Cultural CDMX | Observatorio UACM

Bienvenido al repositorio del ecosistema de mapas interactivos del **Observatorio de Políticas Culturales de la UACM**. Este proyecto visualiza y analiza la infraestructura, condiciones laborales y el impacto histórico/pandémico de los espacios culturales independientes en la Ciudad de México.

## 🚀 Características del Ecosistema
Todos los mapas de este proyecto fueron desarrollados con una arquitectura *Vanilla* (HTML, CSS, JS) utilizando **Leaflet.js** y datos en formato **GeoJSON**. Se diseñaron con un enfoque estricto en la Experiencia de Usuario (UX/UI) y la limpieza de datos:

* 🌓 **Motor de Temas Dinámico:** Interfaz responsiva con *Dark Mode* y *Light Mode* que adapta automáticamente los mapas base de CARTO.
* 🛡️ **Escudo Anti-Coordenadas Invertidas:** Algoritmo que detecta y corrige automáticamente errores de exportación en los GeoJSON (ej. coordenadas invertidas o uso de comas decimales) para evitar que los marcadores caigan en el océano.
* 🧹 **Normalizador Radical:** Motor de búsqueda de propiedades que ignora mayúsculas, acentos y variaciones de sintaxis para renderizar Pop-ups dinámicos sin importar cómo venga estructurada la base de datos.
* 📱 **UI de Redes Sociales (Pills):** Analizador universal que escanea las columnas de contacto, separa enlaces mezclados y genera botones interactivos limpios con iconografía SVG en los pop-ups.
* ⏳ **Timelapses Históricos:** Motor de animación temporal acumulativa e histórica para visualizar el nacimiento y muerte de espacios a lo largo de décadas o meses.
* 📊 **Widgets Dinámicos:** Panel lateral con contadores y gráficos de barras que se actualizan en tiempo real al hacer *pan/zoom* o al aplicar filtros combinados.
* 🔍 **Auditoría de Datos:** Modal inteligente que atrapa y enlista todos los espacios excluidos del mapa (por falta de coordenadas o fechas) para mantener total transparencia.

---

## 📂 Directorio de Mapas

### 🎭 Artes Vivas
Visualización de espacios dedicados a las artes escénicas, su estatus actual y su comportamiento durante la pandemia de COVID-19.
* `av-estatuspostpandemia.html` - Radiografía del estatus actual (abiertos, cerrados, en riesgo).
* `av-aperturas-pandemia.html` - Análisis de aperturas durante la crisis sanitaria.
* `cierre-covid-timelapse.html` / `cierre-av.html` - Timelapses del impacto mensual de cierres.
* `timelapse-av.html` - Evolución histórica general.

### 🎬 Cineclubes
Análisis de la infraestructura y sostenibilidad de los espacios de exhibición cinematográfica alternativa.
* `cc-caracteristicas.html` - Perfiles, aforos, objetivos y frecuencia de exhibición.
* `cc-caracteristicas-timelapse.html` - Evolución histórica (Año de apertura) de los cineclubes.
* `cc-condiciones.html` - Infraestructura técnica (proyectores, archivo fílmico, espacios).
* `cc-laborales.html` - Radiografía de sostenibilidad y condiciones de trabajo (sueldos, horas, figuras legales).

### 📚 Librerías
Mapeo del circuito de librerías independientes y comerciales en la capital.
* `lib-car-110224.html` - Características comerciales, tipo de libros y modelos de venta.
* `lib-cond-110224.html` - Condiciones inmobiliarias, metros cuadrados y equipamiento.
* `lib-pand-110224.html` - Impacto, cierres y estrategias adoptadas durante la pandemia.

---

## 🛠️ Instalación y Uso
Al estar construido íntegramente del lado del cliente (Frontend), este proyecto no requiere dependencias de Node.js ni bases de datos complejas.

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/JorgeCocompech/mapa-cdmx.git](https://github.com/JorgeCocompech/mapa-cdmx.git)
