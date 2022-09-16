---
title: Component Model
date: 2022-09-15
categories: []
tags: []
---



# Component Model Overview

A component in marketplace could be viewed as an application wrapped subsequently in the several layers of infrastructure and security functionality.

Below is presented a detailed overview of how a component could be seen form the marketplace producers and users point of view.

## High Level Diagram

On the high level a component model consist of at 3 layers:

* Security layer. Here are all the permissions needed to access the cloud resources. 
* Infrastructure layer. It could be a custom component like EKS deployment enabling some customizable resources like compute storage and networking for the specific application. This layer is interact with security and api specifics of underlying infrastructure like could or DC and hides it from the higher level components. From the Markeplace users point of view the components is shipped ready-to-use with all the permissions out-of-the-box 
* Application or Functional layer. The Application component sits on the top of the stack and needs a minimal sets of permissions to pick form marketplace and deploy.

![Abstract Component](/assets/abstract_component.png "Abstract component diagram")

## Jenkins Component Sample Implementation

An example of multy-layer component model on the Marketplace could be a Jenkins CI/CD pipeline implementation. In this case there would be more than one Infrastructure Components so the stack would consists of 4 layers:

* A Security component is a bundle of all security permissions needed to run the overlaying EKS cluster 
* First-level Infrastructure component is a EKS cluster. We consider it a component as it could be published on Marketplace on its own although it could bear some application value only for the Infrastructure/devops team. The most of developer team would normally need to use higher level components for their application needs.
* Second-level infrastructure component is a Jenkins CI/CD. Particularly when implemented as a code (JCasC) Jenkins could be shipped as a all-code defined software component convenient to deploy to Kubernetes and further customize and store under the version control without need in any manual changes of operations team.
* Application component. In this case is a specific implementation of Jenkins pipeline. It is implemented as a code as well thanks to Jenkinsfile. Such a component could be reviewed as a application-level utility enabling some developers team to setup some CI/CD pipeline by themselves, with no need of operations team intervention.

![Jenkins sample implementation](/assets/jenkins_component.png "Jenkins sample implementation")


```javascript
console.log("hello world!");
```
