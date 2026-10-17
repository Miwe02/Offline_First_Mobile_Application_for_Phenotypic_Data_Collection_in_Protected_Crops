# Aplicación móvil offline-first para la recolección de datos fenotípicos en cultivos protegidos

**Trabajo de diploma de Ingeniería Automática · UCLV · julio de 2025**  
**Autor:** Miguel Garcés Vázquez · **Tutor:** Dr. Iván Santana Ching

> **Repositorio de documentación técnica y académica.** Contiene capturas originales de la aplicación y resultados documentados en la tesis. **No contiene todavía el código fuente Flutter ni un APK.**

[README in English](README.md) · [Arquitectura](docs/architecture.md) · [Variables de los cultivos](docs/data-model.md) · [Pruebas](docs/validation.md) · [Guía de publicación](GUIA_PUBLICACION.md)

## Problema que resuelve

En las casas de cultivos protegidos del **Valle del Yabú**, en Villa Clara, existía la necesidad de recopilar sistemáticamente variables fenotípicas de tomate, pepino y pimiento. El registro irregular y la conectividad intermitente dificultaban obtener datos consistentes para análisis agronómicos y futuros modelos predictivos.

## Solución desarrollada

Aplicación Android desarrollada con **Flutter y Dart**, arquitectura **MVVM**, almacenamiento local en **SQLite** y sincronización diferida de registros con **ThingsBoard** a través de HTTP/JSON.

Funciones principales:

- Crear, visualizar, editar y eliminar registros fenotípicos.
- Guardar observaciones aun sin conexión a internet.
- Validar campos y registrar la fecha de recolección.
- Reintentar la sincronización de registros pendientes cuando sea posible.
- Consultar información en tablas y gráficos de ThingsBoard.
- Programar recordatorios locales.
- Ofrecer una guía rápida y una interfaz adecuada al trabajo de campo.

## Capturas originales

| Inicio | Formulario de tomate | Registros guardados |
|:--:|:--:|:--:|
| <img src="assets/screenshots/home.jpg" width="185" alt="Menú principal"> | <img src="assets/screenshots/phenotypic-form-tomato.jpg" width="185" alt="Formulario para tomate"> | <img src="assets/screenshots/records-list.png" width="185" alt="Registros locales"> |

| Envío de datos | Recordatorios |
|:--:|:--:|
| <img src="assets/screenshots/synchronization-overview.png" width="185" alt="Sincronización IoT"> | <img src="assets/screenshots/reminders.png" width="185" alt="Recordatorios"> |

Todas las imágenes proceden del documento de tesis de 2025.

## Variables registradas

- **Pepino:** diámetro de tallo, cantidad de flores y frutos, peso y longitud del fruto.
- **Tomate:** diámetro de tallo, cantidad de flores y frutos, peso y firmeza del fruto (escala 1–10).
- **Pimiento:** diámetro de tallo, cantidad de flores y frutos, peso y número de lóbulos.

Consulta los tipos, unidades y valores en [docs/data-model.md](docs/data-model.md).

## Resultados medidos

| Prueba con SQLite | Volumen | Tiempo total |
| --- | ---: | ---: |
| Inserción masiva | 10 000 registros | 804 ms |
| Consulta | 1000 registros | 381 ms |
| Actualización masiva | 1000 registros | 522 ms |
| Limpieza | 10 000 registros | 162 ms |

La tesis también informa ensayos de conectividad con ThingsBoard y pruebas en cuatro modelos de teléfonos Android con diferentes prestaciones. Consulta [la validación detallada](docs/validation.md).

## Alcance científico

Este trabajo **desarrolla infraestructura para recopilar datos**, que pueden utilizarse posteriormente en investigación agrícola y aprendizaje automático. **No entrena modelos de inteligencia artificial ni automatiza por sí mismo el riego.**

## Autoría y disponibilidad

Trabajo de diploma: *Aplicación móvil para el registro de datos fenotípicos de cultivos protegidos*. Universidad Central «Marta Abreu» de Las Villas, julio de 2025. Autor: Miguel Garcés Vázquez. Tutor: Dr. Iván Santana Ching.

Repositorio de documentación sin fuente ni APK. Su reproducción y uso se subordinan a las condiciones de la universidad y la licencia indicada en la tesis. [Atribución y derechos](docs/citation-and-rights.md).

**Contacto académico:** [GitHub @Miwe02](https://github.com/Miwe02) · [Canal de YouTube](https://www.youtube.com/@MiguelGarc%C3%A9sV%C3%A1zquez-k7z)
