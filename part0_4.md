sequenceDiagram
	participant user
	participant browser
	participant server

	user-->>browser: user writes in notes
	user-->>browser: user klicks save
	
	browser-->>server: POST /new_note
	activate server
	server-->>browser: 302 Redirect to /notes
	deactivate server

	browser-->>server: GET /notes
	activate server
	server-->>browser: HTML document
	deactivate server

	browser-->>server: GET /main.css
	activate server
	server-->>browser: CSS file
	deactivate server

	browser-->>server: GET /main.js
	activate server
	server-->>browser: JavaScript file
	deactivate server

	Note right of browser: The browser starts executing the Javascript code that fetches the JSON from the server

	browser-->>server: GET /data.json
	activate server
	server-->>browser: JSON data
	deactivate server

	Note right of browser: The browser executes the callback function that renders the notes


	Part0.0.5-0.6
	
sequenceDiagram
	participant user
	participant browser
	participant server

	browser-->>server: Get /spa (page loads)
	activate server
	server-->>browser: HTML loads
	deactivate server

	browser-->>server: Get /main.css (page loads)
	activate server
	server-->>browser: CSS loads
	deactivate server	

	browser-->>server: GET /spa.js (page loads)
	activate server
	server-->>browser: Javascript loads
	deactivate server	

	browser-->>server: GET /data.json (page loads)
	activate server
	server-->>browser: JSON data
	deactivate server

	user-->>browser: user writes in notes
	user-->>browser: user klicks save

	browser-->>server: POST /new_note_spa
	activate server
	server-->>browser: 201 created
	deactivate server
