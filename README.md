# update.js

## What is update.js?
update.js is a solution to the problem of how to update distributed instances of the [FlightHub Crew Center](https://github.com/vacenter/vacenter). This can be used on other projects assuming a similar architecture.

## How does it work?
update.js works in 2 parts, a centralised update server, and the instance updater module.

## Update Server
The update server is an API and Web Admin Panel that allows developers to push new updates to instances. Each update contains the following details:
| Name | Description |
| ------------- | ------------- |
| Branch  | Related github branch name  |
| SQL Statments | SQL statments to execute |
| Protected files | Protected files not to overwrite during install |

## Updater Module
The updater module is an NPM module that can be installed and run on target instances. The module will ask for 2 parameters, the URL of the Updater Server, and what branch it should be looking at. The Module will never automatically update, and can only be manually run.

The updater will have 4 main functions:

| Name | Description |
| ------------- | ------------- |
| Init  | Initialise the module  |
| Check | Check for updates |
| Download | Download the update zip file |
| Install | Unpack the zip file, and execute SQL |

It will also have the following events:
| Name | Description |
| ------------- | ------------- |
| downloading  | Download in progress with new percentage value for download  |
| downloaded | Download of zip file finished |
| installed | Zip file unpacked, SQL execute successfuly, ready for restart |
| partialInstall | Zip file unpacked, SQL failed to execute successfully |
| error | Error with the install |
