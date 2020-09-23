# BioID

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org) 

``` 
 ______                  __     _____ 
/\  == \   __      ___   \ \   /\  == \
\ \  __<   \ \   /\ == \  \ \  \ \ \_\ \ 
 \ \_\_\_\  \ \  \ \____\  \ \  \ \_____\
  \/_____/   \_\  \/____/   \_\  \/_____/
```

BioID is a Biometric identity system that includes identity services based on .NET Core, .NET Framework and Python. In the other hand, it's also an attendance management application which allow you to upload your customer picture(s), and we recognition them for you automatically. Read [document](http://insightface.ai/) for more information.



## Public presentation
- [State of the art (2019) face detection with RetinaFace and MXNet
](https://medium.com/@fruty/state-of-the-art-2019-face-detection-with-retinaface-and-mxnet-18c86ebdce7e)
- [RetinaFace: Single-stage Dense Face Localisation in the Wild](https://arxiv.org/abs/1905.00641)
- [ArcFace: Additive Angular Margin Loss for Deep Face Recognition](https://arxiv.org/abs/1801.07698)


# Table of contents
- [Demos](#demos)
- [Business Context](#business-context)
- [OS, SDK, library, tooling and prerequisites](https://github.com/vietnam-devs/coolstore-microservices#os-sdk-library-tooling-and-prerequisites)
- [High level software architecture](https://github.com/vietnam-devs/coolstore-microservices#high-level-software-architecture)
- [Installation](https://github.com/vietnam-devs/coolstore-microservices#installation)
- [Licence](https://github.com/vietnam-devs/coolstore-microservices#licence)
## Demos
### Dataset manager (Customer details)
![home-page](ScreenShoot/ui-dataset-manager.PNG?raw=true)
### Image face recognition
![by-face](ScreenShoot/image-reg-ui.gif?raw=true)
### Video face recognition
![by-face](ScreenShoot/video-reg-ui.gif?raw=true)
## Business Context


## OS, SDK, library, tooling and prerequisites
### Infrastructure

- **`Windows 10`** - the OS for developing and building this demo application.
- **[`CUDA 10.1`](https://developer.nvidia.com/cuda-10.1-download-archive-base?)** - a parallel computing platform and programming model that makes using a GPU for general purpose computing simple and elegant.


### Back-end

- **[`.NET Framework 4.x`](https://dotnet.microsoft.com/download)** - .NET Framework 
- **[`Python 3.7.4`](https://www.python.org/downloads/release/python-374/)** - is a programming language that lets you work more quickly and integrate your systems more effectively.

### Front-end

- **[`jquery 3.4.x`](https://code.jquery.com/)** - JavaScript runtime built on Chrome's V8 JavaScript engine.
- **[`typescript`](https://www.typescriptlang.org)** - a typed superset of JavaScript that compiles to plain JavaScript.

## High level software architecture
![home-page](ScreenShoot/High-level-software-architecture.jpg?raw=true)

There are several individual services and infrastructure components that make up this app:

<table>
  <thead>
    <th>No.</th>
    <th>Service</th>
    <th>Description</th>
  </thead>
  <tbody>
     <tr>
      <td align="center">1.</td>
      <td>
        SSO (.NET Core)
      </td>
      <td>Authenization and token.</td>
     </tr>
     <tr>
      <td align="center">2.</td>
      <td>
        BioID (.NET Framework)
      </td>
      <td>UI and API used to manage dataset, devices..</td>
     </tr>
     <tr>
      <td align="center">3.</td>
      <td>
        CoreService(Python)
      </td>
      <td>Detect faces, calculate distances, extract features.</td>
     </tr>
  </tbody>
</table>


