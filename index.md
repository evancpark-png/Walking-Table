# Walking Table

This is a project by Evan Park and David Vaughn to create a walking table, inspired by [The Carpentopod](https://www.decarpentier.nl/carpentopod).

## 3D Motion Model

From our physical prototype, there seemed to be an issue with the amount of force the legs are producing in order for the table to walk and the smoothness of the motion. By smoothness, parts of the walk cycle would go faster than normal when suspended in the air. This issue could be due to the effect of gravity assisting on portions of the cycle while being a detriment on other parts. In order to find the cause of this. We decided to put together a motion model of our pieces to make sure there aren't any issues that are tied to the CAD design of the legs. If we don't find any issues with the model, we can assume it is a assembly issue. Luckily, we put together some 3D models of each piece of the leg so creating the 3D model of the entire leg was simple. 

In Fusion 360, I put the pieces together in separate components.

![leg_model_fusion](/walking-table/docs/images/fusion_model.png)

Then I started on working on trying to make the model. I made a revolving joint where the jimmy is placed and attempted to ground the part of the thigh that needed to be grounded. I had a lot of issue with trying to get the model to work.

## New Motor

(This part can change depending on the results of the 3D model, this documentation is assuming that our model would theoretically work as shown in the CAD model)

Since our legs are working in our CAD model, we decided to see if our motor was the problem. We decided to get higher torque motors to see if our legs would walk if they had more force to push. The motor flanges were stuck to our d-shafts due to deformation of the d-shafts so we had to get vice grips and a crowbar to pry the flanges off the d-shafts for each flange.

(PHOTO OF AFTER DISASSEMBLED AND DEFORMED D-SHAFT)