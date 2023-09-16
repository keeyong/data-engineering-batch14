### AWS EC2로 로그인하는데 필요한 정보

- 호스트 이름: ec2-*****.com (이런식의 이름을 이메일이나 메세지로 전달드립니다)
- 사용자 ID: ubuntu (사용자에 관계없이 통일)
- 로그인에 사용하는 private key의 이름은 data-eng-2022-08.pem 입니다. 이 파일 역시 이메일이나 메세지로 전달됩니다.

먼저 Private key를 적당한 폴더로 다운로드합니다. SSH를 이용해서 접근해야 하는데, 이는 운영체제에 따라 방식이 다릅니다.

### Mac or Linux

터미널을 열어 data-eng-2022-08.pem이 있는 폴더로 이동합니다. 먼저 data-eng-2022-08.pem 파일의 속성을 본인만 읽을 수 있게 바꾸어야 합니다: 첨부된 파일이 이미 속성이 그렇게 잡혀있어서 이 부분이 필요없을 수도 있습니다.
```
$ chmod 600 data-eng-2022.pem
```

이제 ssh를 이용해서 위에 명시된 호스트 이름로 접속합니다. 명령실행시 서버에 접속할지 물어볼 텐데, yes 를 입력합니다.
```
$ ssh -i data-eng-2022.pem ubuntu@호스트이름
```

성공적으로 로그인이 되었다면 아래와 같은 화면이 나와야 합니다

```
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 5.3.0-1023-aws x86_64)
...
To run a command as administrator (user "root"), use "sudo ".
See "man sudo_root" for details.

ubuntu@ip-172-....:~$
```

### Windows 10

먼저 PowerShell이 설치되어 있는지 확인하고 없다면 설치합니다. 설치는 링크를 참고하세요.
PowerShell을 실행합니다.
```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\Users\keeyong>
```

data-eng-2022-08.pem 첨부파일이 있는 폴더로 이동해서 다음 명령을 수행합니다. 호스트이름은 앞서 이메일에 있는 호스트 이름입니다. 명령 실행 시 서버에 접속할지 물어볼 텐데 yes를 입력합니다.

```
PS C:\Users\keeyong\dataeng\> ssh -i data-eng-2022.pem ubuntu@호스트이름
```

성공적으로 로그인이 되었다면 아래와 같은 화면이 나와야 합니다
```
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 5.3.0-1023-aws x86_64)
...
To run a command as administrator (user "root"), use "sudo ".
See "man sudo_root" for details.

ubuntu@ip-172-....:~$
```

### Windows 10 이전 버전

훨씬 더 복잡합니다. PuTTY를 설치해야하고 data-eng-2022-08.pem 파일을 .ppk 파일로 변환해주어야 합니다. 이건 복잡해서 [링크](https://extrememanual.net/26803)를 참고하시기 바랍니다.
