---
title: AWS Lambda
layout: default
---
# AWS Lambda
Event-based serverless computing service. Event driven functions are compute events that happen automatically in response to various inputs known as triggers

Use stateless style of coding .
- MEans each function run is independent of the previous executions. It has no knowledge of past calls.
If data needs to persist it must be stored in an external system. Running the same function multiple times with the same input should give the same result

Event based :
it only runs in response to an event instead of running continuously.
Supports auto scaling of the tasks involved. AWS takes care of autoscaling the tasks

EC2- virtual machine , it is IAAS. Longer running services.Needs manual autoscaling. Pay for the entire time that it was running. Manage the infra by yourself: os,updates, security. Long running tasks.


Runtimes :
pre configured execution environment that allow to run out code  in a specific programming language
 Includes : programming language
libraries and dependencies
execution environment


