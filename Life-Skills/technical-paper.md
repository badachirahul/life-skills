# Event Sourcing Architecture

## What is "Event Sourcing"?
   * Event sourcing is an architecture pattern, instead of storing current state of data we store every change as an event.

## Why it's important to use "Event Sourcing"?
   * To store full history of changes.
   * To avoid losing important data.
   * To track who changed what and when.
   * To help in debugging problems. 

## Where "Event Sourcing" is Used:

* Banking systems to track transactions  
* Payment applications for full history  
* E-commerce systems for order changes  
* Financial systems for auditing  
* Large applications where every change matters  


## Example of event sourcing 
### 1. Registration System **Before** Event Sourcing:
* The system saves only the latest user data.
* ex: 
    * User registers: 
        - Name: Rahul
        - Email: rahul@gmail.com
        - Status: Active

    * Update Email: 
        - Email: rahulsb@gmail.com

        - Here, old email is lost
        - No history saved
            
    * Problems we face: Cannot track changes, Hard to audit etc.
    * To avoid this we go for event sourcing.

### 2. Registration System **After** Event Sourcing:
* The system saves every action as an event.
* ex: 
    * User registers: 
        - Name: Rahul
        - Email: rahul@gmail.com
        - Status: Active

    * Update email 2 times: 
        - EmailUpdated: New Email: rahul123@gmail.com  
        - EmailUpdated: New Email: rahul_new@gmail.com

    * All emails are stored as history. The current email is taken from the latest event.

### Difference
* Before Event Sourcing: Only final data is saved  
* After Event Sourcing: All changes are saved as events  
                   
## References
* https://www.geeksforgeeks.org/system-design/event-sourcing-pattern/
* https://www.youtube.com/watch?v=ID-_ic1fLkY