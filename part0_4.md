sequenceDiagram
	participant user
	participant browser
	participant server

	user-->>browser: user writes in notes
	user-->>browser: user klicks save
	
	browser-->>server: POST /new_note (creates and sends new note to the server)
	activate server
	server-->>browser: 302 Redirect to /notes
	deactivate server

	browser-->>server: GET /notes
	activate server
	server-->>browser: HTML document

	browser-->>server: GET /main.css
	activate server
	server-->>browser: the CSS file
	deactivate server

	browser-->>server: GET /main.js
	activate server
	server-->>browser: the JavaScript file
	deactivate server

	Note right of browser:The browser starts executing the Javascript code that fetches the JSON 	from the server

	browser-->>server: GET /data.json
	activate server
	server-->>browser: POST /("content": "monkey", "date": "2026-05-17T06:04:43.124Z")
	deactivate server

	Note right of browser: The browser executes the callback function that renders the notesa
