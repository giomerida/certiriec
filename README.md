# 🎓 CertiRiec — Gestor y Validador de Constancias Digitales

![Estado](https://img.shields.io/badge/estado-activo-brightgreen)
![Licencia](https://img.shields.io/badge/licencia-MIT-blue)
![Tecnología](https://img.shields.io/badge/tecnología-HTML%20%7C%20CSS%20%7C%20JavaScript-orange)
![Deploy](https://img.shields.io/badge/deploy-GitHub%20Pages-black)

**CertiRiec** es un sistema web completo para la **generación, gestión y validación de constancias y certificados digitales**. Permite a instituciones académicas y organizaciones emitir credenciales con diseño personalizado, código QR de autenticidad y un portal público de verificación — todo desde el navegador, sin necesidad de servidor ni base de datos externa.

🔗 **Demo en vivo:** [https://giomerida.github.io/certiriec/](https://giomerida.github.io/certiriec/)

---

## 📋 Tabla de Contenidos

- [Características](#-características)
- [Capturas de pantalla](#-capturas-de-pantalla)
- [Tecnologías utilizadas](#-tecnologías-utilizadas)
- [Instalación y uso](#-instalación-y-uso)
- [Módulos del sistema](#-módulos-del-sistema)
- [Formato de importación CSV](#-formato-de-importación-csv)
- [Personalización de plantillas](#-personalización-de-plantillas)
- [Validación de certificados](#-validación-de-certificados)
- [Credenciales de acceso demo](#-credenciales-de-acceso-demo)
- [Estructura del proyecto](#-estructura-del-proyecto)
- [Contribuciones](#-contribuciones)
- [Licencia](#-licencia)
- [Autor](#-autor)

---

## ✨ Características

- 🔍 **Portal público de verificación** — Cualquier persona puede validar la autenticidad de una constancia ingresando su ID único.
- 🖼️ **Generación de constancias en alta resolución** — Descarga en formato PNG con la información del participante incrustada sobre la plantilla.
- 🎨 **Personalizador visual en tiempo real** — Panel de diseño interactivo con simulador en vivo para ajustar posiciones, tamaños, colores y tipografías.
- 📄 **Plantillas vectoriales incluidas** — 3 diseños prediseñados (Clásico Dorado, Moderno Corporativo, Sello Esmeralda) y soporte para plantillas propias.
- 📦 **Importación masiva vía CSV** — Carga cientos de registros al mismo tiempo desde un archivo o texto estructurado.
- 📊 **Panel de control administrativo** — Gestión completa de participantes: agregar, importar, exportar y visualizar métricas.
- 🔐 **Acceso administrativo protegido** — Módulo de administración con autenticación por credenciales.
- 📱 **Código QR automático** — Cada constancia incluye un QR vectorial que apunta al portal de validación para verificación inmediata.
- ✍️ **Firmas digitales** — Soporte para cargar hasta 2 firmas digitalizadas (PNG con fondo transparente) con posicionamiento ajustable.
- 🌐 **100% frontend** — No requiere backend ni base de datos externa. Funciona directamente en el navegador y es desplegable en GitHub Pages.

---

## 📸 Capturas de pantalla

> _(Agrega aquí imágenes o GIFs del portal de validación, el panel de control y un ejemplo de constancia generada.)_

---

## 🛠️ Tecnologías utilizadas

| Tecnología                | Uso                                                     |
| ------------------------- | ------------------------------------------------------- |
| **HTML5**                 | Estructura de la interfaz                               |
| **CSS3**                  | Estilos y diseño responsivo                             |
| **JavaScript (Vanilla)**  | Lógica del sistema, generación de imágenes y validación |
| **Canvas API**            | Renderizado y exportación de constancias en PNG         |
| **QR Code (librería JS)** | Generación de códigos QR vectoriales                    |
| **GitHub Pages**          | Hosting y despliegue continuo                           |

---

## 🚀 Instalación y uso

Este proyecto no requiere instalación de dependencias ni configuración de servidor. Solo necesitas clonar el repositorio y abrir el archivo principal en tu navegador.

### Clonar el repositorio

```bash
git clone https://github.com/giomerida/certiriec.git
cd certiriec
```

### Ejecutar localmente

Abre el archivo `index.html` directamente en tu navegador, o usa un servidor local ligero:

```bash
# Con Python 3
python -m http.server 8080

# Con Node.js (npx)
npx serve .
```

Luego visita `http://localhost:8080` en tu navegador.

### Despliegue en GitHub Pages

El proyecto está listo para desplegarse en GitHub Pages sin configuración adicional. Solo activa GitHub Pages en la configuración del repositorio apuntando a la rama `main` (o `gh-pages`).

---

## 📦 Módulos del sistema

### 🔎 Portal de Validación (Público)

Accesible para cualquier usuario sin necesidad de autenticación. Permite:

- Ingresar el **Código Único de Certificado (ID)** impreso en la constancia.
- Verificar la autenticidad del documento contra la base de datos oficial del sistema.
- Previsualizar la constancia validada.
- Descargar una copia en **PNG de alta calidad**.

### 🖥️ Panel de Control (Administrador)

Requiere autenticación. Permite:

- **Gestión de alumnos:** Agregar registros individuales con ID único, nombre, curso y fecha de emisión.
- **Importación masiva:** Carga de múltiples registros desde bloques de texto en formato CSV.
- **Exportación de base de datos:** Respaldo de todos los registros en formato exportable.
- **Personalizador de diseño:** Ajuste visual completo de la plantilla en tiempo real.
- **Métricas y análisis:** Panel con totales de alumnos, eventos formativos y estado del sistema.

### 🎨 Personalizador de Diseño

Herramienta visual avanzada que incluye:

- Configuración de **título**, **leyenda**, nombres y cargos de hasta **2 autoridades firmantes**.
- Carga de **logotipo**, **firmas digitales** (PNG transparente) y **fondo personalizado**.
- Selección entre 3 **plantillas vectoriales** prediseñadas o carga de fondo propio (1920×1358 px recomendado).
- Ajuste de **colores primario y secundario**.
- Control de **coordenadas Y y tamaño de fuente** para cada elemento (título, nombre del alumno, curso, fecha, QR, firma).
- **Simulador en tiempo real** con persona de prueba para ajustar la maquetación antes de aplicar cambios.

---

## 📁 Formato de importación CSV

Al importar participantes de forma masiva, el bloque de datos debe seguir exactamente este orden de columnas, separadas por coma (`,`) o punto y coma (`;`):

```
ID,Nombre Completo,Curso o Evento,Fecha Emisión (AAAA-MM-DD)
```

**Ejemplo:**

```
RIEC-2026-001,María González López,Diplomado en Gestión Educativa,2026-06-15
RIEC-2026-002,Carlos Pérez Ruiz,Taller de Innovación Docente,2026-06-20
RIEC-2026-003,Ana Martínez Silva,Curso de Liderazgo Institucional,2026-06-25
```

> ⚠️ El campo de fecha debe respetar el formato `AAAA-MM-DD` para su correcta visualización.

---

## 🎨 Personalización de plantillas

### Plantillas incluidas

| Nombre              | Descripción                                                     |
| ------------------- | --------------------------------------------------------------- |
| Clásico Dorado      | Diseño formal con tonos dorados, ideal para diplomas académicos |
| Moderno Corporativo | Estilo limpio y profesional para eventos corporativos           |
| Sello Esmeralda     | Diseño elegante con paleta verde esmeralda                      |

### Plantilla propia

Puedes cargar tu propia imagen de fondo en formato `.png` o `.jpg`. Se recomienda una resolución de **1920 × 1358 píxeles** para garantizar la calidad en la descarga.

---

## 🔐 Validación de certificados

El sistema genera un **Código QR** en cada constancia que direcciona al portal de validación con el ID del certificado precargado. Al escanear el QR:

1. El usuario es dirigido al portal público de verificación.
2. El sistema compara el ID contra la base de datos registrada.
3. Si el registro es auténtico, muestra la constancia validada y habilita la descarga.
4. Si el ID no existe, muestra un mensaje de error con instrucciones.

---

## 🔑 Credenciales de acceso demo

Para explorar el panel de administración en el entorno de demo:

| Campo      | Valor      |
| ---------- | ---------- |
| Usuario    | `admin`    |
| Contraseña | `admin123` |

> ⚠️ **Importante:** Cambia estas credenciales antes de usar el sistema en un entorno de producción.

---

## 📂 Estructura del proyecto

```
certiriec/
├── index.html          # Archivo principal — contiene toda la interfaz del sistema
├── /assets             # (Opcional) Imágenes, logos y recursos estáticos
│   ├── /templates      # Plantillas de fondo prediseñadas
│   └── /fonts          # Tipografías utilizadas en el Canvas
└── README.md           # Este archivo
```

> La arquitectura de un solo archivo (`index.html`) facilita el despliegue inmediato sin dependencias externas.

---

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Si deseas mejorar CertiRiec:

1. Haz un **fork** del repositorio.
2. Crea una rama para tu mejora: `git checkout -b feature/nueva-funcionalidad`
3. Realiza tus cambios y confirma los commits: `git commit -m "Agrega nueva funcionalidad"`
4. Haz push a tu rama: `git push origin feature/nueva-funcionalidad`
5. Abre un **Pull Request** describiendo los cambios realizados.

### Ideas para contribuir

- [ ] Soporte para exportación en PDF
- [ ] Autenticación más robusta con tokens
- [ ] Integración con Google Sheets como fuente de datos
- [ ] Modo oscuro para el panel de administración
- [ ] Internacionalización (i18n) para múltiples idiomas
- [ ] Historial de descargas por certificado

---

## 📄 Licencia

Este proyecto está distribuido bajo la licencia **MIT**. Consulta el archivo [LICENSE](LICENSE) para más detalles.

---

## 👨‍💻 Autor

Desarrollado por **Giodev**

- 🌐 GitHub: [@giomerida](https://github.com/giomerida)
- 📧 email: hi@giomerida.dev

---

<div align="center">

© 2026 CertiRiec — Sistema seguro de auditoría criptográfica y validación de certificados a través de Códigos QR vectoriales.

</div>
