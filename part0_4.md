sequenceDiagram
	participant user
	participant browser
	participant server

	user-->>browser: user writes in notes
	user-->>browser: user klicks save
	
	browser-->>server: Post /new_note (creates and sends new note to the server)
	activate server
	server-->>browser: HTML document
	deactivate server

	browser-->>server: Get /main.css
	activate server
	server-->>browser: the css file
	deactivate server

	browser-->>server: Get /main.js
	active server
	server-->>browser: the JavaScripte file
	deactivate server

	

	

	
