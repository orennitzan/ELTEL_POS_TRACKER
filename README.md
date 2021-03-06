# ELTEL_POS_TRACKER

## Software Requirements Specification

### Introduction

This is a testing code project. Its purpose is to show coding and documentation capabilities.
It should produce a running application to visualize entities movement on a board including their properties – shape, color, size etc’.

### Specs
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

  ### Specs Notes
  - The display grid is 100x100 (i.e. 0<=X<=100; 0<=Y<=100)
  - There are three supported colors (red, green, blue)
  - There are three supported entity types (circle, square and triangle)
  - There are three supported entity sizes (small, medium, large)
  - Max number of supported entities is 10
  - JSON input file will be located at executable folder (testing input may vary).
  
  ### Specs Technical Notes
  - The display grid is 100x100 is a gray square, located in a somewhat larger one to enable display of a shape that its center is at 0, 0 for example.
  - Display 0,0 location is bottom-left corner. Up/Down change at Y axis. Right/Left at X axis.
  - Entity is a user control that combines an image of a shape and a label (entity id).
  - The entity coordination represents the *center* of the shape.
  - The note above **can** cause a shape to exceed the borders.
  - The note above means that the
  - Entity must remember, at minimum, its last location to prevent moving backwards, or at maximum ***n*** steps.
  - We assume that as a default the app should save, at minimum, its current location at stop.
  
  ### Project structure and responsibilities
  The solution contains 2 projects:
  - Pos_Tracker_Core
  - Pos_Tracker_View (UI). Has a reference to core. 
  
  ####  Pos_Tracker_Core
  ***Holds***:
  - The entities class
  - The data access (load / save)
  - Data model - the list of entities.
  - The buisnes logic / Manager class (change locations, validations etc') 
  
  
  ####  Pos_Tracker_View
  ***Holds***:
  - Manager win form / wpf form.
  - Entity user control.
  - Start/Stop events handlers.
  - Show/Hide entities handlers.
  - ***n*** steps user input
  - Timer - call reposition method in Core manager class and refresh the display.
  
  #### Thoughts and Uncertainties
  - Not sure whether to use win form or wpf?? It depends what control can position user controls onto itself and also able to draw a line of last ***n*** steps.
  - I think the best is for the model to change and the view automatically change with it - BINDINGS. Not sure how to do it for now.
  - What should the user control look like? Image on a flat button? a graphic shape? Need to check options.
  - Where does the timer sit. Timer in the UI is a logic!!. 
  
  
  
 
