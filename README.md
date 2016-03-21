# adb-broadcast
Simulate realtime location updates by dragging your mouse around a map. Your location is broadcast to your Android device
where your app can handle it however it wants

# Setup
Start the server

`./server/start.sh`

Start the client

`./client/start.sh`

# Configure
The server sends this broadcast to adb:

`var cmd = 'am broadcast -a com.mapzen.erasermap.SET_MOCK_LOCATION --es lat "%1" --es lng "%2" --es sent-at "%3"'`

Modify the command string in `server/adb-server.js` to broadcast to your app's receiver

# Uses
The project uses https://github.com/tangrams/eraser-map as basis for client code with a couple modifications to prevent panning
the map when user drags
