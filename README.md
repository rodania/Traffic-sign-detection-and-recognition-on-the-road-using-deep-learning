# Traffic-sign-detection-and-recognition-on-the-road-using-deep-learning
Integrating two deep neural networks to detect and recognise traffic signs

<img src="./video.gif">


<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#introduction">Introduction</a>
    </li>
    <li>
      <a href="#tools">Tools</a>
    </li>
    <li><a href="#data">Usage</a></li>
    <li><a href="#methodology">Methodology</a></li>
    <li><a href="#results">Results</a></li>
  </ol>
</details>

### Introduction
Traffic sign recognition and classification is an essential technique in Self-Driving Car engineering. It is the process of automatically detecting and recognising traffic signs along the road. 

Sign recognition is a two part process. First process is to recognise there is a traffic sign on the road, and then localise it. The second is to find out which sign it is. The model here integrates two deep neural networks for each process. 

### Tools:
Python 3, Tensorflow, Pandas, Numpy

### Data:
The German Traffic Sign Detection Benchmark(GTSDB), the German Traffic Sign Recognition Benchmark (GTSRB).
The images in (GTSRB) dataset are in low resolution, have a poor contrast, and pixelated. Some images are very hard even for the human eye to recognize the sign. Image processing was needed before training the model.

### Methodology:
**The first model** is a retrain of *YOLO* model, aiming at detecting and locating traffic sign. The trained model can be found at this <a href="https://github.com/rodania/Traffic-sign-localisation-using-YOLO4">link</a>.

**The second model** is a deep convolutional network, trained to recognise the sign label. The model can be found at this <a href="https://github.com/rodania/Sign-Traffic-recognition">link</a>.

The video produced from the detecting camera is passed frame by frame tho the first model, which is trained to find the signs along the road. When a sign is found, it localises its, crops the image to the boundary of the detected box, and passes it to the second model. The second model process the image and classify the sign by giving it a label. The labels is printed on the streaming video.

### Results

The overall accuracy on the test dataset is 96%. A test video is showing below.

<img src="./detecting_video.gif">
