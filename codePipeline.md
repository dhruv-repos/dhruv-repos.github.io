---
title: AWS Codepipeline
layout: default
---
# AWS CodePipeline
It is a *continuous delivery* service used to model visualize and automate the steps required to release your software.

## Continuous Delivery
Continuous delivery is a software development practice where code changes are automatically prepared for a release to production.

>Continuous delivery automates the entire software release process. Every revision that is committed triggers an automated flow that builds, tests, and then stages the update. The final decision to deploy to a live production environment is triggered by the developer.

## Continuous Integration
Continuous integration is a DevOps software development practice where developers regularly merge their code changes into a central repository, after which automated builds and tests are run.

## CodePipeline Concepts
1. Pipeline : Workflow that describes how software changes go through a release process.
2. Stages : Logical unit to isolate an environment. Performs actions on artifacts.
Made up of a series or parallel "actions".
3. Transitions : Moving to the next stage in the pipeline.
4. Actions : set of operations on the application code. Action types : ``` 
source, build, test, deploy, approval, and invoke. ```

5. Execution Modes : 
    - SUPERSEDED
    - QUEUED
    - PARALLED

# CodeBuild
Managed build service, to compile source code , run unit tests and produce artifacts. 
*A buildspec is a collection of build commands and related settings, in YAML format, that CodeBuild uses to run a build.*
