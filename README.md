# Contents
- [Task](#task)
- [AWS Diagram](#aws-diagram)
- [Local planning](#local-planning)
- [Exchange rooles](#exchange-rooles)

# Task
Design and implement an auto scalable microservice architecture and deploy it on aws.

_Requirements:_
- [x] User can create projects
  - [x] _deploy on AWS_
- [x] User can upload images into projects
- [x] User can view the uploaded images
- [x] User can select images to process them
- [x] The processing should be a simple change to the image, for example a conversion to grayscale.
- [x] After processing is done user can also view the results.
- [x] All images should be stored on s3 (input + output)
- [x] The communication between the microservices should be selected in such a way that no important information is lost. For example, information about successful processing should not be lost even if certain services are briefly unavailable.

_Technologies to be used:_
- [ ] ~Kubernetes for Container Orchestration~
- [x] ECS
- [x] API gateway for routing
- [x] Frontend: React
- [x] Backend: Node.js
- [x] the processingWorker which converts the images to grayscale, this should be in python
- [x] Databases: Choose what you think is the best for this usecase (MongoDB chosed)
- [x] All Microservices should be dockerized

[GoUp](#contents)

# AWS Diagram
![image](https://user-images.githubusercontent.com/75684216/124797695-39d1c980-df5b-11eb-889c-27557b0c33e9.png)

[GoUp](#contents)

# Local planning
- [x] Create project Step-By-Step tutorial
- [x] [Project-manager-backend](https://github.com/imageditor/project-manager-backend)
   - API port 8088
   - CORS origin port 8089
- [x] [Project-manager-frontend](https://github.com/imageditor/project-manager-frontend)
   - port 8089
   - [x] project add/list/edit
      - [x] improve UI
- [x] [Image-manager](https://github.com/imageditor/image-manager)
  - API port 8086
  - CORS origin port 8087
- [x] upload and resize AWS Lambda
- [x] AWS GW
- [x] grayscale ASW Lambda


[GoUp](#contents)

# Exchange rooles

## Запуск процессинга

## `POST IM_SERVICE_HOST:IM_SERVICE_PORT/api/processing/`

### Upload

#### Request (**FormData**)
```
{
    projectId: string,
    processingType: 'upload',
    image: File (Buffer?)
}
```

#### Response (**JSON**)
```
{
    newId: uuidv4,
    status: 'recieved' | 'error',
    payload: {
        message: string,
        data: object
    }
}
```

### Grayscale

#### Request (**FormData**)
```
{
    id: uuidv4,
    projectId: string,
    processingType: 'grayscale'
}
```

#### Response (**JSON**)
```
{
    newId: uuidv4,
    status: 'recieved' | 'error',
    payload: {
        message: string,
        data: object
    }
}
```

[GoUp](#contents)


