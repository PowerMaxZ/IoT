# IoT

## This is a team folder of:

powermaxz

Gautier30

GYPM4H

Natomac

maakler

On week 10, we have teamed up to work on the final project.

## Our project - HarvestMate:

List of possible data:

- He wants to measure the amount light that comes in the window;
- Maybe control an LED light;
- Measure the hight of the plants from the light;
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



List of Sensors:

- LIDAR - laser,
- DHT11 - Temp and humidity,
- Capacitive soil sensor - soil humdity
- APDS 9660 - Light and color sensor. (LDR)
- Relay for LED lights
- CO2 gas sensor
- PH water sensor.

List of Materials: 

- Solder;
- Soldering iron;
- Hot glue;
- Wires;
- 3D printer(?);
- Scissors;
- Knife;
- Scotch tape. 



## HarvestMate scenario:

Joanna Greenthumb is a new PhD student at the University of Tartu computer science program. She moved to Tartu, Estonia from Guiana, a tropical country in South America. She really loves to eat fresh salad, and she is not able to get enough greens in Estonia's winter months. She even feels that she is having vitamin withdrawals. She realized that needed to eat more fresh greens. As she can not find good fresh salads at the supermarkets she decided to get a planter box and grow some micro-greens on her own house. She wants to eventually grown enough salad for herself just on the balcony with planter boxes.

She know a little about gardening and she is willing to try out some ideas she found on the internet. The window from here student room gets some sunlight. She is wondering if she can grow the micro-green with just that light. She is unsure if it will be enough light on the darker winter months so she is thinking about complementing the light with some LEDs growing lights. 

As she is also taking the IoT class at the University of Tartu, Joanna decides to create a planter box with some sensors to measure some data from the light of here window. She realizes that she could use an LDR for this, but there is even a better sensor, the APDS 9660 which can measure not only light intensity, but also color frequencies.

Because she is a PhD student, she is quite busy sometimes, she realizes that it would also be good if the planter that she does not have to water often. She also realizes that it would be important to get an alert msg to her smartphone telling when it is time water again. She likes to water the plants herself, so she does not want to automate the watering system, but she does forget to water them at the right moment. She decides to get a "self watering planter box" which has water container in the bottom that feeds the water to plants from underneath. She decides to install a **Water Level Liquid Detection Sensor** on the planter tank to check the level there and send an MQTT msg when it gets bellow a certain threshold. Then using Node-Red **node-red-contrib-discord-advanced** integration to send her a message when it's time to fill the tank again. The water level can also be used to alert about the maximum amount of water that should be put in the thank.  

She remembers that it would also be a good idea to have reading and data from the soil humidity and also air humidity to further analyses the relationship between these and how fast the tank water must be refilled. She decides that the planter needs a **Capacitive Soil Sensor** and also a **DHT 11 or DHT 22** to measure air humidity and room temperature close to the window.  


TODO

FROM HERE DOWN IS JUST A DRAFT OF IDEAS FROM OUR OLD SCENARIO // I will include them in our story this weekend. 

This reading only needs to be done twice a day so the node can stay in sleep mode most of the time. Whenever the water is low or dry, a message must be sent to Olinato so that he can refill the water in the tank. A log is kept of how many times the water was replaced so he can know how much water is being used. This data can also help him understand how many water cycles the pants go through before it is time to fertilize again. In the same tank, he decides to install a pH sensor to measure the water's pH level as he suspect that the tap water in Tartu is Alkaline. If so, action should be taken to bring the water's pH level to between 6 and 7 level.  

At first, he does not want to automate the watering system because he does not have access to the a faucet nearby. This watering time, when done by hand is also a good time for him to do a visual check on the plants to see if they are doing well. Olinato intends to implement the automatic water system if he has to leave on a vacation trip. For the automation he will some kind of a water pump.



After the plants start to grow a little it is time to understand how well they are growing. Of course this can be done visually but we can also measure some data like:
- How tall the plants are growing with distance sensor;
- How green are the plants using a color frequency sensor;
Both of these measurements can be done once a day only as these changes happens slowly over time.


After the first prototype is running, Olinato decides to implement some kind of dashboard and simple data base where he can visualize the data collected to help him take more conscious decisions. Some graph plotting will also help him visualize the data. 

He realizes that in the darkest months of the Estonian winter, the window light is not sufficient for the growth of the micro-greens. Olinato decides to than install the LED growing lights to compliment the amount of light needed for the plants to be healthy. He install a relay to turn the lights on/off if the amount of light drops bellow threshold to early in the day. He needs a some kind of computation that will calculate the amount of light and time period that that plants received of sun light that day and activate the complementary LEDs accordantly. This will be specially tricky as different plants have different needs in different stages of their lives even though micro-greens should be fairly simple in their needs. IoT communication between the Light measuring Node and the LED node is needed. Perhaps the the computation can be done in the gateway itself.   

After the first prototype has been refined, he decides to also hack a CO2 sensor to see if he can collect soil CO2 information. This is a challenge as these sensors are not made to be inside the earth. He also would like to install a camera to take timelapse video of the growing plants. 


