# AWS EKS 사용방법

※[공식문서](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html) 보고 따라함

## kubectl 설치
---

> 이미 쿠버네티스가 깔려있다면 따라하지 하세요

> Kubernetes 1.22

AWS s3에 있는 쿠버네티스 다운로드

``` curl -o kubectl https://s3.us-west-2.amazonaws.com/amazon-eks/1.22.6/2022-03-09/bin/darwin/amd64/kubectl ```

``` curl -o kubectl.sha256 https://s3.us-west-2.amazonaws.com/amazon-eks/1.17.12/2020-11-02/bin/darwin/amd64/kubectl.sha256 ```

kubectl의 권한 변경

``` chmod +x ./kubectl ```

PATH 등록

``` mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$HOME/bin:$PATH ```

``` echo 'export PATH=$PATH:$HOME/bin' >> ~/.bash_profile ```

버전확인

``` kubectl version --short --client ```

## aws cli 설치
---
awscli 설치

``` brew install awscli ```

awscli 인증

![AWS_KEY](assets/AWS_KEY.png)
``` 
aws configure --profile <생성할 프로필명> 

AWS Access Key ID [None] : [발급받은 IAM의 Access Key ID]
AWS Secret Access Key [None] : [발급받은 IAM의 Secret Access Key]
Default region name [None] : ap-northeast-2[서울 리전]
Default output format [None] : 
```
> --profile 을 사용하지 않으면 전역설정이 되며 
> 
> --profile 옵션으로 사용 시 aws, eksctl 명령어 뒤에 --profile <프로필명>으로 계정 접근

## eksctl 설치
---

macOS에 Homebrew가 아직 설치되어 있지 않은 경우 다음 명령을 사용하여 설치

``` /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)" ```

Weaveworks Homebrew 탭을 설치

``` brew tap weaveworks/tap ```

eksctl를 다음 명령으로 설치

``` brew install weaveworks/tap/eksctl ```

eksctl가 이미 설치된 경우 다음 명령을 실행하여 업그레이드

``` brew upgrade eksctl && brew link --overwrite eksctl ```

다음 명령을 사용하여 설치가 성공했는지 테스트

``` eksctl version ```

## eksctl 사용
---

fargate를 사용해서 CloudeFormation을 생성

``` eksctl create cluster --name <생성할 클러스터 명> --region <리전코드> --fargate [--profile <프로필명>]```
> CloudFormation은 무료이며 region-code는 [여기를 참고](https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/using-regions-availability-zones.html)

## argoCD 설치
---
> Docker Desktop에서 AWS EKS에 접속되어있는지 확인하고 시작할 것

Argo CD CLI 설치

``` 
brew tap argoproj/tap 
brew install argoproj/tap/argocd
```
> 로컬에서 Argo CD 명령어를 사용할 수 있어야 하므로 CLI를 깔아준다.

argocd 네임스페이스 생성

``` kubectl create namespace argocd ```

Argo CD 배포

``` kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/ha/install.yaml ```

Argo CD 포트포워드

``` kubectl port-forward svc/argocd-server -n argocd 8080:443 ```

Argo CD 패스워드 확인

``` kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d ```
> ID는 admin으로 고정
