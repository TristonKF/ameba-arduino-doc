WiFi - Set up Server to Communicate
=====================================

.. contents::
  :local:
  :depth: 2
  
Materials
---------

- AmebaD [AMB21 / AMB22 / AMB23 / AMB25 / AMB26 / BW16 / AW-CU488 Thing Plus] x 1

- Laptop (Make sure it is connected to the same network domain as Ameba, and tcp tools are installed.)

Example
--------

In this example, we first connect Ameba to WiFi, then we use Ameba as server to communicate with client.

First, we make sure the correct Ameba development board is set in “Tools” -> “Board”

Then, open the Simple WiFi Server example in “File” -> “Examples” -> “WiFi” -> “SimpleServerWiFi”

In the sample code, modify the highlighted parameters and enter the ssid and password for your WiFi connection.

|image01|

Next, upload the code, then press the reset button on Ameba. Afterwards, you will see the connection information is displayed in the serial monitor.

|image02|

Next, we use the socket tool in the laptop to be the client and connect to the IP address of the Ameba board shown in the connection information at port 5000. (Note: The socket tool we used in this example is “sokit”)

|image03|

Click on the “Client” tab to choose the client mode, specify the IP and port of the server, then click “TCP Connect”.

If the connection is established successfully, the server shows a message: “A client connected to this Server”, and the IP and port of the connected client.

In this example, when the client and server are connected and the client sends a string to Ameba server, the Ameba server returns the identical string back to the client.

The string sent to server is returned and showed at the client side.

|image04|

Code reference
----------------

| Use WiFi.begin() to establish WiFi connection;
| https://www.arduino.cc/en/Reference/WiFiBegin
| To get the information of a WiFi connection:
| Use WiFi.SSID() to get SSID of the current connected network.
| https://www.arduino.cc/en/Reference/WiFiSSID
| Use WiFi.RSSI() to get the signal strength of the connection.
| https://www.arduino.cc/en/Reference/WiFiRSSI
| Use WiFi.localIP() to get the Ameba WiFi shield’s IP address.
| https://www.arduino.cc/en/Reference/WiFiLocalIP
| Create server and transmitting data:
| Use Server(port) to create a server that listens on the specified port.
| https://www.arduino.cc/en/Reference/WiFiServer
| Use server.begin() to tell the server to begin listening for incoming connections.
| https://www.arduino.cc/en/Reference/WiFiServerBegin
| Use server.available() to get a client that is connected to the server and has data available for reading.
| https://www.arduino.cc/en/Reference/WiFiServerAvailable
| Use client.read() to read the next byte received from the server.
| https://www.arduino.cc/en/Reference/WiFiClientRead
| Use client.write() to write data to the server.
| https://www.arduino.cc/en/Reference/WiFiClientWrite
| Use client.stop() to disconnect from the server.
| https://www.arduino.cc/en/Reference/WiFIClientStop


.. |image01| image:: ../../../../_static/amebad/Example_Guides/WiFi/WiFi_Set_up_Server_to_Communicate/image01.png
   :width:  716 px
   :height:  867 px
.. |image02| image:: ../../../../_static/amebad/Example_Guides/WiFi/WiFi_Set_up_Server_to_Communicate/image02.png
   :width:  704 px
   :height:  355 px
.. |image03| image:: ../../../../_static/amebad/Example_Guides/WiFi/WiFi_Set_up_Server_to_Communicate/image03.png
   :width:  799 px
   :height:  574 px
.. |image04| image:: ../../../../_static/amebad/Example_Guides/WiFi/WiFi_Set_up_Server_to_Communicate/image04.png
   :width:  704 px
   :height:  355 px
   