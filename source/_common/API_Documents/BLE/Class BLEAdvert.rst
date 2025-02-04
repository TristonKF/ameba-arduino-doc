Class BLEAdvert
===============

.. contents::
  :local:
  :depth: 2

**BLEAdvert Class**
-------------------

**Description**
~~~~~~~~~~~~~~~

A class used for managing BLE advertising settings.

**Syntax**
~~~~~~~~~~

.. code-block:: c++

    class BLEAdvert

**Members**
~~~~~~~~~~~

+---------------------------------+----------------------------------------------------------------------+
| **Public Constructors**         | No public constructor is available as this class is intended to be a |
|                                 | singleton class. You can get a pointer to this class using           |
|                                 | BLEDevice::configAdvert().                                           |
+=================================+======================================================================+
| **Public Methods**                                                                                     |
+---------------------------------+----------------------------------------------------------------------+
| BLEAdvert::updateAdvertParams   | Update the current BLE advertisement settings.                       |
+---------------------------------+----------------------------------------------------------------------+
| BLEAdvert::startAdv             | Start BLE advertising.                                               |
+---------------------------------+----------------------------------------------------------------------+
| BLEAdvert::stopAdv              | Stop BLE advertising.                                                |
+---------------------------------+----------------------------------------------------------------------+
| BLEAdvert::setAdvType           | Set the BLE advertising type.                                        |
+---------------------------------+----------------------------------------------------------------------+
| BLEAdvert::setMinInterval       | Set the BLE advertising minimum interval.                            |
+---------------------------------+----------------------------------------------------------------------+
| BLEAdvert::setMaxInterval       | Set the BLE advertising maximum interval.                            |
+---------------------------------+----------------------------------------------------------------------+
| BLEAdvert::setAdvData           | Set BLE advertising data.                                            |
+---------------------------------+----------------------------------------------------------------------+
| BLEAdvert::setScanRspData       | Set BLE scan response data.                                          |
+---------------------------------+----------------------------------------------------------------------+

**BLEAdvert::updateAdvertParams**
---------------------------------

**Description**
~~~~~~~~~~~~~~~

Update the current BLE advertisement settings.

**Syntax**
~~~~~~~~~~

.. code-block:: c++

    void updateAdvertParams(void);

**Parameters**
~~~~~~~~~~~~~~

NA

**Returns**

NA

**Example Code**
~~~~~~~~~~~~~~~~

Example: `BLEWifiConfig <https://github.com/Ameba-AIoT/ameba-arduino-pro2/blob/dev/Arduino_package/hardware/libraries/BLE/examples/BLEWifiConfig/BLEWifiConfig.ino>`_

.. note :: Please use the other class member functions to set the BLE advertising parameters before using this function to update the advert data. "BLEAdvert.h" must be included to use the class function.

**BLEAdvert::startAdv**
-----------------------

**Description**
~~~~~~~~~~~~~~~

Start BLE advertising.

**Syntax**
~~~~~~~~~~

.. code-block:: c++

    void startAdv(void);

**Parameters**
~~~~~~~~~~~~~~

NA

**Returns**
~~~~~~~~~~~

NA

**Example Code**
~~~~~~~~~~~~~~~~

Example: `BLEWifiConfig <https://github.com/Ameba-AIoT/ameba-arduino-pro2/blob/dev/Arduino_package/hardware/libraries/BLE/examples/BLEWifiConfig/BLEWifiConfig.ino>`_

.. note :: This function gives you more control and flexibility over BLE advertising parameters. This function should not be used to start the BLE advertising process without first registering the necessary callback and handler functions. Call BLEDevice::beginPeripheral() to register the necessary functions and start advertising for the first time."BLEAdvert.h" must be included to use the class function.

**BLEAdvert::stopAdv**
----------------------

**Description**
~~~~~~~~~~~~~~~

Stop BLE advertising.

**Syntax**
~~~~~~~~~~

.. code-block:: c++

    void stopAdv(void);

**Parameters**
~~~~~~~~~~~~~~

NA

**Returns**
~~~~~~~~~~~

NA

**Example Code**
~~~~~~~~~~~~~~~~

Example: `BLEWifiConfig <https://github.com/Ameba-AIoT/ameba-arduino-pro2/blob/dev/Arduino_package/hardware/libraries/BLE/examples/BLEWifiConfig/BLEWifiConfig.ino>`_

.. note :: This function gives you more control and flexibility over BLE advertising parameters. This function should not be used to directly stop the BLE advertising process. Call BLEDevice::end() to stop advertising and free up used resources. "BLEAdvert.h" must be included to use the class function.

**BLEAdvert::setAdvType**
-------------------------

**Description**
~~~~~~~~~~~~~~~

Set the BLE advertising type.

**Syntax**
~~~~~~~~~~

.. code-block:: c++

    void setAdvType(uint8_t advType);

**Parameters**
~~~~~~~~~~~~~~

advType: the desired advertisement type.

- GAP_ADTYPE_ADV_IND (0, connectable undirected advertisement)

- GAP_ADTYPE_ADV_HDC_DIRECT_IND (1, connectable high duty cycle directed advertisement)

- GAP_ADTYPE_ADV_SCAN_IND (2, scannable undirected advertisement)

- GAP_ADTYPE_ADV_NONCONN_IND (3, Non-connectable undirected advertisement)

- GAP_ADTYPE_ADV_LDC_DIRECT_IND (4, connectable low duty cycle directed advertisement)

**Returns**
~~~~~~~~~~~

NA

**Example Code**
~~~~~~~~~~~~~~~~

Example: `BLEBeacon <https://github.com/Ameba-AIoT/ameba-arduino-pro2/blob/dev/Arduino_package/hardware/libraries/BLE/examples/BLEBeacon/BLEBeacon.ino>`_

.. note :: If connection requests should be allowed, call this function with GAP_ADTYPE_ADV_IND. If all connection requests should be rejected, call this function with GAP_ADTYPE_ADV_NONCONN_IND. "BLEAdvert.h" must be included to use the class function.

**BLEAdvert::setMinInterval**
-----------------------------

**Description**
~~~~~~~~~~~~~~~

Set the minimum BLE advertising interval.

**Syntax**
~~~~~~~~~~

.. code-block:: c++

    void setMinInterval(uint16_t minInt_ms);

**Parameters**
~~~~~~~~~~~~~~

minInt_ms: the desired advertisement minimum interval, expressed in milliseconds.

- 20 to 10240.

**Returns**
~~~~~~~~~~~

NA

**Example Code**
~~~~~~~~~~~~~~~~

NA

.. note :: BLE advertisements will repeat with an interval between the set minimum and maximum intervals. Set a shorter interval for the BLE device to be discovered rapidly and set a longer interval to conserve power. "BLEAdvert.h" must be included to use the class function.

**BLEAdvert::setMaxInterval**
-----------------------------

**Description**
~~~~~~~~~~~~~~~

Set the maximum BLE advertising interval.

**Syntax**
~~~~~~~~~~

.. code-block:: c++

    void setMaxInterval(uint16_t minInt_ms);

**Parameters**
~~~~~~~~~~~~~~

minInt_ms: the desired advertisement maximum interval, expressed in milliseconds.

- 20ms to 10240.

**Returns**
~~~~~~~~~~~

NA

**Example Code**
~~~~~~~~~~~~~~~~

NA

.. note :: BLE advertisements will repeat with an interval between the set minimum and maximum intervals. Set a shorter interval for the BLE device to be discovered rapidly and set a longer interval to conserve power. "BLEAdvert.h" must be included to use the class function.

**BLEAdvert::setAdvData**
-------------------------

**Description**
~~~~~~~~~~~~~~~

Set BLE advertising data.

**Syntax**
~~~~~~~~~~

.. code-block:: c++

    void setAdvData(BLEAdvertData adData);
    void setAdvData(uint8_t* pData, uint8_t size);

**Parameters**
~~~~~~~~~~~~~~

adData: advertising data formatted in a BLEAdvertData class object.

pData: pointer to a byte array containing the required advertising data.

size: number of bytes the advertising data contains, maximum of 31 bytes.

**Returns**
~~~~~~~~~~~

NA

**Example Code**
~~~~~~~~~~~~~~~~

Example: `BLEWifiConfig <https://github.com/Ameba-AIoT/ameba-arduino-pro2/blob/dev/Arduino_package/hardware/libraries/BLE/examples/BLEWifiConfig/BLEWifiConfig.ino>`_

.. note :: "BLEAdvert.h" must be included to use the class function.

**BLEAdvert::setScanRspData**
-----------------------------

**Description**
~~~~~~~~~~~~~~~

Set BLE scan response data.

**Syntax**
~~~~~~~~~~

.. code-block:: c++

    void setScanRspData(BLEAdvertData adData);
    void setScanRspData(uint8_t* pData, uint8_t size);

**Parameters**
~~~~~~~~~~~~~~

adData: scan response data formatted in a BLEAdvertData class object.

pData: pointer to a byte array containing the required scan response data.

size: number of bytes the scan response data contains, maximum of 31 bytes.

**Returns**
~~~~~~~~~~~

NA

**Example Code**
~~~~~~~~~~~~~~~~

NA

.. note :: "BLEAdvert.h" must be included to use the class function.
