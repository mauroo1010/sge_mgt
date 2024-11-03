# Instrucciones para Activar el Módulo de Inventario y Configurar la API de Google en Odoo

## 1. Activar el Módulo de Inventario

1. Ve al menú de aplicaciones en Odoo.
2. Busca el módulo de Inventario y selecciona la opción de **Activar**.

## 2. Importar Productos desde un Archivo Excel

1. Dirígete a **Inventario > Productos > Productos**.
2. Haz clic en **Favoritos > Importar registros**.
3. Selecciona el archivo, en este caso `libros.xls`, y cárgalo.
4. Verifica que los campos de **Título**, **Precio** y **EAN** estén correctamente mapeados. Desmarca la opción de **Imagen**, ya que esta se cargará a través de la API.
5. Haz clic en **Importar**.

## 3. Obtener y Configurar la Clave API de Google

### 3.1. Crear una Clave API

1. Accede a **Google API’s y Servicios**.
2. Selecciona o crea un nuevo proyecto.
3. Ve a la sección de **Credenciales** y selecciona **Crear credenciales > Clave de API**.
4. Copia y guarda la clave generada.

### 3.2. Habilitar la API de Búsqueda Personalizada

1. En el panel de **Biblioteca**, busca **Custom Search API**.
2. Haz clic en **Habilitar**.

## 4. Crear un Motor de Búsqueda Programable

1. Accede a **Google Programmable Search Engine**.
2. Selecciona **Añadir**.
3. Configura el motor de búsqueda:
   - **Nombre**: Asigna un nombre que describa su propósito.
   - **Dónde buscar**: Selecciona **Buscar en toda la web**.
   - **Configuración de búsqueda**: Activa las opciones de **Búsqueda por imágenes** y **Búsqueda segura**.
4. Completa el CAPTCHA y haz clic en **Crear**.
5. Copia el **ID del motor de búsqueda**.

## 5. Configurar Odoo para Usar la API de Google

1. En Odoo, ve a **Ajustes > Opciones generales > Integraciones**.
2. Activa la opción **Obtener imágenes de Google** y guarda.
3. Introduce la **Clave API** y el **ID del motor de búsqueda** obtenidos anteriormente.
4. Guarda los cambios.

## 6. Asignar Imágenes a los Productos

1. Vuelve a **Inventario > Productos > Productos**.
2. Abre un producto que no tenga imagen.
3. En el menú desplegable de **Acción**, selecciona **Obtener imagen**.
4. Odoo buscará y asignará automáticamente una imagen según el código EAN del producto.


[Captura productos](https://imgur.com/zdOLWpW)