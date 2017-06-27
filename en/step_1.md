Sometimes you need to fetch data from a website. This could be data that has been provided by a web API, or it might just be the **HTML** from the web-page that you need. Either way, the Python module called `requests` makes this task very easy.

- To begin, open up IDLE or your preferred programming environment and create a new file.

- The first thing to do is import the module.

	```python
	import requests
	```

- Now you can create a variable that's value will be the URL that you want to fetch. In this example, you are going to fetch the Raspberry Pi homepage.

	```python
	import requests
	url = "https://www.raspberrypi.org"
	```

- Now you need to tell your program to fetch the web-page.

	```python
	import requests
	url = "https://www.raspberrypi.org"
	r = requests.get(url)
	```

- `r` now holds a lot of information. You can have a look at what it contains by running your program and then examining r in the Python shell.

- By typing `r` you should see something like this:

	```python
	>>> r
	<Response [200]>
	```

- This is an HTTP response code. Anything beginning with a `2` means **success**. `200` specifically means **OK**. 

- To get the actual content of the page, you can use `r.text`

- To store this in your Python program, you could do something like this:

	```python
	import requests
	url = "https://www.raspberrypi.org"
	r = requests.get(url)
	data = r.text
	```

- Often, if you're using a website to get data, the data will be in **JSON** format. You can easily convert this into a Python dictionary by using `r.json()`, as shown below.

	```python
	import requests
	url = "https://www.raspberrypi.org"
	r = requests.get(url)
	data = r.json()
	```
