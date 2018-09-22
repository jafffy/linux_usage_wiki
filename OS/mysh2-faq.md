# FAQ

## "실행가능한" 파일이란 뭔가요? What is the "executable" file?

Unix 계열 OS (linux를 포함)의 file에 세가지 권한 속성이 있습니다. - read / write / execute. 이 중 execute 권한이 있는 어떤 파일이든 “실행”이 가능합니다.
All unix-family OS (including linux)’s file has three permission properties. - read / write / execute. Every file which has execute permission “execute’ can be executed.

'''sh
jafffy at Jaewons-MacBook-Pro in ~/workspace/scipy (master)
$ ls -l
total 320
-rw-r--r--   1 jafffy  staff   1143 Sep 17 16:16 CONTRIBUTING.rst
-rw-r--r--   1 jafffy  staff  22904 Sep 17 16:16 HACKING.rst.txt
-rw-r--r--   1 jafffy  staff   6977 Sep 17 16:16 INSTALL.rst.txt
-rw-r--r--   1 jafffy  staff   8761 Sep 17 16:16 LICENSE.txt
-rw-r--r--   1 jafffy  staff    796 Sep 17 16:16 MANIFEST.in
-rw-r--r--   1 jafffy  staff   2096 Sep 17 16:16 README.rst
-rw-r--r--   1 jafffy  staff  11414 Sep 17 16:16 THANKS.txt
-rw-r--r--   1 jafffy  staff   6551 Sep 17 16:16 appveyor.yml
drwxr-xr-x   6 jafffy  staff    192 Sep 17 16:16 benchmarks
-rw-r--r--   1 jafffy  staff    257 Sep 17 16:16 codecov.yml
drwxr-xr-x  11 jafffy  staff    352 Sep 17 16:16 doc
-rw-r--r--   1 jafffy  staff  24717 Sep 17 16:16 pavement.py
-rw-r--r--   1 jafffy  staff    568 Sep 17 16:16 pytest.ini
-rwxr-xr-x   1 jafffy  staff  16104 Sep 17 16:16 runtests.py
drwxr-xr-x  26 jafffy  staff    832 Sep 17 16:16 scipy
-rwxr-xr-x   1 jafffy  staff  17692 Sep 17 16:16 setup.py
-rw-r--r--   1 jafffy  staff   6788 Sep 17 16:16 site.cfg.example
drwxr-xr-x  13 jafffy  staff    416 Sep 17 16:16 tools
-rw-r--r--   1 jafffy  staff   1400 Sep 17 16:16 tox.ini
'''

위와 같이 ls -l이라는 커맨드를 치면 아래의 목록에서 -rw-r—r— 과 같이 써있는 부분이 있는데, - 는 regular file을 의미하고 그 뒤의 string은 권한을 의미합니다.  r 은 read 권한, w는 write, x는 execute를 가리킵니다.
Like above typing ls -l command, you can find the part written like -rw-r—r—, first character - means regular file and last of string represents their permission. r means read, w is write permission and x is execution permission. 

실행 파일은 execute권한을 가진  file을 의미합니다. 즉 x 표시가 있는 파일이죠. 이를 확인하기 위해서는 lstat 이라는 system call을 확인해 보세요.
Executable file means a file has execution permission. I.e. a file has x on their permission string. Check out lstat system call for confirmation.

이번 과제에서는 user의 실행 가능 권한을 기준으로 진행하시면 됩니다.
In this assignment, please check user's execution permission.
