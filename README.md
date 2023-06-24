<h1>Ascii-art-web (Dockerized Version)</h1>

<h2>By Abdulrahman khaled (akhaled), Sameer Ahmed (sahmed) and Mohammed Alsammak (malsamma)</h2>

<h3>Usage</h3>

1. `go run .` in the ascii-art-web/server directory

2. On any web browser, type `localhost:8080/` 

<h3>Implementation details: Algorithms</h3>

The `net/http` standard golang library was used to create the http server in `Go`. navigating to 
`ascii-art-web/server/main.go` and opening it, you will find the main function that handles both 
`/` and `/ascii-art` along with `favicon.ico` (handled by `http.NotFoundHandler()` function). Then, when the server is run, it listens for any requests at port 8080, ready to serve.

The server mainly listens for the GET request to load the main webpage, and a POST request when everything is 
submitted to `/ascii-art`. the server works by parsing HTML templates presented in the templates directory 
(along with styles.css). the ascii art is appended to the webpage inside the result `div`.

<h3> Requests returned </h3>

1. `OK (200)`, if everything went without errors.
2. `404 Not Found`, if nothing is found, for example templates or banners.
3. `400 Bad Request`, for incorrect requests.
4. `500 Internal Server Error`, for any unhandled errors.

<hr>

<h2>This version has a Dockerfile that can be used to build and run a containerized image of this project</h2>

<h3>To run ascii-art-web with docker:</h3>

1. Navigate to `/ascii-art-web-dockerize` and open terminal
2. Ensure the Docker Daemon is running (Docker icon should appear in the top bar).
3. Type `docker build -t ascii-art-web-docker .` and press `Enter`.
4. Ensure port 8080 is free by running `sudo fuser -k 8080/tcp`.
5. Type `docker run -p 8080:8080 ascii-art-web-docker` and press `Enter` to run. 


#To get the metadata of this docker container, run `docker inspect ascii-art-web-docker > metadata.json`
#then open up `metadata.json`

<h4> Look at the comments in the code for more info</h4>
<h5> Only standard Go libraries were used </h5>

