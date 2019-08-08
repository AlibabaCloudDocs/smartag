# The Ethernet interface frequently goes up or down {#trouble_nhk_kgt_mfb .troubleshooting}

This topic explains why the Ethernet interface frequently goes up or down and how to troubleshoot it.

## Symptom { .condition}

The Ethernet interface frequently goes up or down.

## Causes { .cause}

-   The cable is incorrectly connected.
-   The twisted pair or the optical fiber is too long or the link loss is too high.
-   A fault has occurred to the interfaces, interface modules, or devices.

1.  Check whether the cable and modules of the local and peer devices are connected correctly. 
2.  Check whether the links and interface modules of the devices are faulty. If the devices are connected by a twisted pair, check the items listed in the following table.

    |Check item|Criteria|Action|
    |----------|--------|------|
    |Check whether the twisted pair is faulty.|The twisted pair is normal.|Replace the twisted pair if it is faulty.|
    |Check whether the length of the twisted pair between the two devices meets requirements.|The length of the cable between the two devices is less than 100 meters.**Note:** For 10/100/1000-M electrical interfaces, RJ45 connectors and category 5 twisted pair cables \(or higher\) are used, with a transmission distance of 100 meters.

|If the cable is longer than 100 meters, use the following methods:    -   Shorten the distance between the devices to shorten the length of the twisted pair.
    -   If the distance between the devices cannot be changed, the devices can be connected in series through a repeater, hub, or switch.
|
    |Check whether the twisted pair is used correctly.|Twisted pairs are classified into straight-through twisted pairs and crossover twisted pairs.Straight-through twisted pairs are used to connect Ethernet interfaces between the following devices:

    -   A router and a hub
    -   A router and an Ethernet switch
    -   A computer and an Ethernet switch
    -   A computer and a hub
Crossover twisted pairs are used to connect Ethernet interfaces between the following devices:

    -   Two routers
    -   A router and a computer
    -   A hub and a hub
    -   A hub and a switch
    -   Two switches
    -   Two computers
|If the type of twisted pair used is incorrect, change it to the correct type.|

    If the devices are connected through an optical fiber, check the items listed in the following table.

    |Check item|Criteria|Action|
    |----------|--------|------|
    |Check whether the optical module corresponds to the optical fiber.|Check whether the optical module matches the optical fiber according to the following information:    -   A multi-mode optical fiber can be used with a multi-mode optical module.
    -   A single-mode optical fiber can be used with a single-mode optical module, but cannot be used with a multi-mode optical module. Single-mode optical fibers are yellow and multi-mode optical fibers are orange.
    -   The wave length of two connected optical modules must be consistent.
|If the optical fiber and the optical module do not match, replace the optical module or the optical fiber as needed.|
    |Check whether the length of the optical fiber matches the transmission distance supported by the optical module.|The length of the optical fiber must be shorter than the transmission distance supported by the optical module.|Shorten the length of the optical fiber or use an optical module that supports greater transmission distance.|
    |Check whether the signal attenuation is within the allowed range.|The range of optical signal attenuation is less than - 28 dB.|If the attenuation exceeds the allowed range, replace the optical fiber. If the problem persists, shorten the length of the optical fiber.|
    |Check whether the two ends of the link are faulty by using the loopback method or a tester.|If you use a tester, the results indicate that the sending and the receiving data flows are normal.If you use the loopback method, the interface is in the up state after you connect the two ends of the optical fiber to an optical module.

|If a cable is faulty, replace the cable. If the fault persists, replace the optical modules at the two ends.|

3.  Check whether the hardware of the local and peer devices is faulty. 

