# update.js

## What is update.js?
update.js is a solution to the problem of how to update distributed instances of the ![FlightHub Crew Center](https://github.com/vacenter/vacenter). This can be used on other projects assuming a similar architecture.

## How does it work?
update.js works in 2 parts, a centralised update server, and the instance updater module.

## Update Server
The update server is an API and Web Admin Panel that allows developers to push new updates to instances. Each update contains the following details:
| Name | Description |
| ------------- | ------------- |
| Branch  | Related github branch name  |
| SQL Statments | SQL statments to execute |
| Protected files | Protected files not to overwrite during install |
