## Description

This is a CRUD application which manages departments and their employees. To use this application, you need install [Docker](https://docs.docker.com/get-docker/) and it's useful if you have a tool which can work with HTTP methods, for example [Postman](https://www.postman.com/downloads/).

## Installation

1. Clone the repository

```bash
$ git clone https://github.com/patricia-kovacs/CRUD_application.git
```

2. Change directory, initialize and update submodules

```bash
$ cd CRUD_application
$ git submodule init
$ git submodule update
```

3. Build and run the app with Docker Compose

```bash
$ docker-compose up
```


## Running the app
### Ports

- Frontend: localhost:4200

- Backend: localhost:3000

- Postgres: localhost:5432

- PgAdmin: localhost:5050



### Set up PgAdmin

- **Login**

	- admin<span>@admin.<span>com

	- password



- **Add new server**

	- General
		- Name: (what you want)

	- Connection
		- Host Name/Adress: postgres

		- Username: user

		- Password: password


### Upload database data with JSON String

Initially, the database is not filled with data. You can simply upload the database data with a JSON String. Send a **POST** request with ```Content-type:application/json``` in the header, and with the JSON String in the body to this URL: http://localhost:3000/api/user and now you can see the uploaded data on the frontend after refreshing the page.

```json
{
"departments": [
{
	"name":"First Department",
	"users": [
		{
		"name":"John Smith",
		"birthday":"1960-12-12"
		},
		{
		"name":"Maria Martinez",
		"birthday":"1980-02-12"
		}
	]
},
{
	"name":"Second Department",
	"users": [
		{
		"name":"Henry Taylor",
		"birthday":"1993-10-11"
		},
		{
		"name":"Jane Williams",
		"birthday":"1975-02-22"
		}
	]
}
]
}
```

	
Now you can see on the frontend the list of the employees by departments. You can also edit, delete and add employees to the selected department.
