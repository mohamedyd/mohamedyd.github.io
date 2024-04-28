---
layout: page
title: "ComNSense"
description: Grammar-based generation of interior models by mobile participants
img: assets/img/comnsense_pic2.png
importance: 3
category: Completed
---

The ComNSense project has received funding from the German Research Foundation (DFG) and signifies a collaborative endeavor between the Institute of Distributed Systems and the Institute for Photogrammetry, both housed at the University of Stuttgart. This initiative underscores the interdisciplinary cooperation aimed at advancing the frontiers of knowledge within the respective fields.

The aim of this research project is to develop methods for the automatic creation of indoor models using recorded user positions and cooperatively captured camera images. The intention is to utilize the mobile devices located within a building to collect relevant building data via appropriate sensors and cooperatively integrate this data into an indoor model. These methods are designed to enable not only the automatic generation of indoor models but also their constant updating. Continuous updating is particularly crucial when it is necessary to account for movable objects, such as tables or obstacles, for example, a temporarily out-of-service escalator (identifiable, for instance, from current movement patterns that bypass the escalator in favor of regular stairs).

Within ComNSense, we are eager to develop energy-efficient reconstruction of building interiors by utilizing distributedly gathered user footprint data, coupled with the development of a specialized grammar tailored for the mapping and understanding of interior spaces. To this end, user footprints recorded via an inertial measurement unit attached to the foot were corrected using the model of the building's exterior shell. The detection of corridor segments based on steps taken along a straight line yields the corridor skeleton, which can serve to derive a Lindenmayer system or be completed by one. Moreover, the combination of the corridor skeleton with the building's exterior shell defines areas where rooms are located. Based on the spaces extracted as minimal bounding rectangles around the data, the Split-Grammar is applied to these non-corridor areas. This consists of rules for (repeatedly) subdividing the areas using intersecting lines and the probabilities of these rules. It was demonstrated that this approach eliminates the need for a predefined measuring behavior (such as walking along walls) and is capable of creating realistic floor plans from a small set of measurement data in a layout prescribed by the grammar.

Various methods were designed for the energy-efficient acquisition of indoor space models, with the dual aim of minimizing the number of capturing devices and activating energy-intensive sensors only when necessary during the actual data collection process. For this purpose, methods for cooperative positioning using WiFi anchor points were developed, which enable mobile devices to perform an energy-efficient coarse positioning and to deactivate the energy-intensive precise inertial navigation in areas that have already been captured.

 <div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/public_sensing.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Technical challenges addressed by the iEnergy project.
</div>

Furthermore, planning methods were designed to determine which devices actually need to perform data acquisition. Devices not engaged in data acquisition can deactivate energy-intensive sensors (e.g., IMUs for precise position determination). For this purpose, distributed planning methods were developed on one hand, allowing mobile devices to make autonomous decisions. With the aid of probability models, a device can decide which locations likely to be visited should be captured. This is particularly useful for the timely reactivation of accurate position sensors (IMU) before entering the area to be mapped. On the other hand, central planning methods were conceived, where a central planning component within the infrastructure assigns data acquisition tasks to devices based on global information. Predictive models were also utilized here to determine the smallest possible number of devices that can successfully perform data acquisition.

To facilitate central planning of data acquisition within the infrastructure, position information about mobile devices is required. To provide position information in an energy-efficient manner, a new method for position updating was designed that leverages the specific characteristics of mobile communication technologies. Through what are called opportunistic position updates, updates are avoided as much as possible during the IDLE state of the radio interface and are instead transmitted along with background traffic. This approach can often prevent the energy-intensive transition from IDLE to an active state.
