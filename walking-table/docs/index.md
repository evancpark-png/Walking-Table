# Walking Table

This is a project by Evan Park and David Vaughn to create a walking table, inspired by [The Carpentopod](https://www.decarpentier.nl/carpentopod) by Niel de Carpentier. This project is also inspired by [The Strandbeest sculptures](https://www.strandbeest.com/) by Theo Jansen where our leg design is derived from. The end goal of the project is to have a table that can walk, similar to The Carpentopdo, but also be able to utilize a camera to respond and navigate their enviorment. The hope is that the table could have actions where it could see a person or thing in the camera and respond mechanically.

## Other Documentation

The documentation that I created for the project while working on it during October 2024 - April 2025 can be found [here](https://sites.google.com/charlottelatin.org/evan-park/home/bioengineering/the-walking-table)

## Overview

### Design Specifications

The table will be about 12x48'' and about 12'' tall. It will be made primarily of wood, but there will be PLA and Aluminum used in some of the jointery. It will have a living hinge to conceal the electronics (two high torque motors and a Raspberry Pi). The Raspberry Pi will have a camera sensor to analyze it's enviorment. 

### Materials List

| Walking Table 2025 Bill of Materials (BOM) |
| ------------------------------------------ |
| Name:                                      | Evan Park | Period | A |  |  |  |  |
| Project Title                              | Walking Table |  |  |  |  |  |  |
| Item #                                     | Description | Vendor | Part Number | Qty | Cost | Link to Where to Purchase |  |
| ,5'' 96x48 Plywood                         | To CNC into legs and frame | Home Depot |  | 3 | $136.50 | [https://www.homedepot.com/p/SANDEPLY-12mm-Sande-Plywood-1-2-in-Category-x-4-ft-x-8-ft-Actual-0-472-in-x-48-in-x-96-in-454532/203414055](https://www.homedepot.com/p/SANDEPLY-12mm-Sande-Plywood-1-2-in-Category-x-4-ft-x-8-ft-Actual-0-472-in-x-48-in-x-96-in-454532/203414055) |  |
| 3/8''_5/8'' Shoulder Bolt                  | For joints | Amazon |  | 10 | $17.00 | [https://www.amazon.com/Socket-Shoulder-Screws-Bolts-25MM/dp/B009TE1K4S](https://www.metalsdepot.com/aluminum-products) |  |
| 5mm Aluminum Rod                           | For crankshaft | Metals Depot |  | 4ft | $20.00 | [https://www.metalsdepot.com/aluminum-products](https://www.metalsdepot.com/aluminum-products) |  |
| F625ZZ Flanged Bearings                    | 5mm ID, 16mm OD | Amazon |  | 18 | $14.00 | [https://www.amazon.com/uxcell-Flange-Bearing-Shielded-Bearings/dp/B08CK6LM8Q](https://www.amazon.com/uxcell-Flange-Bearing-Shielded-Bearings/dp/B08CK6LM8Q) |  |
| 5mm Shaft Collars (Set Screw)              | To keep crankshaft from sliding | Amazon |  | 10 | 15$ | [https://www.amazon.com/Ruland-MSC-5-F-Screw-Collar-Metric/dp/B0063KWEDW](https://www.amazon.com/Ruland-MSC-5-F-Screw-Collar-Metric/dp/B0063KWEDW) |  |
| 12V DC Geared Motor (20-50 RPM)            | High torque, low RPM geared motor. 20-50 RPM ideal for walking speed | Amazon |  | 2 | $80.00 | [https://www.amazon.com/Electric-Torque-Reduction-Centric-Output/dp/B0728HDH45](https://www.amazon.com/Electric-Torque-Reduction-Centric-Output/dp/B0728HDH45) |  |
| Raspberry Pi 5 4GB                         | For computing the visual inputs | Adafruit |  | 1 | $77 | [https://www.adafruit.com/product/5812](https://www.adafruit.com/product/5812) |  |

#### Final Estimate

The final estimate is $359.50 

### Machines, Software, and Tools

The machines I will be using to create the walking table will be primarily the ShopBot. I might end up using other tools to create the legs but the main machine I will be using will be the ShopBot. I will occasionally use the bandsaw and sander to smooth and shape the legs if needed. 

Fusion360 and Aspire will be the main softwares I will be using to design and cut my legs. I will design my files parametrically in Fusion360 and take the dxf files into Aspire to create the toolpaths for the ShopBot.

The tools I will need for this project is a bolt fastener for the joints, hex nut fasteners for the motor flanges, and wood glue to put together the layers for each leg. 


## 3D Motion Model

From our physical prototype, there seemed to be an issue with the amount of force the legs are producing in order for the table to walk and the smoothness of the motion. By smoothness, parts of the walk cycle would go faster than normal when suspended in the air. This issue could be due to the effect of gravity assisting on portions of the cycle while being a detriment on other parts. In order to find the cause of this. We decided to put together a motion model of our pieces to make sure there aren't any issues that are tied to the CAD design of the legs. If we don't find any issues with the model, we can assume it is a assembly issue. Luckily, we put together some 3D models of each piece of the leg so creating the 3D model of the entire leg was simple. 

In Fusion 360, I put the pieces together in separate components.

### Single Leg (September)

![leg_model_fusion](/walking-table/docs/images/fusion_model.png)

Then I started on working on trying to make the model. I made a revolving joint where the jimmy is placed and attempted to ground the part of the thigh that needed to be grounded. I had a lot of issue with trying to get the model to work.

I then learned that both grounds for the the leg needed to be a revolute joint type and be pinned so that they cannot move. This allowed the single leg to work.

https://github.com/user-attachments/assets/0f659eb2-71fe-4b76-a008-0f084a4013fa

### Double Leg (October 1st - 15th)

The double leg required me change the single leg file a little bit so that the pieces that connect to the motor can all fit. Using the single leg motion file, I was able to easily create a second leg by mirroring the components across the middle of the leg. I then constrained the mirrored components and added the joints the same way that I did for the single leg.

https://github.com/user-attachments/assets/6a0d1ccd-b37a-4eaf-acc6-456f574038d4

### Half-Table (November-December 10th)

Making the half table was more complicated than I expected. I thought the process would be as simple as copy and pasting the double leg twice and adding more joints but I kept running into problems.

#### Grounding & Reworking Crankshaft

There was a few issues with grounding my pieces at first. Deleting my grounds that I had previously would require me to unlink my pieces to the design I had made for them which would create issues later down the line. To fix this, I had to recreate the legs with new grounds. Before I did this, I had to tackle another issue.

The crankshaft was creating problems when I tried to connect each individual piece together. To fix this, I designed the entire cranksahft and imported it into the file. I then rebuilt the legs which was a much easier process once I had fixed these two things.

https://github.com/user-attachments/assets/64f976b2-2913-4219-aeee-ac5f481f202a

## Download CAD Files

You can download all the CAD files I created [here](/walking-table/docs/downloads/EP-Leg_CAD.zip)

## Reworking Design (December)

Now that I know that our design works theoretically, I wanted to make a few changes to the design. Because our design should be working, that means that there has to be a problem with how we are assembling the table. One of the most obvious problems would be our crankshaft. The first step to fixing this issue being is to add bearings again. I reasoned that the only spots that needed bearings were the crankshaft and where the grounds connect because this is were most of the load on the table legs go so improving these joints would make the leg turn much smoother. I decided to go with flanged bearings that I can glue or screw to the leg to keep them tight and not move. With the changes I want to make known I can find my materials required to develop the project. 

Another piece that I would want to rework is our D-Shafts. During testing last year, I understood that our D-shafts would deform and not fully stay in place. Now that I am adding bearings, I can attempt to use aluminum shafts for the connections to the crankshaft. This could potentially solve our issue because the shafts would be much more robust leading to less issues with the amount of load our crankshaft can handle. 

## New Motor

Since our legs are working in our CAD model, we decided to see if our motor was the problem. We decided to get higher torque motors to see if our legs would walk if they had more force. The motor flanges were stuck to our d-shafts due to deformation of the d-shafts so we had to get vice grips and a crowbar to pry the flanges off the d-shafts for each flange.

![](/walking-table/docs/images/deformed_shaft.jpg)