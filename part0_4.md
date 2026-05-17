sequenceDiagram
	participant user
	participant browser
	participant server

	user-->>browser: user writes in notes
	user-->>browser: user klicks save
	
	browser-->>server: Get /new_note (creates and sends new note to the server)
	activate server
	server-->>browser: HTML document
	deactivate server
