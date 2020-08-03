# esp8266_p1meter
This is a 1-on-1 fork from [Flip Hess](https://github.com/fliphess/esp8266_p1meter) and merged the DSMR 5 topics from [Daniel de Jong](https://github.com/daniel-jong/esp8266_p1meter).
I've used the code from Flip Hess and changed the SoftwareSerial to the normal Rx UART. Then I took the DSMR 5 topics from Daniel de Jong and merged them into the code from Flip Hess.

## Usage
Anyone is freely to use and modify this data. I'm not claiming ownership on it and all credits goes to Flip Hess and Daniel de Jong. I only combined the best of both code to one code that suits my needs: mqtt for my wireless devices.
Please go to my [website](https://www.zuidwijk.com) to read more about my P1 modules

## Data Sent

All metrics are send to their own MQTT topic.
The software sends out to the following MQTT topics:

```
sensors/power/p1meter/consumption_low_tarif 2209397
sensors/power/p1meter/consumption_high_tarif 1964962
sensors/power/p1meter/returndelivery_low_tarif 2209397
sensors/power/p1meter/returndelivery_high_tarif 1964962
sensors/power/p1meter/actual_consumption 313
sensors/power/p1meter/actual_returndelivery 0
sensors/power/p1meter/l1_instant_power_usage 313
sensors/power/p1meter/l2_instant_power_usage 0
sensors/power/p1meter/l3_instant_power_usage 0
sensors/power/p1meter/l1_instant_power_current 1000
sensors/power/p1meter/l2_instant_power_current 0
sensors/power/p1meter/l3_instant_power_current 0
sensors/power/p1meter/l1_voltage 233
sensors/power/p1meter/l2_voltage 0
sensors/power/p1meter/l3_voltage 0
sensors/power/p1meter/gas_meter_m3 968922
sensors/power/p1meter/actual_tarif_group 2
sensors/power/p1meter/short_power_outages 3
sensors/power/p1meter/long_power_outages 1
sensors/power/p1meter/short_power_drops 0
sensors/power/p1meter/short_power_peaks 0
```

## My devices
The first two devices (photos) are made with the esp12f (on the left the wemos, on the right a compact own pcb design). The last two photos is my ethernet version. This one doesn't have an ESP on it, only a serial to ethernet converter. That's why the ethernet version doesn't have mqtt. Only raw telegrams send via telnet.
![Text](https://tweakers.net/i/Fu3kQKK-TCiij5-QTYYTbSTvUwU=/full-fit-in/4920x3264/filters:max_bytes(3145728):no_upscale():strip_icc():fill(white):strip_exif()/f/image/IQrKPk9CTYnJJv4qDNYXPJ0K.jpg?f=user_large)
![Text](https://tweakers.net/i/51o8v1z-kwIW0AatvzNtnD0oxfQ=/full-fit-in/4920x3264/filters:max_bytes(3145728):no_upscale():strip_icc():fill(white):strip_exif()/f/image/BKqk6h9q23IzcBOP2Xq0dalf.jpg?f=user_large)
![Text](https://tweakers.net/i/6dk6Qdvhg7LgXAGTGq-Rwe7z71k=/full-fit-in/4920x3264/filters:max_bytes(3145728):no_upscale():strip_icc():fill(white):strip_exif()/f/image/BLgsoPwITIQLqw65psryR94o.jpg?f=user_large)
![Text](https://tweakers.net/i/BSZT_vPtIsxMqNCx2IbBTiknli4=/full-fit-in/4920x3264/filters:max_bytes(3145728):no_upscale():strip_icc():fill(white):strip_exif()/f/image/Aev80UhLDiXNIRG8E2aHOCKI.jpg?f=user_large)

## Home Assistant Configuration

Use this [example](https://raw.githubusercontent.com/daniel-jong/esp8266_p1meter/master/assets/p1_sensors.yaml) for home assistant's `sensor.yaml`

The automatons are yours to create.
And always remember that sending alerts in case of a power outtage only make sense when you own a UPS battery :)

## Thanks to
All credits goes to the two names named prevously:

https://github.com/fliphess

https://github.com/daniel-jong
