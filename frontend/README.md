# Movie Rating Frontend
## Getting Started
Start the [API](../api/README.md) before the React app so the health check has something to talk to.

### Running the React App in a GitHub Codespace
If you haven't created a codespace yet, follow the steps in the [root README](../README.md#running-codespace) first.
The codespace dev container already includes Node and npm.

1. Open a new terminal in the codespace (Terminal -> New Terminal) and `cd frontend`
- your path (`pwd`) should be **/workspaces/movie-rating/frontend**
2. `npm install`
3. `npm start`
- React app will start on port 3000. Open it from the Ports tab using the `Forwarded Address` for port 3000

![img_8.png](../img_8.png)

4. Going forward any React call to the api will need to use the `Forwarded Address` for port 8080. Right click port 8080 -> Port Visibility -> **Public** so the browser can reach it

![img_9.png](../img_9.png)

5. Update the api health endpoint in `frontend/src/Health.js` to `<forwarded address for 8080>/api/health`

![img_10.png](../img_10.png)

6. Validate react app is working properly by seeing it state in terminal it has started and validate it is talking to your api by navigating to `<forwarded address for 3000>/health` and seeing OK in the browser console logs

### Running the React App Locally
1. Open a new terminal in the repo directory and `cd frontend`
- your path (`pwd`) should be **{system directories}/interview-pre-req-check/frontend**
2. `npm install --location=global react-scripts`
3. `npm install`
4. `npm start`
- React app will start at localhost:3000

5. Update the api health endpoint in `frontend/src/Health.js` to `http://localhost:8080/api/health`
6. Validate react app is working properly by seeing it state in terminal it has started and validate it is talking to your api by navigating to `http://localhost:3000/health` and seeing OK in the browser console logs

### Troubleshooting
- If you encounter any issues with `npm install`, try deleting the node_module directory and package-lock.json file in /frontend and running the commands again.
- Codespace: if the health call fails with a CORS or 401 error, double check port 8080's visibility is set to **Public**
