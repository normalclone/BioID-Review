# BioID

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org) 

``` 
 ______                  __     _____ 
/\  == \   __      ___   \ \   /\  == \
\ \  __<   \ \   /\ == \  \ \  \ \ \_\ \ 
 \ \_\_\_\  \ \  \ \____\  \ \  \ \_____\
  \/_____/   \_\  \/____/   \_\  \/_____/
```

BioID is a Biometric identity system including identity services based on .NET Core, .NET Framework, and Python. On the other hand, it also provides facial recognition service which allows you to upload your customer picture(s), and recognize them (on video, stream, image) automatically with high accuracy by using State of the Art algorithms. Read the [document](http://insightface.ai/) for more information.


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
### Conceptual Model
![conceptual-model](ScreenShoot/business_context.JPG?raw=true)

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
        <tr>
      <td align="center">4.</td>
      <td>
        VideoConsoleExecute (.NET Framework)
      </td>
      <td>Video maker.</td>
     </tr>
  </tbody>
</table>
## Technology

### RetinaFace

- RetinaFace is a practical single-stage **[`SOTA`](http://shuoyang1213.me/WIDERFACE/WiderFace_Results.html)** face detector which is initially introduced in **[`arXiv`](https://arxiv.org/abs/1905.00641)** technical report and then accepted by **[`CVPR 2020`](https://openaccess.thecvf.com/content_CVPR_2020/html/Deng_RetinaFace_Single-Shot_Multi-Level_Face_Localisation_in_the_Wild_CVPR_2020_paper.html)**.

- You can read more **[`here`](https://github.com/deepinsight/insightface/tree/master/RetinaFace)**

### ArcFace

#### - Data : 

- Refine the largest publicly available training data, MS-Celeb-1M, in both automatic and manual way.

#### - Network : 

- Taking VGG2 as the training data, the authors conduct extensive contrast experiments regarding the convolutional network settings and report the verification accuracy on LFW, CFP and AgeDB.

#### - Loss : 

- The authors propose a new loss function, additive angular margin (ArcFace), to learn highly discriminative features for robust face recognition.

#### - Performance : 

- The proposed ArcFace achieves state-of-the-art results on the MegaFace Challenge, which is the largest public face benchmark with one million faces for recognition.

### InsightFace

- `InsightFace` provides a complete implementation of both RetinaFace and ArcFace with a lot of pre-trained models.
- More information **[`here`](https://insightface.ai/)**

## Installation

### Step 1: 
- Install 
**[`Visual Studio`](https://visualstudio.microsoft.com/)**, **[`Python 3.7.4`](https://www.python.org/downloads/release/python-374/)**, **[`CUDA 10.1`](https://developer.nvidia.com/cuda-10.1-download-archive-base?)**

### Step 2:
- Install all required package in `CoreServices\FacialRecognition\requirements.txt`

### Step 3:
- Open `BioID.sln` with your `VS`. Then build `VideoExecuteConsole` to `BioID.Admin\App_Data`. You must put Certificate file to `BioID.Admin\App_Data` too.

### Step 4:
- Run terminal `python manage.py runserver --nothreading` in `CoreServices\FacialRecognition\Source`.

### Step 5: 
- Configure information in `Web.config`.
### Step 6:
- Run `BioID.Admin` and enjoy!

## System advantages
### Face Detection
- Very high accuracy.
- It can avoid the light and distance effects.
- Work well even the face is not frontal.

![face](https://github.com/deepinsight/insightface/raw/master/resources/11513D05.jpg)
### Face Recognition
- Don't like the other algorithm which is almost based on 128-d features (FaceRecongition, FaceNet...), we provide a very strong features extraction tool based on 512-d features per face.
- We just need 1 frontal face per user for the dataset.
- Our tool can avoid light effect well. (But good light effect still better)

## Known issues
- `Insight face` works on `mxnet`. Unfortunately, `mxnet` isn't support multithreading. So, we need to lock the Thread, but it will slow our process down.
- Even `Insight face` is a very strong features extraction tool, it's performance not good as expect (800ms/image with CPU; 300ms/image with GPU).
- The project works on .NET so It's limited to `Windows` OS.
## In the future
- Optimize facial recognition process.
- Update new technology while it's available.
## Citation

```
@inproceedings{deng2019retinaface,
title={RetinaFace: Single-stage Dense Face Localisation in the Wild},
author={Deng, Jiankang and Guo, Jia and Yuxiang, Zhou and Jinke Yu and Irene Kotsia and Zafeiriou, Stefanos},
booktitle={arxiv},
year={2019}
}

@inproceedings{guo2018stacked,
  title={Stacked Dense U-Nets with Dual Transformers for Robust Face Alignment},
  author={Guo, Jia and Deng, Jiankang and Xue, Niannan and Zafeiriou, Stefanos},
  booktitle={BMVC},
  year={2018}
}

@article{deng2018menpo,
  title={The Menpo benchmark for multi-pose 2D and 3D facial landmark localisation and tracking},
  author={Deng, Jiankang and Roussos, Anastasios and Chrysos, Grigorios and Ververas, Evangelos and Kotsia, Irene and Shen, Jie and Zafeiriou, Stefanos},
  journal={IJCV},
  year={2018}
}

@inproceedings{deng2018arcface,
title={ArcFace: Additive Angular Margin Loss for Deep Face Recognition},
author={Deng, Jiankang and Guo, Jia and Niannan, Xue and Zafeiriou, Stefanos},
booktitle={CVPR},
year={2019}
}
```
