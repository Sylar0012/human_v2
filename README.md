# 미니프로젝트 humancloud2 - Rest하게 서버 만들기

### 개발 이유
 1. RestApi 서버에 대한 이해도를 높이기 위함.
 2. 1차 프로젝트시 미흡했던 코드 리팩토링.
 3. 팀별 협업을 통해 코드 컨벤션의 중요성을 알기 위함.

### 테이블 구성

![image](https://user-images.githubusercontent.com/108394995/210049877-b4fbc692-d985-4446-a392-6ab2eed80b76.png)

### 1. 제작 기간 
* 2022.10.26 ~ 2022.11.07

### 2.개발 환경

* Tool ![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white) 

* BackEnd  ![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=java&logoColor=white) ![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white) ![Gradle](https://img.shields.io/badge/Gradle-02303A.svg?style=for-the-badge&logo=Gradle&logoColor=white) ![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)

* Team 	![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white) ![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white) ![Notion](https://img.shields.io/badge/Notion-%23000000.svg?style=for-the-badge&logo=notion&logoColor=white) ![Discord](https://img.shields.io/badge/Discord-%235865F2.svg?style=for-the-badge&logo=discord&logoColor=white)

### 3. 이력서 API
https://subsequent-poppyseed-2fc.notion.site/2-bd914ca9dbd642ffae7e491c8cd0a2a1

### 4. 아키텍쳐
![image](https://user-images.githubusercontent.com/108394995/210051500-b1740556-2a00-4c7d-8314-69de845a5822.png)
* 스프링 기반의 개발에서 가장 보편적으로 사용되는 MVC 패턴에서 view만 빠진 형태
* 데이터 송수신을 위한 REST한 서버만이 필요해서 MC패턴이 되었다.

### 5. 코드 컨벤션
* 각 도메인의 ReqDto와 RespDto 내에서 static으로 세부 Dto 만들어서 사용
* Exception은 throw new RuntimeException("필요한 메세지")로 작성
* Controller의 경로는 인증이 필요한 메서드들은 "/s"를 앞에 붙이고, 그 이외의 것들은 "/도메인/**" 방식으로 작성
* Entity 생성자에는 @Builder 작성
* toEntity()는 Dto마다 작성, 관련 Dto 들도 각각 Dto 내에서 작성해서 사용
* insert는 SaveDto, update는 UpdateDto로 작성. 리스트를 보여주는 Dto는 도메인AllRespDto로 작성
* List 객체들의 변수명은 "도메인명List"로 작성
