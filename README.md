# darknet-cpp-windows

Windows support for Darknet-cpp. This repository provides visual studio project files for Darknet-cpp. This repository does not require additional libraries like pthread, and provides all requirements integrated.

- For 2013 Visual Studio
- Needs CUDA 8.0 (and its environment settings correctly defined)

## Steps to build darknet-cpp-windows:

- Download the darknet-cpp port, from 

https://github.com/prabindh/darknet

- At the same level as the darknet folder, clone or download the darknet-cpp-windows sources

https://github.com/prabindh/darknet-cpp-windows

- Copy the "common" folder from Nvidia GPU Computing Toolkit into darknet-cpp-windows\darknet\ folder.

- Open the below solution file in Visual Studio

darknet-cpp-windows\darknet\darknet.sln

- Build the project arapaho, which will also build the darknet project dependency

- Copy the required data, weight, cfg and input image file for detection into the arapaho folder. All the files need to be named as {input.cfg, input.data, input.jpg, input.weights}. The names can be changed in the darknet\arapaho\test.cpp file.

- Run the generated binary arapaho.exe, for detection, from 

darknet-cpp-windows\bin\win64\$(Configuration)\arapaho.exe

- This will run the arapaho C++ wrapper, and generate output for the provided image. Example output below:

`
....
Image data = 000001362EF87060, w = 992, h = 620
Detect: Resizing image to match network
l.softmax_tree = 0000000000000000, nms = 0.400000
Detected 1 objects
Box #0: x,y,w,h = [0.406386, 0.283149, 0.384096, 0.509924]
`

For a brief about Arapaho C++ API, refer to https://github.com/prabindh/darknet/blob/master/arapaho/arapaho_readme.txt