# Open Ticket

A small, fast and simple Ticket Service designed to solve common problems.

## Problems

There are many problems in many ticket-systems today.  
This Project wants to solve them.

### Ticket IDs not human readable

Long IDs, like 20190708000025634 seem simple, but are hard to give via phone or to remember.

Our solution is to accompany each Ticket with a human readable ID like this:  
`42-red-big-horses`  
NUMBER [10-99]-adjective-adjective-noun(plural)

A Hash is created to have a unique ID.

### Custom Fields

You want to have some custom fields for some tickets but not for all.

Our solution is to save each ticket as JSON-Object, so we can simply add, remove or rename fields here.

### Renaming of Info

You add a service to a ticket, but the service is renamed later.  
But your ticket should be known under the old service...

No Problem as we keep the info hard in a json. No Problem exporting the Ticket either!

### Rights Management

In many solutions, there are big matrices to give everyone the right he needs or not.

We make this very simple, as there are only 4 groups of people:

* public (everyone, can open a ticket an see his own)
* agent (can edit tickets)
* manager (can create reports)

On Top, these groups can be attached to LDAP-Groups or just be filled with users themselves.

Wait, no Admins? Yes, everything they need to change are files on disk. This is the only way to configure the services.

### Ticket History

Ticket shall not be tempered with to keep the history consistat

So everytime you add info to a Ticket or edit it, we add this block of information (timestamp, key, value, user) to a chain in the ticket, complete with a hash build from the former blocks.

Sounds like a Blockchain? Think of every Ticket like a mini-Blockchain!

### Services

You want to attach every ticket to a service from your catalouge.

We have a simple microservice to publish those!

### External Data

You want to add external data (like an item from your CMDB) to a ticket.

Simply use our externalData-Microservice to configure an endpoint to use (this is effectively a source-to-json service)

### Automation

We want stuff to happen on tickets, like send a mail on creation or close it after some days. Or deploy a server if the correct fields are there.

All this can be done using the automation-Microservice with the config

### Config and Documentation

All Config-Files are JSON-Files on your Disk.

We Recommend using git to keep track of changes.