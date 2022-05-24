# git ssh 생성
Linux, MacOS

1. ssh key 생성
    ``` 
    ssh-keygen -t ed25519 -C "<이메일>"

    ----------------------------------------------

    Enter file in which to save the key (/Users/account/.ssh/id_ed25519): /Users/account/.ssh/<저장할 ssh-key명>

    Enter passphrase (empty for no passphrase): 엔터

    Enter same passphrase again: 엔터
    ```
2. public 키 확인
    ```
    cat ~/.ssh/<ssh-key명>.pub
    ```
3. 등록할 레포지토리에 Deploy Keys 추가
    ![](assets/key%EB%93%B1%EB%A1%9D1.png)
4. 2번에서 확인한 키값 붙여넣기 후 생성
    ![](assets/key%EB%93%B1%EB%A1%9D2.png)