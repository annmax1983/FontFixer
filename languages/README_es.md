# FontFixer

[English](../README.md) | [中文](README_zh.md) | Español | [Deutsch](README_de.md) | [日本語](README_ja.md) | [Français](README_fr.md)

Una extensión ligera para el navegador que optimiza las fuentes de las páginas web para una lectura más cómoda. Cambia la familia tipográfica, el tamaño y los colores del texto con un solo clic.

> Basada en Chromium · Manifest V3 · Permisos mínimos · Sin rastreo

---

## ¿Por qué FontFixer?

Muchos sitios web usan fuentes pequeñas, borrosas o difíciles de leer. FontFixer te permite ajustar las fuentes de la página web con tu tipografía preferida, modificar el tamaño de fuente y personalizar los colores de texto/enlaces — todo en tiempo real, sin recargar la página.

| Ventaja | Detalle |
|---------|--------|
| 🔤 **Soporte de fuentes locales** | Lee las fuentes instaladas en tu dispositivo mediante la API `queryLocalFonts` |
| ⚡ **Vista previa en tiempo real** | Todos los cambios se aplican al instante mientras ajustas — sin recargar la página |
| 💾 **Memoria por sitio** | Guarda configuraciones de fuente diferentes para distintos sitios web |
| ⚙️ **Aplicación automática** | Vuelve a aplicar la configuración guardada automáticamente cada vez que visitas un sitio configurado |
| 🔒 **Permisos** | `storage` + `scripting` + `activeTab`; acceso de host `<all_urls>` solo para inyectar fuentes en los sitios que configures |

---

## Funcionalidades

### 🆓 Gratis

| Funcionalidad | Descripción |
|---------|-------------|
| 🔤 **Selección de fuente** | Elige entre 3 fuentes integradas (Noto Sans, Source Han Sans, Arial) o cualquier fuente instalada en tu dispositivo |
| 📏 **Escala de tamaño de fuente** | Ajusta del 80% al 160% con un control deslizante |
| 🎨 **Color del texto** | Color de texto personalizado con selector de color |
| 🔗 **Color de los enlaces** | Color de enlaces separado para mejor legibilidad |
| 🔄 **Aplicación automática** | Vuelve a aplicar la configuración automáticamente en cada visita a un sitio configurado |
| 💾 **Guardado automático** | La configuración persiste automáticamente por sitio (hasta 5 sitios) |
| ↺ **Restablecimiento con un clic** | Restaura las fuentes originales de la página al instante |
| 🌍 **6 idiomas** | Inglés, chino, japonés, español, alemán y francés |

### ⭐ Pro (Requiere licencia)

| Funcionalidad | Descripción |
|---------|-------------|
| ♾️ **Configuraciones ilimitadas** | Guarda configuraciones de fuente para sitios web ilimitados |
| 📤 **Importar / Exportar** | Haz una copia de seguridad y restaura tus configuraciones de fuente entre dispositivos |

---

## Vista previa

<p align="center">
  <img src="icons/icon128.png" alt="Icono de FontFixer" width="80">
</p>

---

## Navegadores compatibles

| Navegador | Estado |
|---------|--------|
| Google Chrome | ✅ Totalmente compatible |
| Microsoft Edge | ✅ Totalmente compatible |
| Otros navegadores basados en Chromium | ✅ Debería funcionar |

---

## Instalación

1. Abre la página de extensiones de tu navegador:
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
2. Activa el **modo de desarrollador** (interruptor arriba a la derecha)
3. Haz clic en **Cargar descomprimida** y selecciona la carpeta `font-fixer`
4. Haz clic en el icono 🔤 de FontFixer en tu barra de herramientas para empezar

---

## Uso

### Cambiar fuentes

1. Haz clic en el icono de FontFixer en tu barra de herramientas
2. Selecciona una fuente del desplegable — 3 fuentes integradas están siempre disponibles; haz clic en **🔄** para cargar las fuentes instaladas en tu dispositivo
3. Ajusta el tamaño de fuente con el control deslizante (80%–160%)
4. Opcionalmente marca **Color del texto** / **Color de enlaces** para sobrescribir los colores (desactivado = no tocar los colores de la página)
5. Haz clic en **Aplicar y guardar** — la configuración se aplica al instante y se almacena para este sitio

### Aplicación automática

- Activa el interruptor **Aplicación automática** para volver a aplicar la configuración guardada de este sitio automáticamente cada vez que lo visites
- Con la aplicación automática desactivada, la configuración solo se aplica cuando abres el popup y haces clic en **Aplicar y guardar**

### Restablecer

- Haz clic en **Restablecer** para eliminar la configuración del sitio actual y restaurar sus fuentes originales

---

## Cómo funciona

```
Seleccionar fuente y ajustar configuración
       ↓
Clic en Aplicar y guardar
       ↓
CSS inyectado vía chrome.scripting.insertCSS
       ↓
Las fuentes de la página cambian al instante
       ↓
Configuración guardada en chrome.storage.local
       ↓
(Aplicación automática activada) se vuelve a aplicar automáticamente en tu próxima visita
```

Todo el procesamiento de estilos ocurre localmente en tu navegador. La única solicitud de red es **opcional** — cuando activas una clave de licencia Pro, FontFixer contacta con el servidor de licencias con tu clave y metadatos básicos del navegador (navegador, idioma, zona horaria). Nunca se lee ni sube contenido de páginas web.

**Nota sobre el acceso a fuentes locales:** Las fuentes locales usan la Local Font Access API — no se necesita permiso en el manifest. Chrome muestra un aviso de permiso en tiempo de ejecución, y la API solo se ejecuta durante un clic del usuario, así que abre el popup y haz clic en el **botón de actualización 🔄** para cargar tus fuentes locales. Solo se leen los nombres de visualización de las fuentes — los archivos fuente de las fuentes no se extraen, copian ni suben. Puedes revocar el permiso en los ajustes del navegador en cualquier momento.

**Regla de aplicación automática:** La inyección automática de estilos es por sitio. Activa el interruptor **Aplicación automática** en el popup para volver a aplicar la configuración de ese sitio en cada visita; con ella desactivada, la configuración solo se aplica cuando haces clic en **Aplicar y guardar**.

---

## Aviso de derechos de autor de fuentes

Tres tipografías integradas (Noto Sans, Source Han Sans, Arial) se distribuyen bajo la SIL Open Font License, que permite el uso personal y comercial sin autorización adicional.

La extensión solo lee la lista de nombres de las fuentes instaladas en tu dispositivo local mediante la API estándar del navegador, y no extraerá, copiará ni subirá ningún archivo de fuente local. Todos los derechos de las fuentes del sistema pertenecen a sus respectivos titulares de derechos de autor.

---

## Privacidad

- `storage` — Guarda tus preferencias de fuente localmente. No se almacena contenido de páginas web.
- `scripting` — Inyecta CSS para cambiar las fuentes de la página. No lee texto ni datos de la página.
- `activeTab` — Solo accede a la pestaña actual cuando interactúas con la extensión.
- `<all_urls>` — Permite a la extensión volver a aplicar tus estilos de fuente guardados automáticamente en los sitios que hayas configurado. Nunca lee ni sube contenido de páginas.
- **Acceso a fuentes locales** — Sin permiso en el manifest; el acceso se concede en tiempo de ejecución mediante un aviso del navegador. Lee solo nombres de visualización, nunca archivos de fuente. Se puede revocar en cualquier momento.
- Sin rastreo, sin analíticas. La única solicitud de red es la activación/validación de licencia cuando usas una clave de licencia Pro.

---

## Aviso de derechos de autor

Esta extensión solo ajusta localmente el estilo de renderizado visual de las páginas web para una experiencia de lectura más cómoda del usuario. Todo el texto, las imágenes y los derechos de autor del contenido del sitio web pertenecen al editor original. Modificar los estilos de visualización de la página no otorga a los usuarios ninguna autorización de derechos de autor sobre el contenido del sitio web. Los usuarios deberán respetar las leyes locales de propiedad intelectual al navegar por páginas web.

---

## Licencia

Copyright © 2026 FontFixer. Todos los derechos reservados.

---

## ❤️ Apoyo

Si te resulta útil FontFixer, ¡considera apoyar el proyecto!

**[👉 Obtener una clave de licencia](https://www.annmax1983.com/checkout.html?plugin=fontfixer)**
