# ELTEL_POS_TRACKER

## Software Requirements Specification

### Introduction

This is a testing code project. Its purpose is to show coding and documentation capabilities.
It should produce a running application to visualize entities movement on a board including their properties – shape, color, size etc’.

#### Specs
  - Display the entities at initial coordinates - x,y (as stored in a json file)
  - Identify each entity by color, type, size and also name
  - On startup, all entities will be displayed and the user will have the option to hide / show entities from the display
  - A Start button will cause the entities to move until Stop button is pressed by the user.
  - The user can input ***n*** last steps to be saved when Stop button is pressed.  
  - The entities will move in 5 seconds intervals. That is, all entities will perform a movement every round by 5 sec intervals.
  - Movement specs:
      - Movement direction - 4 options Up, Down, Left, Right
      - Selected direction for each entity is random
      - Each movement measures 5 units (pixels)
      - The entity cannot go back to previous location on next step
  - When Stop button is pressed the app will save the ***n*** last steps that the user set as input.  

