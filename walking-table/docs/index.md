# Walking Table

This is a project by Evan Park and David Vaughn to create a walking table, inspired by [The Carpentopod](https://www.decarpentier.nl/carpentopod). The purpose of the project is to have a table that walks using motor control and can utilize a camera to respond to their environment.

## 3D Motion Model

From our physical prototype, there seemed to be an issue with the amount of force the legs are producing in order for the table to walk and the smoothness of the motion. By smoothness, parts of the walk cycle would go faster than normal when suspended in the air. This issue could be due to the effect of gravity assisting on portions of the cycle while being a detriment on other parts. In order to find the cause of this. We decided to put together a motion model of our pieces to make sure there aren't any issues that are tied to the CAD design of the legs. If we don't find any issues with the model, we can assume it is a assembly issue. Luckily, we put together some 3D models of each piece of the leg so creating the 3D model of the entire leg was simple. 

In Fusion 360, I put the pieces together in separate components.

### Single Leg

![leg_model_fusion](/walking-table/docs/images/fusion_model.png)

Then I started on working on trying to make the model. I made a revolving joint where the jimmy is placed and attempted to ground the part of the thigh that needed to be grounded. I had a lot of issue with trying to get the model to work.

I then learned that both grounds for the the leg needed to be a revolute joint type and be pinned so that they cannot move. This allowed the single leg to work.

https://github.com/user-attachments/assets/0f659eb2-71fe-4b76-a008-0f084a4013fa

### Double Leg

The double leg required me change the single leg file a little bit so that the pieces that connect to the motor can all fit. Using the single leg motion file, I was able to easily create a second leg by mirroring the components across the middle of the leg. I then constrained the mirrored components and added the joints the same way that I did for the single leg.

https://github.com/user-attachments/assets/6a0d1ccd-b37a-4eaf-acc6-456f574038d4

### Half-Table

Making the half table was more complicated than I expected. I thought the process would be as simple as copy and pasting the double leg twice and adding more joints but I kept running into problems.

#### Grounding & Reworking Crankshaft

There was a few issues with grounding my pieces at first. Deleting my grounds that I had previously would require me to unlink my pieces to the design I had made for them which would create issues later down the line. To fix this, I had to recreate the legs with new grounds. Before I did this, I had to tackle another issue.

The crankshaft was creating problems when I tried to connect each individual piece together. To fix this, I designed the entire cranksahft and imported it into the file. I then rebuilt the legs which was a much easier process once I had fixed these two things.

https://github.com/user-attachments/assets/64f976b2-2913-4219-aeee-ac5f481f202a

<video width="320" height="240" controls>
  <source src="walking-table\docs\images\ep-halftable_motion.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

## Reworking Design

Now that I know that our design works theoretically, I wanted to make a few changes to the design. The first being that I wanted to add bearings again. I reasoned that the only spots that needed bearings were the crankshaft and where the grounds connect because this is were most of the load on the table legs go so improving these joints would make the leg turn much smoother. I decided to go with flanged bearings that I can glue or screw to the leg to keep them tight and not move. 

## New Motor

(This part can change depending on the results of the 3D model, this documentation is assuming that our model would theoretically work as shown in the CAD model)

Since our legs are working in our CAD model, we decided to see if our motor was the problem. We decided to get higher torque motors to see if our legs would walk if they had more force to push. The motor flanges were stuck to our d-shafts due to deformation of the d-shafts so we had to get vice grips and a crowbar to pry the flanges off the d-shafts for each flange.

(PHOTO OF AFTER DISASSEMBLED AND DEFORMED D-SHAFT)