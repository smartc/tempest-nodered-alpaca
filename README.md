# tempest-nodered-alpaca
NodeRED flow to serve Weatherflow Tempest data via ASCOM Alpaca

Basic NodeRED flow that will listen for Tempest UDP packets and provide weather data to ASCOM clients via the Alpaca protocol.

To use:

1. Install and configure NodeRED to run on your system.  By default this should run on port 1880.
2. Install the WeatherFlow palette from NodeRED library.
3. Import the included json flow template to NodeRED.
4. Optionally, change the safety limits and other info in the Set Flow Variables node.
5. Deploy the flow.
6. You should now be able to connect to the NodeRED server at http://your.pi.address:1880.  To connect to the Alpaca server in ASCOM, point the set up to port 1880.

Assuming that your Tempest hub is on the same LAN as your pi, this should be all you need to do. However, note that a few extra steps are necessary to implement discovery protocols and serve data on the Alpaca standard ports. In my case, I setup a lighttpd server and redirected the Alpaca ports (11111) to 1880 using the included lighttpd.conf configuration.

Unfortunately, providing advice or directions on configuring NodeRED or Lighttpd for your system are beyond my scope to support.  ChatGPT and Google were my friends - hopefully they will be as kind to you.
