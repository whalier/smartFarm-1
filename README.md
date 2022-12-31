# smartFarm

## 구조
### Raspberry Pi Pico W - Firebase Realtime Database - Web or App  
#### 1. Firebase의 활용방법  
![1](https://user-images.githubusercontent.com/13882302/210129906-76bc322a-fb4e-4375-8104-6a515bfeb861.png)  

#### 2. 본 smartFarm의 운용 구조  
![2](https://user-images.githubusercontent.com/13882302/210129908-b2e48b08-0a86-4980-ba4a-a07fab87f81c.png)

--- 
## 각 세그먼트의 특징
### 1. Firebase  
#### 1. Firebase는 구글에서 운영하는 인터넷 관련 BaaS서비스라고 볼 수 있다. BaaS에 대한 정의는 [링크](https://blog.back4app.com/iaas-paas-baas-provider-list/)를 참고한다. 각 온라인 서비스 프로바이더의 분류는 아래 그림을 참고하면 된다.  
![image](https://user-images.githubusercontent.com/13882302/210130588-caaa4759-b32e-4526-aed5-e8b5cd149a70.png)  

#### 2. 우리가 스마트팜 프로젝트에서 Firebase를 사용하는 그 이유는 다음과 같다.  
* 첫째, 우리는 IPv4 시스템의 한계로 인해 개별 기기에 공인IP를 가질 수 없다.  
* 둘째, 이는 몇 개 안되는 공인IP 아래에 공유기를 연결해 사설 IP를 만들어내 사용해야 함을 의미한다.  
* 셋째, 사설 IP를 사용하는 디바이스가 운용하는 서비스에 접근하려면 네트워크의 개념을 이해하고 있어야 한다. 
* 넷째, 이 중 가장 기본인 공인 IP에서 사설 IP로 연계를 하기 위한 과정인 포트포워딩에 대해 이해하고 있어야 한다.
* 다섯째, 모바일 통신에서는 각 모바일 통신사가 권한을 가지고 있는 모바일 통신망 NAT의 구조에 대해 이해하고 있어야 한다.
* 여섯째, 하지만 이를 도전한 사람들은 NAT를 통해 역으로 모바일 디바이스나 모바일 통신망을 통해 테더링을 하고 있는 디바이스에서 운용하는 서비스에 접근하는 것은 모바일 서비스를 제공하는 통신사의 권한부여 없이는 불가능하다는 사실을 수십 수백번의 시도 끝에 알게 된다. 통신사는 그걸 지원할 생각이 없다. 
* 일곱째, 일반적으로 통신은 서버와 클라이언트로 구성되고, 서버가 서비스를 열면, 클라이언트가 접근하는 형태로 서비스가 되는데, 위의 설명과 같은 이유들로 서버가 서비스를 해도 클라이언트가 접근을 할 수가 없거나, 그 과정이 매우 어렵다는데 있다. 
* 여덟째, 따라서, 우리는 구글 계정과 간단한 세팅만으로 쉽게 사용할 수 있는 Firebase라는 중간 단계의 Realtime Database 서비스를 이용해 이 곳에 데이터를 올리고, 이 곳에 접근해서 데이터를 읽어가는 형태의 서비스를 구상하게 된 것이다. 
* 참고로, Firebase는 Realtime Database만 지원되는 것이 아니고, 인증, 앱체크, 데이터베이스, 스토리지, 호스팅, 함수 서비스, 머신러닝, 분석 등 엄청나게 다양한 서비스를 지원하고 있으며, 충분한 용량을 무료로 제공하므로, 개발단계나 테스트 단계에서는 무료라고 봐도 무방하다. 
* 어쨌든 사람들이 해당 서비스를 사용하고, 그 서비스를 이용해 부가가치를 만들어내야 자신들도 먹고 살 수 있음을 잘 알고 있는 것이고, 그런 사람들이 많으면 많을수록 좋으니 이렇게 제공되는 기본 서비스들을 통해서 우리 같은 초보개발자들이 마음 놓고 테스트를 진행해볼 수 있다는 것이다. 
* 이는 오픈소스 진영의 라이프사이클이 잘 돌아가고 있고, 그 안에 있는 사람들이 아직 건재하게 생존해 있다는 것으로 증명된 사실이며, 사실 구글도 그런 문화를 통해 성장해왔으니, 그런 서비스를 통해 자신들의 생태계를 더욱 확장하는 방법을 알고 있는 것은 어찌보면 매우 당연한 일이다.


### 2. Github Pages  
#### 1. Github는 전세계 코더들의 자료 저장소이며, 자신의 프로젝트들을 관리하고 공유할 수 있도록 서비스를 제공하고 있다. 
#### 2. Github Pages는 HTML, CSS, JavaScript로 대변되는 정적 웹페이지에 대한 서비스를 무료로 제공하고 있다. 정적 웹페이지는 서버측에서 클라이언트의 특정한 요청에 대해 프로세스를 진행하고 그 결과물을 제공해주는 동적웹페이지(WAS서버, 데이터베이스, 로그인 기능 등이 추가됨)와 달리 단순히 웹페이지만 제공한다.
#### 3. 우리가 스마트팜 프로젝트에서 Github Pages를 사용하는 이유는 다음과 같다.

---
## 세그먼트 간 통신 테스트 영상
### Web - Firebase
https://user-images.githubusercontent.com/13882302/210126670-243a6fd7-b9b9-4378-b12e-63e5b2ef9260.mp4

---
## 세팅
### 1.Firebase 세팅
#### 1. 아래 링크로 이동해서 구글 계정으로 로그인을 하고, 오른쪽 상단에 있는 '콘솔로 이동' 버튼을 눌러 Firebase 콘솔로 들어간다.  
[https://firebase.google.com/](https://firebase.google.com/)  
![image](https://user-images.githubusercontent.com/13882302/210128421-231a463e-c585-4814-8544-16eb70728961.png)

#### 2. '프로젝트 추가'버튼을 눌러 자신의 프로젝트를 만든다.  
![image](https://user-images.githubusercontent.com/13882302/210128433-2493803d-020a-4560-ac5f-8c6560a0e82c.png)  
![image](https://user-images.githubusercontent.com/13882302/210128462-40a34a3a-6ed5-4759-9292-ed18856f3b6e.png)  

#### 3. 데이터 분석을 하지 않을 경우 Google 애널리틱스 사용 설정을 해제하고 '프로젝트 만들기'버튼을 누른다.  
![image](https://user-images.githubusercontent.com/13882302/210128474-640f97e3-0a27-417a-b9e8-f0d1b747ae97.png)  
![image](https://user-images.githubusercontent.com/13882302/210128488-dc17be71-c67b-4be4-bf07-fd68c77a5117.png)  

#### 4. 30초 정도 프로젝트 생성 시간을 기다린다.  
![image](https://user-images.githubusercontent.com/13882302/210128513-84031eea-968f-4b3d-a7ad-610bd2bd7e91.png)  
![image](https://user-images.githubusercontent.com/13882302/210128514-c0907965-f00a-47cb-af5c-d6b2acde54f9.png)  
![image](https://user-images.githubusercontent.com/13882302/210128521-98278090-4159-4e4c-a769-cba0c58946c5.png)  

#### 5. 새로 만든 프로젝트 폴더로 들어간다.  
![image](https://user-images.githubusercontent.com/13882302/210128535-ea7d689c-2baf-4252-bfab-2746290c8b03.png)  

#### 6. Firebase 메뉴중에서 빌드-Realtime Database를 선택해서 연다.  
<img width="389" alt="화면 캡처 2022-12-31 160136" src="https://user-images.githubusercontent.com/13882302/210128358-d1045b3f-98d1-495c-b4fa-29fab188e25a.png">  

#### 7. '데이터베이스 만들기' 버튼을 누른다.  
![image](https://user-images.githubusercontent.com/13882302/210128622-b9bf441c-b07c-449c-9633-b638d744f179.png)  

#### 8. 서버 위치를 선택한다.  
![image](https://user-images.githubusercontent.com/13882302/210128633-124bfef0-5edc-4214-a111-eea07e291ea1.png)  

#### 9. 데이터베이스 기본 설정을 한다. 추후 언제나 바꿀 수 있으니 기본 세팅으로 사용설정을 한다.  
![image](https://user-images.githubusercontent.com/13882302/210128658-8eaa6130-0875-4517-b8a0-1c34824340b9.png)  

#### 10. 가운데 있는 링크를 통해 Realtime Database에 접근을 할 수 있다.  
![image](https://user-images.githubusercontent.com/13882302/210128672-ce1602e5-535c-4db1-80e0-77c6f38a5e5e.png)  

#### 11. '규칙' 탭으로 들어오면 데이터베이스에 대한 읽기, 쓰기 권한이 설정되어 있는데, 이 설정이 매우 중요하다.  
![image](https://user-images.githubusercontent.com/13882302/210128700-f12252c9-6de3-4c2b-a0e2-feb2801dc9b2.png)  

#### 12. false로 기본 설정되어 있는데, 이곳을 클릭하여 true로 바꿔주고 '게시'버튼을 누르면 누구나 접근해서 데이터를 읽고 쓸 수 있다. 추후 보안 및 트래픽에 따른 결제비용 증가에 영향을 줄 수 있으니, 테스트 할 때만 true로 설정하고, 실제 사용할 때는 읽고 쓰는 권한을 false로 바꾸고 접근한 사람의 사용자 권한에 따라 사용하거나, 엑세스 토큰을 부여받아 사용할 수 있도록 해야한다.  
![image](https://user-images.githubusercontent.com/13882302/210128717-727f05cb-7f26-4512-ad64-05fe50a9a7c5.png)  

#### 13. 다음으로 이 Realtime Database를 실제로 사용하기 위해서 관련 config 내용을 얻어야 한다. 프로젝트 개요-기어 버튼-프로젝트 설정으로 가서 내 웹앱에 firebase를 추가하는 버튼을 눌러 세팅을 완료하고, config 정보를 얻어낸다. 한 번 세팅을 완료하면 세팅을 삭제하기 전까지는 계속 해당 config를 사용할 수 있다.    
![image](https://user-images.githubusercontent.com/13882302/210128316-0838da1d-557a-4972-86e5-7b5654286696.png)  

<img width="573" alt="210127985-4958b729-b8d9-4291-88dd-9501b94bfc01" src="https://user-images.githubusercontent.com/13882302/210128211-9489a97d-d658-4298-b674-a54d5a44e023.png">  

<img width="716" alt="210128004-1cfdf26e-da0b-4f69-9ae5-163931e758bd" src="https://user-images.githubusercontent.com/13882302/210128268-1395688d-3c6a-4745-b540-76e218954ecd.png">  

![image](https://user-images.githubusercontent.com/13882302/210128010-065282ab-3778-4edb-bed9-709ac418d0de.png)  

![image](https://user-images.githubusercontent.com/13882302/210128019-d674a4f2-a714-42aa-b2f9-c4f908e9df20.png)  

<img width="623" alt="화면 캡처 2022-12-31 155100" src="https://user-images.githubusercontent.com/13882302/210128091-6e17baa4-6798-4b1a-bf11-1a36afd1402c.png">  

#### 14. firebase config 정보를 가져온다. 아래의 최종 이미지 안에 있는 firebaseConfig 내부의 값만 복사해서 내 웹의 web/public/js/firebase.js파일의 해당 부분에 붙여넣으면 자신의 Realtime Database에 접근해서 온도, 습도, 조도, LED제어, Fan제어를 위한 데이터를 주고 받는 smartFarm 제어용 웹 서비스를 바로 이용할 수 있다. 
<img width="287" alt="화면 캡처 2022-12-31 155119" src="https://user-images.githubusercontent.com/13882302/210128094-0829b06a-c575-4ba5-8ef4-2df90652cc8b.png">  

* Firebase 사용 요금제는 아래 링크를 참고하면 되며, 테스트 용도로는 비용이 따로 들지 않는다고 봐도 무방하다.  
[https://firebase.google.com/pricing?authuser=0&hl=ko](https://firebase.google.com/pricing?authuser=0&hl=ko)  

### 2. Web(github pages) 세팅
* 테스트 링크 
[https://mtinet.github.io/smartFarm/web/public/index.html  ](https://mtinet.github.io/smartFarm/web/public/index.html)  

### 3. Raspberry Pi Pico W 세팅



