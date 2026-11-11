# Movie Rating API

## Getting Started

### Running the Go API in a GitHub Codespace
If you haven't created a codespace yet, follow the steps in the [root README](../README.md#running-codespace) first.
The codespace dev container already includes Go and a running Postgres database, so you don't need to start Docker yourself.

1. Open a terminal in the codespace (Terminal -> New Terminal), `cd api` and run `go mod vendor`
2. `go run main.go` this command takes a minute to run for the first time

- API will start on port 8080 inside the codespace

3. Find the Ports tab at the bottom of the codespace next to your Terminal. Use the url found under `Forwarded Address` for port 8080 whenever you call the api from outside the codespace terminal (for example from a browser or the React app)
4. Right click port 8080 -> Port Visibility -> **Public** so the React app can reach the api

![img_9.png](../img_9.png)

5. Validate the api started correctly by navigating to `<forwarded address for 8080>/api/health` in a browser, or by running `curl http://localhost:8080/api/health` in a second codespace terminal, and confirming response body of **{"health":"OK"}**

### Running the Go API Locally
1. Start docker by opening the docker desktop application.
2. From a terminal opened to this repo `cd api` and run `go mod vendor`
3. `go run main.go` this command takes a minute to run for the first time

- API will start at localhost:8080

4. Validate api started correctly by navigating to `http://localhost:8080/api/health` in a browser or run `curl http://localhost:8080/api/health` and confirming response body of **{"health":"OK"}**

### Troubleshooting
- If you encounter any issues building the application before start, try deleting the provided vendor file at /api/vendor and running `go mod tidy` and `go mod vendor`
- Codespace: if port 8080 doesn't show up in the Ports tab, click `Add Port` and enter `8080`
