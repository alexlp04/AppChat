# AppChat - TDS 2024/25

AppChat es una aplicación de mensajería instantánea con interfaz gráfica desarrollada como proyecto para la asignatura de **Tecnologías de la Programación (TDS)**, curso 2024/25, en la Universidad de Murcia.

## 👥 Autores
- **Alejandro López López**
- **Jorge Serrano Rueda**
- **Subgrupo:** 2.3
- **Profesor:** Francisco Javier Bermúdez Ruiz
- **Convocatoria:** Junio

## 🚀 Características principales
- **Gestión de Usuarios:** Registro, inicio de sesión y creación de perfiles personalizados (incluyendo fotografía de perfil mediante URL o archivo local).
- **Contactos y Grupos:** Añadir o eliminar contactos, listarlos y crear grupos de chat.
- **Mensajería en tiempo real:** Envío de mensajes de texto y emoticonos de forma fluida e intuitiva.
- **Búsqueda Avanzada:** Sistema de filtros combinables para buscar mensajes dentro de chats individuales o grupos (por texto, nombre de contacto o teléfono).
- **Funcionalidad *Premium*:** Opción de convertirse en usuario Premium mediante una simulación de pago. Los usuarios Premium obtienen beneficios exclusivos, como la **exportación de chats enteros a formato PDF**.

## 🏗️ Arquitectura del Sistema
El proyecto sigue una arquitectura modular en capas que garantiza un alto nivel de escalabilidad y mantenibilidad, dividiéndose en los siguientes paquetes principales:
- **`controllers/`:** Gestiona el flujo de la aplicación.
- **`models/`:** Contiene las clases del dominio (`Usuario`, `Mensaje`, `Contacto`, `Grupo`).
- **`persistencia/` y `repository/`:** Cuentan con el patrón *Data Access Object* (DAO) para manejar el almacenamiento y la recuperación en memoria/bases de datos.
- **`services/`:** Lógica de negocio (Descuentos, Búsquedas y Exportación a PDF).
- **`windows/`:** Interfaz gráfica estructurada con vistas y componentes renderizados, en entornos de ventanas (*Login*, *Registro*, *Chat*, etc.).
- **`program/`:** `Programa.java`, el punto de entrada principal del software.

## 🛠 Patrones de Diseño Aplicados
En el desarrollo de la aplicación se han aplicado robustos patrones de diseño para solventar los retos de ingeniería:
1. **Factoría Abstracta y Singleton:** Para gestionar la creación de servicios de persistencia independientes de la tecnología (bases de datos MySQL o H2) y acceder a ellos centralizadamente.
2. **Adapter:** Para integrar la librería externa y desacoplar la lógica de generación y exportación externa de los documentos en formato PDF.
3. **Strategy:** Permite calcular dinámicamente los precios y aplicar distintos tipos de *descuentos* a los usuarios en sus suscripciones Premium.
4. **Decorator:** Utilizado para permitir a los usuarios aplicar múltiples y flexibles filtros de búsqueda sobre el historial de mensajes de manera combinada.

## 💻 Entorno y Tecnologías
- **Java 17**
- **Maven** (Gestión de dependencias del proyecto)
- **H2 / MySQL** (Bases de datos con persistencia JDBC)
- Liderazgo de la UI con **JTattoo** para obtener acabados visuales de mayor calidad
- **JCalendar** (Componentes de visualización de fechas)
- **iTextPDF** (Exportación de contenido)
- **JUnit 3.8.1** (Pruebas unitarias controladas)

## 🏁 Cómo ejecutar el proyecto
El proyecto cuenta con un archivo `pom.xml`. Tras descargar el repositorio y ubicarte en la raíz de `appchat`, puedes lanzar el proyecto usando:
```bash
mvn clean compile exec:java
```

## 📝 Notas de desarrollo
Desarrollar esta enorme aplicación nos ha tomado cerca de 120 horas (60 horas por cada componente del grupo). Este proyecto ha supuesto nuestra primera e importante experiencia en el diseño completo de una aplicación gráfica de ventanas en la universidad. Hemos podido vislumbrar cuán útiles resultan los **Patrones de Diseño**, aportando extensibilidad y mantenimiento al código desde una perspectiva totalmente práctica y profesional.
