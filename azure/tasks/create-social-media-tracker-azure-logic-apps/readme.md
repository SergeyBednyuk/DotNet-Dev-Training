# Create a social media tracker with Azure Logic Apps

## Short Description

In this exercise, you'll create your social media monitoring logic app using the Azure portal.
[Exercise in sandbox](https://learn.microsoft.com/en-us/training/modules/route-and-process-data-logic-apps/4-ex-create-social-media-tracker)

## Estimation (h)

4

## Topics

* Azure Logic Apps

## Requirements

* Create the logic app resource with the following properties:
  * Subscription: Concierge Subscription
  * Resource Group: If you don't use the Sandbox, select yours, otherwise select the sandbox resource.
  * Logic app name: ShoeTracker (or whatever you want)
  * Region: Select a location nearest you.
  * Type: Consumption
* Add a twitter trigger
  * Find appropriate trigger in the search box ("When a new tweet is posted")
  * Create connection to your Twitter Account
  * Authorize in your Twitter Account
  * Configure trigger parameters:
    * Search text: The text to find in the tweet.
    * (Interval) : The number of time units to wait until the next check.
    * (Frequency) : The time unit to use for the polling interval.
* Check the output of your trigger
