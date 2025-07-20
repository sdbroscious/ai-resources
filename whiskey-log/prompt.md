> NOTE: I've moved this to the [whiskey log repo]() as a prd.md file in the documentation directory. The requirements below are no longer current.

# Please create a web app that allows a user (unauthenticated) to log whiskeys that they have tasted.

## Core requirements
For each whiskey logged, the user wants to capture these attributes:
* distiller
* city (of distiller)
* state (of distiller)
* country (of distiller)
* brand
* proof
* taste (should include 3 options: 1 (high), 2 (medium), 3 (low))
* type of whiskey options should include at least bourbon, rye, irish, scotch, whiskey, other
* mash bill: 
    * this should be comprised of a list of ingredients
    * each ingredient is a percentage value
    * all ingredients for a mash bill must equal 100%
    * ingredients can include corn, rye, barley, wheat, and other
        * when the user selects 'other' add a field set for ingredient label and percentage (this value should be included in the 100% requirement)
* notes

## Additional requirements
- the user needs to be able to view, edit and delete a specific whiskey log entry
- the user needs to be able to see a list of all whiskeys (rows) and their attributes (columns)
    - when it comes to the mash bill, there should be a column for each possible ingredient and actual percentage values shown in the appropriate column
- the user needs to be able to sort the list on any attribute
- the list and the view/edit/delete page should be separate pages with navigation back and forth between them
- the list view and whiskey page view should be modeled on the look and feel of the Apple mail app in iPadOS 18
- the user should be able to toggle back and forth between light and dark modes

## Non-Functional requirements
- the backend and front end should both be executed with Python
- all code should be easily testable
- whiskey log data should be available across application sessions
- all existing and new functionality should be covered by unit tests
    - coverage should not fall below 90% for the entire code base
    - all unit tests should assert something meaningful
- update the README file to reflect any new, deleted or changed functionality

Only execute instructions above that have not already been implemented
