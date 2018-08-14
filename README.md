# OpenWrt_MQTT_InFlux_BPI_R1
OpenWRT Router that has built in MQTT Support via collectd and  transmmit data to Influxd

this is the newest version of openwrt for BPI-R1   18.0.6.0 .  it is preconfigured to handle
Mqtt via Custom Collectd interface.  it is preconfigure to transmit sollectd CSV data to an influx server. 
For MQTT the data is written to the CSV as soon as it is recieved. independent of what frequency collectd is set at

 to modify influx server info goto /runfile and modify the server location in Sendinflux.sh  if you wish to add
 or  remove data being sent to influxdb  please modify /runfiles/cp-csv
 to enable influx sends in local startup (system>startup)  add the line /runfiles/./startup.sh  -- this copies the
 files over to /tmp and executes them which will extend the life of your SD card

MQTT catagories  are Energy, Temp, Humidity, Flow and Pressure

format for sending topic

mosquitto_pub -t 'incoming/OpenWrt/mqtt-Energy/power-grid' -m 'N:21.5'

mosquitto_pub -t 'incoming/OpenWrt/mqtt-Temp/temperature-greenhouse' -m 'N:21.5'

mosquitto_pub -t 'incoming/OpenWrt/mqtt-Humidity/humidity-greenhouse' -m 'N:21.5'

mosquitto_pub -t 'incoming/OpenWrt/mqtt-Flow/flow-heatpump' -m 'N:21.5'

mosquitto_pub -t 'incoming/OpenWrt/mqtt-Pressure/pressure-heatpump' -m 'N:21.5'


 
