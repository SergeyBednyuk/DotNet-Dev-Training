# Trigger a logic app by using Event Grid

## Short Description

Use Event Grid to connect it to logic apps.
[Exercise in sandbox, Part 1](https://learn.microsoft.com/en-us/training/modules/react-to-state-changes-using-event-grid/3-exercise-trigger-logic-app)
[Exercise in sandbox, Part 2](https://learn.microsoft.com/en-us/training/modules/react-to-state-changes-using-event-grid/5-exercise-email-vm-change)

## Estimation (h)

4

## Topics

* Azure Logic Apps
* Event Grid

## Requirements

* Create VM, it will be the events' source
* Create a Logic App, it will react on VM events
* Add an Event Grid trigger to the logic app
  * Find in the search box Azure Event Grid
  * Configure Event Grid
* Add a condition for event from Event Grid
  * Find Condition control and add it
  * Configure Condition by adding condition expression
* Add an email send step
* Test workflow
