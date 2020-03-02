Sometimes you need to fetch data from a website. This could be data that has been provided by a web API, or it might just be the **HTML** code of the web page. Either way, the Python module `requests` makes this task very easy.

- Open up IDLE or your preferred programming environment and create a new file.

- First, import the module.

    ```python
    import requests
    ```

- Create a variable that stores the URL from which you want to fetch data. In this example, you are going to fetch the Raspberry Pi homepage.

    ```python
    import requests
    url = "https://www.raspberrypi.org"
    ```

- Next, tell your program to fetch the web page and store it in a variable. In this example, we're calling it `r`.

    ```python
    import requests
    url = "https://www.raspberrypi.org"
    r = requests.get(url)
    ```

- Now run your program. `r` will hold a lot of information. You can examine it in the Python shell using the instructions below.

- When you type `r`, you should see something like this:

    ```python
    >>> r
    <Response [200]>
    ```

- This is an **HTTP response code**. Anything beginning with a `2` means 'success', i.e. fetching has been successful. `200` specifically means 'OK'.

- To get the actual content of the page, you can use `r.text`. To store this content, you could do something like the following:

    ```python
    import requests
    url = "https://www.raspberrypi.org"
    r = requests.get(url)
    data = r.text
    ```

- Often, the data you get from a website will be in **JSON** format. You can easily convert this into a Python dictionary by using `r.json()`, as shown below.

    ```python
    import requests
    url = "https://www.raspberrypi.org"
    r = requests.get(url)
    data = r.json()
    ```
