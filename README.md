<p align="center">
<img width="200" height="200" src="https://user-images.githubusercontent.com/28677872/65840937-d8e08080-e2f4-11e9-8ae3-116fc96ce689.png">
</p>

The telemetry hardware has access to the CAN bus of vehicles, which gives us access to several sensors installed in it.
The sensor data is sent in intervals of 100ms to the internal MQQT queue whenever there is a change in the current state, that is when a vehicle is accelerating, the speed data is sent in intervals of 100ms but when the vehicle maintains a constant speed, no data is sent for the topic.

## Available sensors:
- speed | values from 0 to 200
- brake pedal angle | values from 0 to 100

## User case:
As responsible for the maintenance of the vehicle,
I need to know when a driver brakes abruptly
so that I can assess whether there was damage to the vehicle’s powertrain or tires.

*Abrupt braking is characterized by:*
- Deceleration greater than or equal to 10km/h in one second
- Pedal travel exceeding 95% when the speed is more than 5km/h

Use the sensor data to calculate when a vehicle has exceeded the stipulated limits and send the infractions to an external MQQT queue.

## What we will evaluate:
* How do you manage multiple threads
* How do you manage memory consumption
* How do you apply the concepts of BigO efficiency
* How do you apply Clean Code concepts
* How do you use classes and namespaces

## Is a plus if have:
* Use of protobuf
* UnitTests with gtest

## Some tips and links that can help you:
- You can use this service to create an external broker - https://www.cloudmqtt.com/
- To learn more about protobuf: https://developers.google.com/protocol-buffers/docs/cpptutorial
- To learn more about gtest: https://github.com/google/googletest
