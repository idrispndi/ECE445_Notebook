# April 06
Progress Demo at 2.40pm

# April 07 - April 12
This week I worked on integrating two more sensor nodes because we mentioned that we will be having three plants. 

I developed the communication between multiple sensor nodes as transmitters and one main receiver. As my team is still in the midst of soldering the PCBs, there is only one ESP32-S3 (on PCB) available for me to use. The other sensor nodes are still using the Dev Module. 

For the ESP32-S3, I had to modify the code to correspond for different pins layout and naming. It's also important to connect the moisture sensor to GPIO with internal ADC.

In the receiver (given the names of each sensor node):
~~~
if (advertisedDevice.haveServiceUUID() && advertisedDevice.isAdvertisingService(serviceUUID)) {
    String name = advertisedDevice.getName().c_str();
    if (name == "Plant_Sensor_S3_Node1") {
        myDeviceA = new BLEAdvertisedDevice(advertisedDevice);
        doConnect = true;
    } else if (name == "Plant_Sensor_Dev_Node2") {
        myDeviceB = new BLEAdvertisedDevice(advertisedDevice);
        doConnect = true;
    } else if (name == "Plant_Sensor_Dev_Node3") {
        myDeviceC = new BLEAdvertisedDevice(advertisedDevice);
        doConnect = true;
    }
}
~~~

In the receiver loop to handle three sensor nodes:
~~~
if (doConnect) {
    if (myDeviceA && (pClientA == nullptr || !pClientA->isConnected())) {
        Serial.println("Attempting to connect to Node A...");
        pClientA = BLEDevice::createClient();
        if(connectToServer(myDeviceA, pClientA)) Serial.println("Success: Node A Connected");
    }
    if (myDeviceB && (pClientB == nullptr || !pClientB->isConnected())) {
        Serial.println("Attempting to connect to Node B...");
        pClientB = BLEDevice::createClient();
        if(connectToServer(myDeviceB, pClientB)) Serial.println("Success: Node B Connected");
     }
    if (myDeviceC && (pClientC == nullptr || !pClientC->isConnected())) {
        Serial.println("Attempting to connect to Node C...");
        pClientC = BLEDevice::createClient();
        if(connectToServer(myDeviceC, pClientC)) Serial.println("Success: Node C Connected");
    }
    doConnect = false;
}
~~~

Since the data packets from each sensor node would be similar, there must be a proper management of the data value corresponding to each plant in the receiver.
~~~
struct PlantNode {
    String name;
    String species;
    int moisture;
    int threshold;
    int maxPumpTime;
    BLEAdvertisedDevice* device;
    BLEClient* client;
    bool active;
};
~~~
# April 10
Team Contract Assessment due 11.59pm