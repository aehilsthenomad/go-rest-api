# REST API using GO and Gin

This is a simple web service written in Go using the Gin framework. Its an example of how to create a RESTful API to manage a collection of music albums (in a record shop perhaps). The API allows users to:

- Recieve a list of all albums (GET request)
- Retrieve a single album using its ID (GET request)
- Add a new album to the collection (POST request)

The project is based on the [Go Web Service with Gin tutorial](https://go.dev/doc/tutorial/web-service-gin).

## Prerequisites

To run this project, you'll need:

- Go installed on your system
- Gin package (`go get -u github.com/gin-gonic/gin`)

## Running the Project

1.  Clone this repository and navigate to the project directory.
2.  Install the necessary dependencies: \
`go mod tidy`
3.  Run the application: \
`go run main.go`
4.  The server will start, and you can access the API on http://localhost:8888 using this line: \
`curl http://localhost:8888`

# API Endpoints


## Get an album by ID
Method: GET \
Endpoint: `/albums/:id` \
Description: Return data for a single album from the list in JSON format.

Example response:

```
[
  {
    "id": "001",
    "title": "My Beautiful Dark Twisted Fantasy",
    "artiste": "Kanye West",
    "year": 2010,
    "price": 59.99
  },
]
```
## Get All Albums
Method: GET \
Endpoint: `/albums` \
Description: Return the full list of albums in JSON format.

## Add a New Album
Method: POST \
Endpoint: `/albums` \
Description: Add a new album to the collection. Requires a JSON body for album information. Returns a message confirming the addition and the sequentially assigned unique ID \

Example request:

```
{
  "id": "005",
  "title": "New Album",
  "artiste": "New Artist",
  "year": 2024,
  "price": 29.99
}
```

Example response:

```
{
    "message": "Added 'Love (Deluxe)' by Sade at ID 007"
}
```

## Update an Album

Method: PUT \
Endpoint: `/albums/:id` \
Description: Update the album stored at an ID in the resource list.

