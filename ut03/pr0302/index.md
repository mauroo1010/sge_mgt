# Documentación: Módulo Inventario en Odoo - Alta de Productos y Búsqueda de Imágenes

## 1. Alta de Productos
El proceso de alta de productos es similar al proceso de alta de clientes. Existen dos maneras principales de dar de alta productos en el sistema:

### 1.1 Alta Manual
Se puede registrar un producto manualmente ingresando todos los datos necesarios directamente en el sistema.

### 1.2 Alta Automática
Se pueden importar productos mediante la carga de archivos **Excel** o **CSV**, lo cual permite agregar grandes cantidades de productos al sistema de una sola vez.

### 1.3 Asociación de Imágenes a Productos
Una funcionalidad interesante es la capacidad de asociar imágenes a los productos. Aunque este proceso es difícil de automatizar, Odoo permite la integración con la **Google Custom Search API**, lo que posibilita la búsqueda automática de imágenes a partir del **código EAN** del producto.

## 2. Integración con Google Custom Search API

### 2.1 Obtener una API Key de Google
Para integrar Odoo con Google y buscar imágenes automáticamente, sigue estos pasos:

1. **Acceder a Google APIs y Servicios**:
   - Visita Google Cloud Console
   - Regístrate o accede con una cuenta de Google.

2. **Crear un nuevo proyecto**:
   - En el panel de control, crea un nuevo proyecto.

3. **Crear credenciales**:
   - Ve a la sección "Credenciales" y selecciona "Crear credenciales".
   - Elige la opción "Clave de API". Esto generará una **API Key** que se utilizará en Odoo.

### 2.2 Activar la Custom Search API
1. En la sección de "Biblioteca" de Google Cloud Console, busca **Custom Search API**.
2. Activa esta API para poder realizar búsquedas RESTful en Internet.

### 2.3 Configurar Google Programmable Search Engine
1. Accede al Google Programmable Search Engine
2. Crea un nuevo motor de búsqueda:
   - Asigna un nombre.
   - Configura el motor para buscar en toda la web.
   - Habilita la opción de "Búsqueda por imágenes" y la "Búsqueda segura".
3. Una vez creado el motor de búsqueda, obtén el **ID del buscador**, que será necesario para configurar Odoo.

## 3. Configuración en Odoo

### 3.1 Ajustes de Integración
1. Accede a **Ajustes** en Odoo.
2. Dirígete a la sección de **Integraciones**.
3. Activa la opción **Google Imágenes**. La página se recargará, mostrando dos campos:
   - **API Key**: Introduce la clave generada en Google Cloud.
   - **ID del Motor de Búsqueda**: Introduce el identificador del motor de búsqueda creado en Google Programmable Search Engine.

### 3.2 Uso de la Funcionalidad
1. Una vez configurado Odoo, ve a la sección de **Productos**.
2. En el menú **Acciones**, selecciona la opción **Obtener imágenes de Google Imágenes**.
3. Si el producto tiene un **código EAN**, el sistema buscará y cargará automáticamente la imagen del producto desde Google Imágenes.

[Captura productos](https://imgur.com/zdOLWpW)