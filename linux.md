# Linux
이 페이지는 Linux 의 기본 명령어 및 서버에 사용되는 명령어를 담고 있습니다.
아래에서 설명될 명령어들은 자주 쓰이는 명령어와 옵션들을 담고 있기 때문에 
자세한 명령어에 대한 내용은 `man [command]` 를 통해서 공부하시기 바랍니다.

아래에서 설명하는 명령어들은 모두 `Terminal` 이라는 application 에서 사용될 수 있습니다. 
먼저 아래에 설명될 command 를 사용하기 이전에 설치된 Linux 에 기본적인 tools 들이 설치되어 있지 않을 가능성이 
있으니 아래 명령어들을 입력해서 기본적인 기능들을 설치합니다. 
```bash
$ sudo apt-get update
$ sudo apt-get install build-essential
$ sudo apt-get upgrade
```

__ssh__   
SSH 는 Secure Socket Shell 약자로 이름처럼 안전한 네트워크 프로토콜입니다. 이 명령어는 리모트 컴퓨터에 접속하기 위해 사용되며 RSA 와 같은 
인증키를 사용하기 때문에 안전한 접속을 보장할 수 있습니다.

이 명령어를 사용해서 다른 컴퓨터로 접속하기 위해선 몇 가지 준비사항이 필요합니다. 
바로 앞서 이야기했던 인증키가 필요하며 이 키는 Linux 에서 기본적인 명령어를 사용하여 생성할 수 있습니다.
```bash
$ ssh-keygen
Enter file in which to save the key(/home/username/.ssh/id_rsa):
Enter passpharse (empty for no passphrase):
```
위 첫 번째 문구에서 별다른 입력없이 엔터를 입력하면 해당 경로로 두 가지 파일이 생성됩니다. 
하나(`id_rsa`)는 자신의 컴퓨터의 개인키(`private key`) 이고 다른 하나(`id_rsa.pub`)는 공개키(`public key`) 입니다.
생성된 공개키는 `cat ~/.ssh/id_rsa.pub` 를 통해서 확인할 수 있으며 이 키는 접속하려는 컴퓨터의 ssh config 파일에 저장되어야 합니다.

만약 접속하려는 컴퓨터의 OS 가 Linux/OS X 라면 `~/.ssh/authorized_keys` 파일에 아까 생성했던 공개키를 입력하고 저장합니다. 
만약 파일이 존재하지 않다면 새로 생성해도 됩니다.

이 모든 작업이 완료되었다면 이제 내 컴퓨터에서 다른 컴퓨터로 접속할 준비가 끝났습니다. 
접속하려는 컴퓨터의 아이피와 계정을 확인하고 해당 내용을 명령어에 입력합니다.
```bash
$ ssh remote-username@remote-server-ip
```

__Putty__   
설명필요

__scp__
```bash
```
