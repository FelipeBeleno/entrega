# Informe de Aplicación

 **1. Resumen Ejecutivo**

**Objetivo del Informe**: Presentar una visión completa de la aplicación, detallando el desarrollo y despliegue tanto del frontend como del backend.

**Visión General de la Aplicación**: Esta aplicación está desarrollada utilizando Next.js para el frontend, NestJS para el backend, y MongoDB como base de datos. Todo el desarrollo se ha realizado con TypeScript. El despliegue está configurado para actualizarse automáticamente con cada commit al repositorio.

**2. Descripción de la Aplicación**

**Visión General**

Esta aplicación es una solución integral diseñada para gestionar el ciclo de vida completo de componentes y productos, desde su registro inicial hasta la creación de productos, la gestión de ventas, el control de stock, la generación de facturas, y la elaboración de reportes detallados. Está dirigida a empresas que requieren un control exhaustivo sobre sus inventarios, producción, y ventas.

**Funcionalidades Clave**

1. **Gestión de Componentes**:
   1. **Registro de Componentes**: Permite registrar y catalogar todos los componentes disponibles, incluyendo detalles como nombre, tipo, stock disponible, valor unitario, y fecha de vencimiento.
   1. **Control de Inventario**: Monitorea en tiempo real los niveles de stock de cada componente, asegurando que siempre haya suficiente inventario para la producción de productos.
1. **Creación de Productos**:
   1. **Ensamblaje de Productos**: Utiliza los componentes registrados para crear productos. La aplicación permite seleccionar, combinar y definir la cantidad de cada componente que constituye un producto final.
1. **Gestión de Ventas**:
   1. **Registro de Ventas**: Permite registrar cada venta, asociando productos vendidos con clientes específicos y calculando automáticamente el valor total de la venta.
   1. **Generación de Facturas**: Genera facturas detalladas para cada venta, incluyendo información sobre los productos vendidos, cantidades, precios unitarios, impuestos, y el total a pagar.
   1. **Seguimiento de Ventas**: Proporciona informes detallados sobre las ventas realizadas, permitiendo analizar el rendimiento de productos y tomar decisiones informadas para optimizar el inventario y las ventas futuras.
1. **Control de Stock**:
   1. **Monitoreo en Tiempo Real**: Permite un seguimiento preciso y en tiempo real del inventario, asegurando que los niveles de stock sean suficientes para satisfacer la demanda de producción y ventas.
1. **Generación de Reportes**:
   1. **Reportes de Inventario**: Proporciona informes detallados sobre el estado del inventario, incluyendo niveles de stock, componentes en baja, y valor total del inventario.
   1. **Reportes de Ventas**: Ofrece una vista completa de las ventas realizadas, permitiendo analizar el rendimiento de productos, la rentabilidad de ventas, y las tendencias de compra de los clientes.
1. **Control de Acceso**:
   1. **Autenticación y Autorización**: Utiliza JWT y tokens para asegurar que solo usuarios autenticados puedan acceder a la aplicación y que solo aquellos con permisos específicos puedan realizar acciones como registrar componentes, crear productos o registrar ventas.

**Usuarios Objetivo**

La aplicación está diseñada para empresas que requieren una gestión precisa y eficiente de sus inventarios de componentes y productos, así como un control detallado de sus procesos de ventas y stock. Esto incluye fabricantes, distribuidores y tiendas minoristas que buscan optimizar su cadena de suministro y mejorar la eficiencia operativa.

**Beneficios**

- **Optimización del Inventario**: Al proporcionar un seguimiento en tiempo real del inventario de componentes y productos, la aplicación ayuda a evitar la escasez de suministros y a optimizar los niveles de stock.
- **Automatización y Eficiencia**: Facilita la gestión de ventas y el control de stock a través de la automatización de procesos clave, permitiendo a las empresas ahorrar tiempo y reducir errores.
- **Mejora en la Toma de Decisiones**: Los informes detallados sobre ventas, inventario y finanzas permiten a las empresas tomar decisiones estratégicas basadas en datos reales.

**3. Arquitectura de la Aplicación**

**Componentes Principales**:

- **Frontend**: Desarrollado con Next.js.
- **Backend**: Implementado con NestJS.
- **Base de Datos**: MongoDB.
- **Desarrollo**: Utiliza TypeScript para garantizar un código robusto y seguro.

**4. Frontend**

**Tecnologías Utilizadas**:

- **Framework**: Next.js.
- **Lenguaje**: TypeScript.
- **Estilos y Diseño**: Tailwind CSS.

**Estructura del Proyecto**:

- **Páginas y Componentes**: Descripción de las principales páginas y componentes del frontend.
- **Rutas y Navegación**: Manejo de rutas en Next.js.
- **Estado Global**: Gestión del estado Redux.

**5. Backend**

**Tecnologías Utilizadas:**

- **Framework: NestJS.**
- **Base de Datos: MongoDB.**
- **Lenguaje: TypeScript.**
- **Autenticación y Autorización: Control de acceso utilizando JWT y tokens.**

**Arquitectura del Backend:**

- **Estructura de la Aplicación:**
  - Controladores: Los controladores en NestJS son responsables de manejar las solicitudes HTTP entrantes y devolver las respuestas adecuadas. En esta aplicación, cada controlador está vinculado a un conjunto de rutas específicas que se ocupan de diferentes recursos, como productos, componentes, ventas, usuarios, y control de stock.
  - Servicios: Los servicios encapsulan la lógica de negocio y son utilizados por los controladores para procesar las solicitudes. Estos servicios interactúan con la base de datos a través de los repositorios y gestionan operaciones como la creación, actualización y eliminación de recursos.**
  - Repositorios: En NestJS, los repositorios actúan como una capa de abstracción sobre la base de datos, permitiendo realizar operaciones de lectura y escritura sobre los modelos de MongoDB. Son responsables de la comunicación directa con la base de datos, proporcionando métodos que los servicios utilizan para acceder a los datos.
- APIs Expuestas:
  - Endpoints: Los endpoints son puntos de acceso a los diferentes recursos de la aplicación. Se han creado endpoints para manejar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre componentes, productos, ventas, usuarios, y stock.
  - Métodos y Parámetros: Cada endpoint soporta métodos HTTP como GET, POST, PUT, DELETE, que permiten realizar diferentes acciones sobre los recursos. Los parámetros se validan y transforman utilizando los DTOs para asegurar que los datos sean correctos antes de ser procesados.

**Manejo de Datos:**

- **Adjunto en el repo esta la imagen ER con el diagrama entidad relación¨**.

- **Modelos de Datos:**
  - Los modelos de datos están definidos como esquemas de MongoDB, que representan la estructura de los documentos en la base de datos. Estos modelos incluyen definiciones de campos como name, description, components, value, quantity, clientId, entre otros, dependiendo del recurso.
  - Los esquemas incluyen reglas de validación para asegurar la integridad de los datos, tales como tipos de datos (string, number, boolean) y restricciones como la longitud mínima de campos de texto, o valores mínimos para campos numéricos.
- **Validación y Transformación:**
  - DTOs (Data Transfer Objects): Los DTOs son utilizados para definir la estructura de los datos que se envían y reciben en las operaciones de la API. A través de decoradores como @IsString(), @IsInt(), @IsEmail(), y @IsEnum(), los DTOs aseguran que los datos sean validados antes de ser procesados.
  - Transformación de Datos: La transformación de datos es manejada por decoradores como @Transform(), que permiten realizar ajustes en los datos antes de su validación, como la eliminación de espacios en blanco o la conversión de cadenas de texto a minúsculas.

**6. Integración entre Frontend y Backend**

**Comunicación API**:

- **Métodos de Solicitud**: Comunicación entre frontend y backend (RESTful API).
- **Manejo de Errores**: Estrategias para manejar errores en solicitudes API.

**Seguridad**:

- **Autenticación**: Utiliza JWT y tokens para la autenticación y autorización de usuarios.
- **Autorización**: Control de acceso a recursos basado en roles y permisos.

**7. Documentación de la API en Swagger**

La aplicación cuenta con documentación completa de la API utilizando Swagger, una herramienta que facilita la exploración y prueba de los endpoints disponibles. Swagger proporciona una interfaz interactiva donde los desarrolladores pueden ver, probar y comprender cómo funcionan las diferentes rutas y operaciones de la API.

- **Configuración de Swagger:** La configuración de Swagger en la aplicación NestJS permite a los desarrolladores acceder a una interfaz gráfica desde la cual pueden interactuar con la API. Esta configuración incluye la definición del título, descripción, versión de la API, y cualquier etiqueta adicional que clasifique los endpoints.
- **Documentación de Endpoints:** Cada endpoint de la API está documentado en Swagger, detallando la ruta, método HTTP (GET, POST, PUT, DELETE), parámetros esperados y las posibles respuestas. Esto facilita la comprensión y el uso correcto de la API por parte de otros desarrolladores.
- **Documentación de DTOs**: Los DTOs (Data Transfer Objects) utilizados en la aplicación están documentados con decoradores de Swagger, asegurando que la estructura de los datos esperados en las solicitudes y respuestas sea clara y precisa.
- **Acceso a la Documentación de Swagger:** La documentación está desplegada y accesible en el path /doc, permitiendo a los desarrolladores realizar pruebas interactivas directamente desde la interfaz de Swagger.

**8. Despliegue**

**Despliegue en Vercel:**

- **Descripción:** Vercel es utilizado para el despliegue del frontend de la aplicación. Esta plataforma facilita el despliegue continuo y el manejo de las versiones del frontend con cada commit al repositorio.
- **Configuración:** La configuración en Vercel incluye variables de entorno y ajustes de compilación específicos para la aplicación.**
- **Proceso de Despliegue: El despliegue es continuo, lo que significa que cada commit realizado en el repositorio desencadena automáticamente un nuevo despliegue.
- **Enlace al Frontend Desplegado: [URL del frontend desplegado en Vercel]**

**Despliegue en Render:**

- **Descripción:** Render es la plataforma utilizada para el despliegue del backend de la aplicación. Permite gestionar servicios backend y proporciona un entorno robusto para el manejo de la base de datos y la lógica de negocio.
- **Configuración:** Incluye la configuración de variables de entorno y ajustes de compilación para asegurar que el backend funcione correctamente.
- **Proceso de Despliegue:** Similar a Vercel, el despliegue en Render es continuo y se enlaza con el repositorio para actualizar automáticamente el backend con cada commit.
- **Enlace al Backend Desplegado: [URL del backend desplegado en Render]**

**9. Mantenimiento y Soporte**

**Monitoreo:**

- **Herramientas y Técnicas:** Se utilizan herramientas específicas para monitorear el rendimiento de la aplicación, detectar problemas y asegurar que tanto el frontend como el backend funcionen correctamente en todo momento.

**Actualizaciones:**

- **Plan de Actualización:** Se ha definido una estrategia para la actualización continua de la aplicación, asegurando que nuevas funcionalidades y mejoras se implementen de manera ordenada y sin interrupciones en el servicio.

**10. Conclusión**

**Resumen de Logros:**

- La aplicación ha sido desarrollada con éxito utilizando tecnologías modernas como Next.js y NestJS, y cuenta con un robusto sistema de control de stock, generación de facturas, reportes, y manejo de ventas.

**Áreas de Mejora:**

- Se identifican posibles mejoras en la escalabilidad del sistema, optimización del rendimiento, y la incorporación de nuevas funcionalidades que puedan enriquecer la experiencia del usuario y la gestión del negocio.


**Código Fuente:**

- **Repositorio del Frontend y Backend:**
   - Frontend: [https://github.com/FelipeBeleno/client-adm]
   - Backend: [https://github.com/FelipeBeleno/server-adm]
   - Despliegues:
      - Frontend: [https://client-adm.vercel.app/]
      - Backend: [https://server-adm-production.up.railway.app/doc], [https://server-adm-production.up.railway.app/api/v1]

- Nota: **El proyecto pasara a ser privado una vez se revise el mismo. Se adjuntara las variables de entorno en este repositorio para su uso en las aplicaciones.**
