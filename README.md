# IoT

## Team Members:

powermaxz

Gautier30

GYPM4H

Natomac

maakler

On week 10, we have teamed up to work on the final project.

## Our project - HarvestMate:

## List of Possible Data To Be Collected:

- The amount light that comes in the window;
- Measure the height of the plants from the light;
- Measure PH from water;
- Measure Air humidity;
- Measure Air Temperature;
- dashboard;
- Weight the amount of harvest.

### V 2.0

- CO2 sensor (V2.0);
- Timelapse the growth of plants (V2.0);;
- Measure PH from water;(v2)
- He needs to control a water pump for auto watering; (v2)
- Measure Ar humidity; (DHT11)
- Monitoring data daily (graph the data); (Dashboard)
- CO2 sensor;
- Timelapse the growth of plants (Instagram);
- dashboard;
- Scale amount of harvest. 
- music wth the plant,
- Screen with dashboard.
- Local data storage.

## List of Sensor and Actuators:

- VL53L0X Lidar - laser distance sensor;
- DHT11 - Temp and humidity;
- Capacitive soil sensor - soil humidity;
- APDS 9660 - Light and color sensor (LDR is an alternative);
- Relay shield for LED lights;
- CO2 gas sensor;
- Raspberry Pi as gateway;
- PH water sensor;
- Screen with dashboard; 
- Relay shield controls LED growing lights;
- Dashboard with graphs;
- Tablet with a Screen for dashboard;
- Mobile Discord alert;
- A water pump for auto watering or Water flow controller. (V2.0)


### List of Materials: 

- Solder;
- Soldering iron;
- Hot glue;
- Wires;
- 3D printer(?);
- Scissors;
- Knife;
- Scotch tape. 



## HarvestMate Scenario:

### The project:

Joanna Greenthumb is a new PhD student at the University of Tartu computer science program. She moved to Tartu, Estonia from Guiana, a tropical country in South America. She really loves to eat fresh salad, and she is not able to get enough greens in Estonia's winter months. She even feels that she is having vitamin withdrawals. She realized that needed to eat more fresh greens. As she can not find good fresh salads at the supermarkets she decided to get a planter box and grow some micro-greens on her own house. She wants to eventually grown enough salad for herself just on the balcony with planter boxes.

She knows a little about gardening and she is willing to try out some ideas she found on the internet. The window from here student room gets some sunlight. She is wondering if she can grow the **micro-green** with just that light. She is unsure if it will be enough light on the darker winter months so she is thinking about complementing the light with some LEDs growing lights. 

### Measuring light:

As she is also taking the IoT class at the University of Tartu, Joanna decides to create a planter box with some sensors to measure some data from the light of here window. She realizes that she could use an LDR for this, but there is even a better sensor, the **APDS 9660 sensor** which can measure not only light intensity, but also color frequencies.

Joanna realizes that in the darkest months of the Estonian winter, the window light is not sufficient for the growth of the micro-greens. She then decides to install the LED growing lights to compliment the amount of light needed for the plants to be healthy. 
She uses 2x **20CM 12V full spectrum LED light strips** which will be controlled from a relay to turn the lights on/off if the amount of light drops bellow the desired threshold. 

She needs a some kind of computation that will calculate the amount of light and time period that that plants received of sun light that day and activate the complementary LEDs accordingly. 

This will be specially tricky as different plants have different needs in different stages of their lives even though micro-greens should be fairly simple in their needs. IoT communication between the Light measuring Node and the LED node is needed. Perhaps the the computation can be done in the gateway itself inside of Node-red.

### Watering the plants:

Because she is a PhD student, she is quite busy sometimes, she realizes that it would also be good if the planter that she does not have to water often. She also realizes that it would be important to get an alert msg to her smartphone telling when it is time water again.
At first, she does not want to automate the watering system because there isn't a faucet nearby. Also, when filling the tank by hand, she is able to visually check on the plants to see if they are doing well. She enjoys watering the plants herself, but she forgets to do so sometimes.
She decides to get a "self watering planter box" which has water container in the bottom that feeds the water to plants from underneath. She decides to install a **Water Level Liquid Detection Sensor** on the planter tank to check the level there and send an MQTT msg when it gets below a certain threshold. Then using Node-Red **node-red-contrib-discord-advanced** integration to send her a message when it's time to fill the tank again. The water level can also be used to alert about the maximum amount of water that should be put in the thank.
Joanna intends to implement the automatic water system if she has to leave for a long a vacation trip. For this automation she will need to implement a water flow controller actuator or some kind of a water pump.


The water level reading only needs to be done twice a day because it is not critical time reading. THe node can stay in sleep mode most of the time. A log is kept of how many times the water was replaced so he can know how much water is being used to grow the microgreens. This data can also help her understand how many water cycles the pants go through before it is time to fertilize again. 

Another sensor that can be installed in the water tank, is the **pH water sensor** to measure the water's pH level when the tank is filled. She would like to know if the tap water is Alkaline. If so, action should be taken to bring the water's pH level to between 6 and 7 level with pH stability solution. 

She remembers that it would also be a good idea to have reading and data from the soil humidity and also air humidity to further analyses the relationship between these and how fast the tank water must be refilled. She decides that the planter needs a **Capacitive Soil Sensor** and also a **DHT 11 or DHT 22** to measure air humidity and room temperature close to the window.

### Visualizing the Data:

After she implement the sensor and actuators, she decides to implement a  dashboard using Node-red dashboard UI to visualize the data. She also will collect the data locally on the gateway to have a simple database for running some analyses later and help her take more conscious decisions regarding light, water, fertilization and what to plant. 

Some graph plotting will also help her visualize the data collected. She also plans to use Node-red dashboard for this. 

After the plants start to grow a little it is time to understand how fast they are growing. Of course this can be done visually but we can also measure some data on how tall the plants are growing with the **VL53L0X Lidar distance sensor**;
These measurements can be done once a day only as these changes happens slowly over time. 

### Improvements:

The HarvestMate project can be expanded depending on what Joanna learns from her first prototype. Other sensors and actors can be implemented in a later stage to refine the design to accommodate other needs. 

It could also be interesting to measure the CO2 level around the plants at different stages. For this we could use the CO2 gas sensor. 



### Challenges:

- It can be trick to measure accurate light amount and understand the plants needs regarding light. 

- Plants take time to grow and a lot of time is needed to relate plants health and grow to the data collected. 

- Good design is needed to avoid as much as possible sensors' corrosion by proximity or contact with water. 

- Wiring and correct placement of the sensors will take some trial and error to optimize adjustment. 
