# case-study-xinshasha
case-study-xinshasha created by GitHub Classroom

### Case Study For Pytorch
#### Technology and Platform used for development
a.What coding languages are used? Do you think the same languages would be used if the project was started today? What languages would you use for the project if starting it today?<br>
b.What build system is used (e.g. Bazel, CMake, Meson)? What build tools / environment are needed to build (e.g. does it require Visual Studio or just GCC or ?)<br>
c.What frameworks / libraries are used in the project? At least one of these projects don’t use any external libraries or explicit threading, yet is noted for being the fastest in its category--in that case, what intrinsic language techniques is it using to get this speed.<br><br>

a. Pytorch is a deep learning framework written in python but has a core compiled by C++ and CUDA. <br>
I think the same choice would be made if the project was started today. And I will also choose to use python.<br>
Pytorch is compiled with C++ and CUDA because they are compiled languages and can be run much faster than python. However, it's a trade-off that C++ and CUDA are less user-friendly than python.
And Python can control a C++ backend perfectly, so it's a good choice to use python API.<br><br>
b. Cmake is used to build pytorch. GCC and NVCC are necessary.<br><br>
c. Pytorch is developed as native python lib. And its dependencies are ```numpy,pyyaml,mkl,mkl-include,setuptools,cmake,cffi,typing```<br>
Pytorch has no specific backend but utilizes different backends for CPU, GPU and different backends.<br>
For cpu, it depends on MKL and OpenBLAS. For GPU, it depends on CuDNN and CUDA.<br><br>

#### Testing: describe unit/integration/module tests and the test framework
a.How are they ensuring the testing is meaningful? Do they have code coverage metrics for example?<br>
b.What CI platform(s) are they using (e.g. Travis-CI, AppVeyor)?<br>
c.What computing platform combinations are tested on their CI? E.g. Windows 10, Cygwin, Linux, Mac, GCC, Clang<br>
<br>
a. There are code coverage metrics for pytorch according to some issues and for some pytorch-based libs like pytorch-geometric uses ```.coveragerc``` to test coverage.<br><br>
b. Travis-CI was used accoding to [```.travis.yml```](https://github.com/pytorch/pytorch/blob/master/.travis.yml). However, for now,circle CI is used for test accoding to the commit history and [```.circleci```](https://github.com/pytorch/pytorch/tree/master/.circleci).<br><br>
c. According to  [```.travis.yml```](https://github.com/pytorch/pytorch/blob/master/.travis.yml) and [```.travis.aten.yml```](https://github.com/pytorch/pytorch/blob/master/.travis.aten.yml), Linux and CLang are tested.
And Linux,CLang,Mac,GCC is tested under circleci.<br><br>

#### Software architecture in your own words, including:
a.How would you add / edit functionality if you wanted to? How would one use this project from external projects, or is it only usable as a standalone program?<br>
b.What parts of the software are asynchronous (if any)?<br>
c.Please make diagrams as appropriate for your explanation<br>
d.How are separation of concerns and information hiding handled?<br>
e.What architectural patterns are used<br>
f.Does the project lean more towards object oriented or functional components<br><br>

a. pytorch is a relatively low level lib so that users can manipulate nearly every variables in Model. It's flexible to use build-in api to modify the project and fullfill user's requirements.
Users may use torch.tenser to manipulate data, torth.nn to build model, torch.nn.functional to define their own functions,torch.optim to inital the training steps and so on.<br>
b. No part is asynchronous.<br>
c. Diagram for a pytorch system.<br>
![image](https://github.com/ec500-software-engineering/case-study-xinshasha/blob/master/Pytorch_Structure.png)<br>
```net.py``` saves the model defined by users. ```data_loader.py``` is the data prepocessing scripts.```train.py``` is the training strategy and ```evaluate.py``` is the way to evaluate the model.<br>
For torch lib,I cant find any existed diagram. I draw one from to myown understanding.<br>
![image](https://github.com/ec500-software-engineering/case-study-xinshasha/blob/master/Torch.png)<br>
d. Informations are manipulated in tensors. And tensors share memory with numpy arrays.<br>
e. It's a set of functions to be used. The architecture depends on the real project.<br>
f. All funtions are bagged in an object in putorch.

#### Analyze two defects in the project--e.g. open GitHub issue, support request tickets or feature request for the project<br>
a. Does the issue require an architecture change, or is it just adding a new function or?<br>
b. make a patch / pull request for the project to fix problem / add feature.<br>
<br>
1. The issues are mostly requires help from developer to use the lib. Most of them do not require a new funtion or architecture change.<br>
2. Most of them like [#18104](https://github.com/pytorch/pytorch/issues/18104) are requiring help for bug fixing. Not only developers but also other users will be helpful.<br>
### Demo for Pytorch.<br>
See the [demo](https://github.com/ec500-software-engineering/case-study-xinshasha/blob/master/Demo_Torch.ipynb).
It's a LeNet on Mnist with acc = 98.7%.





