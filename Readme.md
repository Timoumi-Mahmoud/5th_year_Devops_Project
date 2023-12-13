# Project DevOps of fifth year:


## Introduction

As part of fifth year project in Esprit university , I have implemented a CD/CI pipeline to an existing spring/Angular web application using Jenkins.

## Tools and technologies used in this project


- **Vagrant**:  IAC infrastructure as code vagrantfile contains two node one the Master node which contains the ansible roles and the other is the jenkins server.
- **Ansible**: ansible roles to installe various packeges such docker, docker compose, Java 11 , maven and Jenkins.
- **Jenkins**: Two nodes : the first one run locally as the jenkins master and the second as the worker node run in the cloud in Microsoft azure virtual machine.
- **Github**: contain Two private repository :
         1. FrontEnd with Angular
         2. BackEnd with spring
- Playit.gg: networking srevice that create enable to create a tunnel between localhost machine and a fixed public ip address. (this public ip address will be used in setting up webhook, and the comminucation betwing the Jenkins master(in premises) and jenkins agent  of-premises in azure )


## Architecture



![[Images/DevopsProjectArchitecture 1.png]]

## Steps:
- Step 1: Jenkins Pipeline Creation
- Step 2: Develop Unit Tests for the Backend Application   
- Step 3: Build Backend (Spring Boot)
- Step 4: Build Frontend (Angular)
- Step 5: Deploy Backend to Nexus
- Step 6: Run SonarQube Analysis
- Step 7: Push Docker Images to Docker Hub
- Step 8: Deploy Backend/Frontend with MySQL using  Docker Compose
- Step 9: Send Emails


## Realisation

`Jenkins Dashbord` 
![[1-JenkinsDash.png]]

`Jenkins Agent`
![[azure_dash.png]]

`connection between jenkins master and agent with JPNL and websocket`
![[connectionToAgent.png]]

`Setting webhook on push`
![[6-githubWebhook.png]]![[6-githubWebhookTWO.png]]  

`Docker compose of Promethues and grafana`
![[3-promtehus_grafana_nexusContainers.png]]

`Nexus dashbord (running inside a container)`
![[4-nexus.png]]


`Promethues info`
![[5-prometheus.png]]

`Grafana Dashbord`
![[grafana.png]]

![[grafanaTWO.png]]
`Pipeline Steps of the BackenD`
![[7-diagram.png]]
`Pipeline Steps of the FrontEnd`
![[diagramFront.png]]

`SonarQube`

![[Sonar.png]]

`Azure dns`
![[8-deploy.png]]

`Web application Accesable in the internet`
![[9-deploy.png]]

`The three containers of backend, front and Database`
![[containerInsideTheAgent.png]]

`Post pipline : Send notfication email `
![[emailnotification.png]]

![[notificationFront.png]]



