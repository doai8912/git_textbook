## 📄 git 교과서 5단원 요약

<br>

> **1. 서버 저장소**

- **서버 저장소 (=원격 저장소)** : 로컬 저장소의 코드를 복제한 복사본 

  - 서버의 소스코드는 다른사람들과 협업하여 개발을 할 수 있는 특징을 지님
<br>

- 협업 저장소 : 여러 개발자와 협력하기 위해 탄생 

  - 깃은 다양한 개발 환경을 고려해 **분산형 모델**을 선택  
<br>  

- 연속된 작업 

  - 장소와 시간에 영향을 받지 않고 여러 컴퓨터에 코드를 동기화해 연속된 작업 가능
  
  - 깃 저장소를 복제하고, 작업 결과물을 다시 서버로 통합
  
  - 깃은 분산된 저장소를 하나로 통합하고, 최신코드를 배포
  
  - 깃은 원격저장소로 모든 구성원에게 코드의 결과를 동기화
<br>

> **2. 깃허브 서버 준비**

- 깃허브 : 대표적인 깃호스팅 서비스로, 모든 서비스를 무료로 이용 가능

  - 공개용 저장소 : 무제한으로 사용 가능
  
  - 비공개용 저장소 : 일부 유료 서비스 존재
<br> 

-원격 저장소 생성
- 깃허브 계정 가입 후 new repository 클릭 후 원격 저장소 생성. 단, 저장소 이름은 중복 불가능.
<br>

> **3. 깃허브 연동 및 원격 등록**
- **프로토콜 : 깃은 Local, HTTP, SSH, Git 네 종류의 전송 방식을 지원한다.**

  -Local : 로컬 컴퓨터에 원격 저장소를 생성함. 모든 자료가 자신의 컴퓨터에 집중되는 약점이 있음
  
  -HTTP : 기존 아이디와 비밀번호만으로 인증하는 절차를 가짐. 익명으로 처리 가능.
  
  -SSH : 인증서를 사용하여 인증. 인증서는 공개키와 개인키로 구분되고 공개키는 서버에 등록, 개인키는 로컬에 저장. 익명 사용 가능.
  
  -Git : 보안에 취약해 잘 사용하지 않음.
  
<br>
- **로컬 저장소와 원격 저장소 연결**

  - git remote add origin 깃허브주소.git : 원격 저장소와 연결
  
  - git remote -v : 연결되어있는지 확인
<br>

- **원격 저장소로 커밋 전송**

  - git push origin master : 커밋 전송
<br>

- **원격 저장소 복제**

  - git clone 깃허브 주소 : 저장소 복제
<br>

- **코드 수정 후 원격 저장소로 전송**
  
  - code 파일명 : 코드 수정 
  
  - git commit -am "메세지" : 커밋 
  
  - git push : push 전송
<br>

- **원본 저장소 갱신** 

  - git pull : 코드 수정내역 갱신
<br>

> **4. 서버 전송**

- **push : 서버에 전송**

  - 원격 저장소로 로컬 깃 저장소의 내용을 전송할 때 push 명령어 사용<br>

  - 자신의 로컬 저장소를 백업하는 용도로 원격 저장소를 사용할 수 있음<br>

<br>

- **push 과정**

  1)처음 푸시 시 서버에 새로운 master 브랜치를 생성<br>
  
  2)로컬의 master 브랜치 안에 소스 코드를 서버의 master 브랜치로 업로드<br>

<br>

> 📘 NOTE 
>> ⭐ 원격저장소에 푸시하면 master 저장소가 총 2개 생성 <br>
>>
>> **-->** 로컬 저장소의 master 브랜치와 서버의 master 브랜치<br>
>>
>> ⭐ 전송은 두 브랜치 간에 전송과 수신을 동기화
<br>

> **5. 자동으로 내려받기**

- **clone: 복제**

  - 초기화 init 명령어 외에 원격 서버에 접속에 필요한 추가 설정을 자동으로 수행
  
  - 서버의 연결 설정을 마친 후 서버 안에 있는 모든 커밋된 코드 이력을 한번에 내려받음

<br>

- **pull: 서버에서 내려받기**
  
  - 복제 후 원격 저장소의 갱신된 내용을 추가로 내려받으려면 pull 명령어를 사용
  
  - pull 명령어를 주기적으로 사용시 최신 커밋 정보를 로컬 저장소를 유지가능

<br>

- **pull 과정**

  1)작성한 (sever.htm) 파일을 커밋
  
  2)커밋한 내용을 원격 저장소로 업로드(원격저장소 갱신)
  
  3)복제된 저장소에서 커밋 로그 확인
<br>

> **6. 수동으로 내려받기**

- **자동 병합(pull) 처리 과정** : <br>

  1)원격 서버에서 현재 커밋보다 더 최신 커밋 정보가 있을 때 내려받기<br>

  2)내려받은 커밋 정보는 임시 영역(=브랜치)에 저장<br>

  3)내려받은 최신 커밋을 현재 브랜치로 자동 병합<br>

<br>

> 📘 NOTE 
>> ⭐ **병합** : 원격 서버 파일 + 로컬 파일 -> 하나의 파일
>> 
>> ⭐ 여러 개발자와 협업하는 도중 충돌의 우려 존재   **-->**   **fetch** 사용 필요

<br>

- **가져오기(fetch)** : 원격 저장소에서 코드를 수동으로 내려받는 작업 실행<br>

  1)원격 저장소에 커밋된 코드를 임시 브랜치로 내려받기<br>

  2)내려받은 후 현재 브랜치와 자동 병합 x 
<br>

- **병합하기(merge)** : 내려받은 커밋을 로컬 저장소에 적용하는 기능 수행

  - 명령어 : git merge 원격저장소별칭/브랜치 이름
<br>
 
> **7. 순서**

- **최신 상태**

  - push를 위해 로컬 저장소를 최신 상태로 유지 필요
  
  - 로컬 저장소의 상태가 원격 저장소의 상태보다 최신

<br>

> 📌 커밋이 순차적이지 않을 때 깃을 push 동작을 거부 <br>
>
> ex)서버의 마지막 커밋(최신)과 push되는 커밋(최신 정보x) 둘을 병합할 때 <br>
>
> **-->** pull or fetch 작업으로 로컬 저장소를 갱신하면 문제 해결 <br>

<br>

- **충돌 방지**

  1)push 충돌 방지 : 미리 원격 저장소 확인, pull 명령어로 커밋 갱신 확인 
  
  2)로컬 저장소와 원격 저장소의 상태를 최신으로 유지 
  
  3)권장 순서 : pull -> coding -> commit -> pull -> push 
  
  4)소스트리 : push 전 로컬 저장소와 차이를 쉽게 확인 가능 

<br>

> 📘 NOTE 
>> ⭐ **인증 정보 캐시** : 아이디와 비밀번호를 임시적으로 보관 <br>
(명령어 : git config --global credential.helper cache)
>>
>> ⭐ 깃을 원격 저장소에 연결 시 ./git/config 파일 안에 리모트 연결 설정 정보가 자동 추가
  
<br>

> **8. 정리** 

- **깃의 기능** : 오픈 소스를 활성화하는데 가장 많은 기여를 함

  1)코드 이력 관리 및 다른 개발자와의 협업 도구 
  
  2)다양한 종류의 서버 지원 
  
  3)원격저장소와 커밋 정보 주고 받기 
