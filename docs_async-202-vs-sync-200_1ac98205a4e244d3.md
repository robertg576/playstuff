> Source: https://docs.ns-api.com/docs/async-202-vs-sync-200

The netsapiens api by default will submit requests to its service bus for replication to all nodes/servers for saving to the DB's and applying to the real time memory for immediate use in the application. For most writes (Creates/POST, Updates/PUT, Deletes/DELETE) the success response code will be 202, meaning Accepted. This success message should be treated as a full success with an immediate ability to use the new resources.

In the cases where you want to get the full resource data including any defaults that might have been applied from the system you can request a Synchronous request where a 200ok will be retuned instead of a 202 with a full JSON response in the same format as a Read/GET of that specific item. The Synchronous requests are only available today on Creates (POSTs) and on certain APIs listed below.

* Resellers
* Domains
* Users
* Devices
* Callqueues
* Agents
* Answerrules
* Contacts
* Dialrules
* Audio (Moh/Greeting) upload/tts
* Timeframes
* Event Subscriptions
* Calls - Click to Call requests