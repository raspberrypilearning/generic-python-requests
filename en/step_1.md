Sometimes you need to fetch data from a website. This could be data that has been provided by a web API, or it might just be the **HTML** from the web-page that you need. Either way, the Python module called `requests` makes this task very easy.

- To begin, open up IDLE or your preferred programming environment and create a new file.

- First, import the module.

	```python
	import requests
	```

- Create a variable that stores the URL from which you want to fetch data. In this example, you are going to fetch the Raspberry Pi homepage.

	```python
	import requests
	url = "https://www.raspberrypi.org"
	```

- Next, tell your program to fetch the web page and store it in a variable.

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

- To get the actual content of the page, you can use `r.text`. To store this data in your program, you could do something like this:

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
