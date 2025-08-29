# ProyectoTienda Django

## Descripción

**ProyectoTienda** es una aplicación de comercio electrónico desarrollada con Django, diseñada para gestionar comercios, productos, usuarios y ventas de manera eficiente.

## Requisitos Previos

Antes de comenzar, asegúrate de tener instalados los siguientes programas en tu sistema:

* **Python 3.12.10** o superior.
* **Git** para clonar el repositorio.

## Instalación

Sigue estos pasos para configurar y ejecutar el proyecto en tu máquina local:

1.  **Clonar el repositorio:** Abre tu terminal y ejecuta el siguiente comando para descargar el código.

    ```bash
    git clone [https://github.com/carlabastida/reingenieriaPOS.git](https://github.com/carlabastida/reingenieriaPOS.git)
    cd ProyectoTienda
    ```

2.  **Crear y activar el entorno virtual:** Es crucial crear un entorno virtual para aislar las dependencias del proyecto.

    ```bash
    # Crear entorno virtual env
    python -m env myworld

    # Ejecuutar entorno virtual
    # En Windows:
    env\Scripts\activate.bat
    # En macOS/Linux:
    source env/bin/activate
    ```

3.  **Instalar dependencias:** Con el entorno virtual activado, instala todas las librerías necesarias desde el archivo `requirements.txt`.

    ```bash
    pip install -r requirements.txt
    ```

## Configuración de la Base de Datos

El archivo SQL crea la base de datos, mientras que las migraciones se encargarán de crear las tablas necesarias para la aplicación.

1.  **Crear la base de datos:** La aplicación utiliza MySQL, ejecuta el script SQL que se encuentra en la raíz del proyecto para crear la base de datos vacía.

    ```bash
    # Ejemplo para MySQL:
    mysql -u tu_usuario -p < base_de_datos.sql
    ```
2. **Agregar tu usuario y contraseña en setting.py:** Se deben agregar en el archivo settings.py, en USER tu usuario de acceso a mysql y en PASSWORD tu contraseña

    ```bash
    # En el archivo de settings.py busca la siguiente sección
    DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'BarrioStore',
        'USER': 'root',
        'PASSWORD': 'root1',
        'HOST':'localhost',
        'PORT':'3306',
        }
    }
    ```

3.  **Aplicar las migraciones:** Este comando creará todas las tablas y relaciones definidas en los modelos de Django.

    ```bash
    python manage.py migrate
    ```

## Creación de un Superusuario

Para acceder al panel de administración de Django y gestionar el contenido de la tienda, es necesario crear un superusuario.

1.  **Ejecutar el comando `createsuperuser`:** Sigue las instrucciones en la terminal para definir un nombre de usuario, correo electrónico y contraseña.

    ```bash
    python manage.py createsuperuser
    ```

## Ejecución del Proyecto

1.  **Ejecutar el servidor de desarrollo:**

    ```bash
    python manage.py runserver
    ```

2.  **Acceder a la aplicación:** La aplicación estará disponible en tu navegador en la siguiente dirección:

    ```
    [http://127.0.0.1:8000/tienda](http://127.0.0.1:8000/tienda)
    ```

    Puedes acceder al panel de administración de Django en `http://127.0.0.1:8000/admin`.

