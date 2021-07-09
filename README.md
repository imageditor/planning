# Contents
- [Task](#task)
- [AWS Diagram](#aws-diagram)
- [Detailed planning](#detailed-planning) 

# Task
Design and implement an auto scalable microservice architecture and deploy it on aws.

_Requirements:_
- [x] User can create projects
  - [ ] _deploy on AWS_
- [ ] User can upload images into projects
- [ ] User can view the uploaded images
- [ ] User can select images to process them
- [ ] The processing should be a simple change to the image, for example a conversion to grayscale.
- [ ] After processing is done user can also view the results.
- [ ] All images should be stored on s3 (input + output)
- [ ] The communication between the microservices should be selected in such a way that no important information is lost. For example, information about successful processing should not be lost even if certain services are briefly unavailable.

_Technologies to be used:_
- [ ] Kubernetes for Container Orchestration
- [ ] API gateway for routing
- [x] Frontend: React
- [x] Backend: Node.js
- [ ] the processingWorker which converts the images to grayscale, this should be in python
- [x] Databases: Choose what you think is the best for this usecase (MongoDB chosed)
- [ ] All Microservices should be dockerized

[GoUp](#contents)

# AWS Diagram
![image](https://user-images.githubusercontent.com/75684216/124797695-39d1c980-df5b-11eb-889c-27557b0c33e9.png)

[GoUp](#contents)

# Detailed planning
- [ ] Create project Step-By-Step tutorial
- [x] [Project-manager-backend](https://github.com/imageditor/project-manager-backend)
   - API port 8088
   - CORS origin port 8089
- [ ] [Project-manager-frontend](https://github.com/imageditor/project-manager-frontend)
   - port 8089
   - [x] project add/list/edit
      - [ ] improve UI
- [ ] [Image-manager](https://github.com/imageditor/image-manager)
  - API port 8086
  - CORS origin port 8087



[GoUp](#contents)
