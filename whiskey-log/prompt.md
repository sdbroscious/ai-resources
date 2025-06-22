# Please create a web app that allows a user (unauthenticated) to log whiskeys that they have tasted.

## Core requirements
For each whiskey logged, the user wants to capture these attributes:
* distiller
* city (of distiller)
* state (of distiller)
* country (of distiller)
* brand
* proof
* type of whiskey options shoudl include at least bourbon, rye, irish, scotch, whiskey, other
* mash bill: 
    * this should be comprised of a list of ingredients
    * each ingredient is a percentage value
    * all ingredients for a mash bill must equal 100%
    * ingredients can include corn, rye, barley, wheat, and other
* notes

## Additional requirements
- the user needs to be able to view, edit and delete a specific whiskey log entry
- the user needs to be able to see a list of all whiskeys (rows) and their attributes (columns)
- the user needs to be able to sort the list on any attribute

## Non-Functional requirements
- the backend and front end should both be executed with Python
- all code should be easily testable (tests will be added later)
- whiskey log data should be available across application sessions