# Virtual Machine
Virtual Machine 이란 Host OS 위에 다른 OS 를 구동할 수 있게 하는 프로그램입니다.

## VirtualBox
VirutalBox 는 Oracle 에서 만든 virtual machine 으로 AMD64/Intel64 등 x86 ISA 를 
지원합니다.

### 준비물
* [Downlaod VirtualBox] 에 접속하여 자신의 OS 에 맞는 package 를 설치합니다.
  * VirtualBox package 뿐만 아니라 pacakge 항목 아래에 있는 `VirtualBox Oracle VM VirtualBox Extension Pack` 
  도 같이 다운로드합니다.
  * Exetension pack 은 USB 2.0 / USB 3.0 등 필요한 기능들을 가지고 있습니다.
* [Download Ubuntu] 에 접속하여 자신의 bit 에 맞는 Ubuntu 를 다운로드 합니다.
  * 64bit: ubuntu-16.04.5-desktop-amd64.iso
  * 32bit: ubuntu-16.04.5-desktop-i386.iso

### Ubuntu 설치
1. Ubuntu 를 설치하기 이전에 다운로드 받은 Extension pack 을 미리 설치합니다. 
(받은 파일을 클릭하면 자동으로 VirtualBox 가 인식해서 설치 메세지를 띄웁니다.)

2. 원하는 이름을 입력하고 Type 과 Version 을 맞춥니다. (예: Linux / Ubuntu 64bit)
  * 만약 자신의 OS 가 64bit 임에도 불구하고 32bit 밖에 보이지 않는다면 
VT-d / AMD SVM 이 Off 되어 있을 수 있습니다. [Why does VirtualBox only have 32bit?]
  * 32bit 로 했음에도 정상적으로 VirtualBox 가 동작하지 않는다면 [VMware] 로 설치하시기바랍니다.
![install1][install1]

3. 자신이 원하는 Memory size 를 설정합니다.
![install2][install2]

4. 새로운 virtual image 를 `.vdi` 로 만들고 원하는 File Location 과 size 를 정해서 image 를 생성합니다.
![install3][install3]
![install4][install4]
![install5][install5]
![install6][install6]

5. 생성한 virtual image 를 클릭하고 자신이 다운로드받은 ubuntu `.iso` file 의 경로를 설정하여 ubuntu 를 image 에 설치합니다.
![install7][install7]
![install8][install8]

6. 아래 스크린샷과 맞게 Ubuntu 를 설치합니다. 이름의 경우 자신이 원하는 것으로 설정합니다.
![install9][install9]
![install10][install10]
![install11][install11]
![install12][install12]
![install13][install13]


[Downlaod VirtualBox]:https://www.virtualbox.org/wiki/Downloads
[Download Ubuntu]:http://releases.ubuntu.com/16.04/
[Why does VirtualBox only have 32bit?]:https://superuser.com/questions/866962/why-does-virtualbox-only-have-32-bit-option-no-64-bit-option-on-windows-7
[VMware]: http://empty


[install1]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu1.png
[install2]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu2.png
[install3]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu3.png
[install4]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu4.png
[install5]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu5.png
[install6]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu6.png
[install7]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu7.png
[install8]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu8.png
[install9]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu9.png
[install10]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu10.png
[install11]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu11.png
[install12]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu12.png
[install13]:https://github.com/jafffy/linux_usage_wiki/blob/master/images/virtual/ubuntu13.png
