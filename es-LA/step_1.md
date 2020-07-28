A veces es necesario obtener datos de un sitio web. Esto podría ser información proporcionada por una API web, o podría ser el código **HTML** de la página web. De cualquier manera, el módulo Python `requests` hace que esta tarea sea muy fácil.

- Abre IDLE o tu entorno de programación preferido y crea un nuevo archivo.

- Primero, importa el módulo.

    ```python
    import requests
    ```

- Crear una variable que almacene la URL de la que desea obtener datos. En este ejemplo, vas a obtener la página principal de Raspberry Pi.

    ```python
    import requests
    url = "https://www.raspberrypi.org"
    ```

- A continuación, indica a tu programa que busque la página web y la almacene en una variable. En este ejemplo, lo llamamos `r`.

    ```python
    import requests
    url = "https://www.raspberrypi.org"
    r = requests.get(url)
    ```

- Ahora ejecuta tu programa. `r` guardará mucha información. Puedes examinarlo en la interfaz de Python usando las instrucciones de abajo.

- Cuando escribes `r`, deberías ver algo como esto:

    ```python
    >>> r
    <Response [200]>
    ```

- Este es un **código de respuesta HTTP**. Todo lo que comience con un `2` significa 'éxito', es decir, se obtuvieron los datos de manera exitosa. `200` significa específicamente 'OK'.

- Para obtener el contenido real de la página, puedes usar `r.text`. Para almacenar este contenido, puedes hacer algo como lo siguiente:

    ```python
    import requests
    url = "https://www.raspberrypi.org"
    r = requests.get(url)
    data = r.text
    ```

- Frecuentemente, los datos que obtienes de un sitio web serán en formato **JSON**. Puede convertir esto fácilmente en un diccionario de Python usando `r.json()`, como se muestra a continuación.

    ```python
    import requests
    url = "https://www.raspberrypi.org"
    r = requests.get(url)
    data = r.json()
    ```
