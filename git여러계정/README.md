# Git계정 여러개 사용하기

ssh키 생성

``` ssh-keygen -t ed25519 -C "<이메일>" ```
``` 
---
Enter file in which to save the key (/Users/account/.ssh/id_ed25519): /Users/account/.ssh/<저장할 ssh-key명>

Enter passphrase (empty for no passphrase): 엔터

Enter same passphrase again: 엔터
```
> 비밀번호를 입력하면 복잡해지므로(경험X) 엔터를 눌러 비밀번호를 스킵
>
> 사용할 계정만큼 ssh key를 생성

ssh config 생성

``` vi ~/.ssh/config ```

안에 내용 입력
```
Host github.com
        HostName github.com
        User git
        IdentityFile ~/.ssh/github/git
Host github.com-<구분할 이름>
        HostName github.com
        User <이메일>
        IdentityFile ~/.ssh/<ssh-key명>
Host github.com-<구분할 이름2>
        HostName github.com
        User <이메일2>
        IdentityFile ~/.ssh/<ssh-key명2>
```

ssh에 추가
```
ssh-add ~/.ssh/<ssh-key명>
ssh-add ~/.ssh/<ssh-key명2>
```

사용법

``` git clone git@github.com-<구분할 이름>:AumaHub/mes.git ```

> clone예시