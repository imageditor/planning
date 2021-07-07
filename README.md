# Task

Design and implement an auto scalable microservice architecture and deploy it on aws.

_Requirements:_
- [ ] User can create projects
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
- [ ] Frontend: React
- [ ] Backend: Node.js
- [ ] the processingWorker which converts the images to grayscale, this should be in python
- [ ] Databases: Choose what you think is the best for this usecase (MongoDB chosed)
- [ ] All Microservices should be dockerized
