# The Ethernet interface is physically down {#trouble_lb2_jgt_mfb .troubleshooting}

This topic describes what causes an Ethernet interface to physically go down and the troubleshooting methods.

## Symptoms {#condition_jdw_zjy_jo0 .condition}

The Ethernet interface is physically down.

## Causes {#cause_ol2_0d8_c4z .cause}

-   The devices are not powered on or the cable is not connected properly.
-   The twisted pair or the optical fiber is too long or the loss over the link is great.
-   The interfaces, interface modules, or devices have failed.

1.  Check whether the local and peer devices are powered on and whether the cable and modules are connected properly.
2.  Check whether the links and interface modules of the devices are faulty. If the devices are connected through a twisted pair cable, check the following items:

    |Item|Criteria|What to do next|
    |----|--------|---------------|
    |Test if the twisted pair is faulty.|The twisted pair is normal.|Change the cable if it is faulty.|
    |Whether the length of the twisted pair between two devices meets requirements.|The length of the cable between two devices < 100 m. **Note:** 10/100/1000-M electrical interfaces use RJ45 connector and category 5 twisted pair cables \(or higher\), with a transmission distance of 100 m.

 |If the cable is longer than 100 m, use the following methods:     -   Shorten the distance between the devices to shorten the length of the twisted pair.
    -   If the distance between the devices cannot be changed, the devices can be connected through a repeater, hub, or switch.
 |
    |Check whether the twisted pair is formed in the correct order.|Twisted pairs are classified into straight-through twisted pairs and crossover twisted pairs. Straight-through twisted pairs are used to connect Ethernet interfaces between the following devices:

    -   A router and a hub
    -   A router and an Ethernet switch
    -   A computer and an Ethernet switch
    -   A computer and a hub
 Crossover twisted pairs are used to connect Ethernet interfaces between the following devices:

    -   A router and a router
    -   A router and a computer
    -   A hub and a hub
    -   A hub and a switch
    -   A switch and a switch
    -   A computer and a computer
 |If the type of twisted pair you use is incorrect for your device, change to the correct type.|

    If the devices are connected through an optical fiber, check the following items:

    |Item|Criteria|What to do next|
    |----|--------|---------------|
    |Check if the optical module corresponds to the optical fiber.|Check if the optical module matches the optical fiber using the following information:     -   A multi-mode optical fiber can be used with a multi-mode optical module.
    -   A single-mode optical fiber can only be used with a single-mode optical module, and cannot be used with a multi-mode optical module. Single-mode optical fibers are generally yellow and multi-mode optical fibers are generally orange.
    -   The wave length of two connected optical modules must be consistent.
 |If the optical fiber and the optical module do not match each other, change the optical module or the optical fiber according to the actual situation.|
    |Check whether the length of the optical fiber matches the transmission distance supported by the optical module.|The length of the optical fiber must be shorter than the transmission distance supported by the optical module.|Shorten the length of the optical fiber or use an optical module that supports greater transmission distance based on the actual situation.|
    |Test if the signal attenuation is within the allowed range.|The range of optical signal attenuation|If the attenuation surpasses the allowed range, change the optical fiber. If the problem persists, shorten the length of the optical fiber.|
    |Check if the two ends of the link are faulty by using the loopback method or a testing unit.|If you use a testing unit, check that the results show that data flow \(sending and receiving\) is normal. If you use the loopback method, connect the two ends of the optical fiber to an optical module. The interface goes up if the two ends of the link are normal.

 |If cable failure is detected, change the cable. If the failure persists, change the optical modules at the two ends.|

3.  Check if the hardware of the local device and the peer device is faulty.

