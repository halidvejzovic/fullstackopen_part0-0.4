sequenceDiagram
	participant user
	participant browser
	participant server

	user-->>browser: user writes in notes
	user-->>browser: user klicks save
	
	browser-->>server: POST /new_note (creates and sends new note to the server)
	activate server
	server-->>browser: HTML document
	deactivate server

	browser-->>server: GET /main.css
	activate server
	server-->>browser: the css file
	deactivate server

	browser-->>server: GET /main.js
	active server
	server-->>browser: the JavaScripte file
	deactivate server

	The browser starts executing the Javascript code that fetches the JSON from the server

	browser-->>server: GET /data.jsaon
	active-->>browser: ("content": "monkey", "date": "2026-05-17T06:04:43.124Z")
	deactivate server

	The browser executes the callback function that renders the notesa

	

	
