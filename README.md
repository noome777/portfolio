# portfolio 

![크기변환 me](https://user-images.githubusercontent.com/98254235/201081319-f2d3f92a-e2f2-4af3-bc58-87319daac266.jpg)

>안녕하세요. 꾸준히 성장하는 개발자 이아름입니다.


<br><br>
## 📌Intro.


### 새로운 일에 대한 도전
제가 하는 일들이 언제나 사람들에게 좀 더 나은 삶을 주었으면 하였습니다. 하지만, 일반적인 일들을 통해서는 그 한계가 명확하다고 느꼈습니다. 프로그래밍을 통해 사람들에게 도움을 줄 수 있는 서비스를 개발하여 사람들이 시간을 좀 더 가치 있게 쓸 수 있도록 해주고 싶습니다.


### 사람과의 협업, 성장
개발에 도전한 이후, 개발자에 있어서 협업은 가장 중요한 소통의 창구라는 것을 느꼈습니다. 2번의 팀 프로젝트를 통해 협업 중 팀원들과의 갈등 발생 시 경험과 팀 규칙을 활용하여 성공적으로 프로젝트를 마무리 할 수 있었습니다. 이러한 경험을 바탕으로 직무 수행에 있어서도 문제에 대해 함께 고민하고 해결 방안을 찾아가는 모습을 통해 원활한 의사소통을 할 수 있도록 노력하겠습니다.

<br><br>


## 📌Contact.
- Phone : 010-5302-1360
- Email : noome1360@gmail.com
- Blog : https://velog.io/@noome777
- GitHub : https://github.com/noome777

<br><br>

## 📌Project.
### ![크기변환 EveryWareLogo](https://user-images.githubusercontent.com/98254235/204456980-a975052e-6113-4ab5-8c30-85bfe22fea17.png)
> 사내 협업을 위해 메일, 전자 결재, 인사 관리, 근태 관리, 게시판, 일정 관리 등 여러 협업 기능을 한 곳에서 이용할 수 있는 그룹웨어 서비스 <br><br>
> 개발 기간 : <br> 2022.10.01 ~ 2022.11.12 <br><br>
> 개발 인원 :<br>  6명 / 팀 프로젝트 <br><br>
> 기술 스택 : <br> Java 11, HTML5, CSS3, Javascript ES6+, JSP, Spring-framework 5.3.22, Oracle database 21c XE - SQL Developer, Spring Security, mybatis, jQuery 3.6.1,
JSTL 1.2, JSON 2.8.9, AJAX <br>
><details>
><summary>담당 부분 erd 설계</summary>
><div markdown="1">
>
>![EveryWare_MyErd](https://user-images.githubusercontent.com/98254235/202900579-46aa8c68-469a-4405-a02b-422513ba3431.png)
>
></div>
></details>
> 
> [프로젝트 코드 및 설명](https://github.com/noome777/EveryWare) 참고
><br><br>
>
> ### `트러블 슈팅`
><details>
><summary>javamailsender 사용시 SSLHandshakeException 오류</summary>
><div markdown="1">
><br> 문제 : <br> NaverSMTP 사용시, SMTP 설정에 port 번호를 설정해줬는데도 불구하고 Could not connect to SMTP host 라는 에러 발생 <br><br>
>
>![Untitled (1)](https://user-images.githubusercontent.com/98254235/204472996-337be8c6-0291-4db7-bb51-6e6208ea2f2b.png)
>
>해결 : <br> 이메일 전송시에 javamail을 사용하게 되는데 ssl오류로 SSLHandshakeException 이 발생한 것 <br>
>JDK가 TLS 프로토콜이 비활성 되어있거나 TLS 버전이 상이하여 발생하는 것이기 때문에, 자바 메일에서 사용할 기본 TLS 버전을 1.2로 변경해 주어야 하였음.<br><br>
>따라서, System.setProperty("jdk.tls.client.protocols", "TLSv1.2");과 같은 형식으로 property를 설정해주면 되는데, 프로젝트에서 작성한 자바 코드와 유사하게 >serverInfo.put("mail.smtp.ssl.protocols", "TLSv1.2"); 로 맞추어 적어주어 에러를 해결
></div>
></details>
><details>
><summary>json으로 데이터 전송시 STATUSTEXT PARSEERROR 발생</summary>
><div markdown="1">
> <br> 문제 : <br> ajax에서 서버로 요청 시 데이터가 서버로 넘어가지 않는 문제 <br><br>
> 해결 : <br> datatype을 json으로 적었다가 삭제해주었음
></div>
></details>
><details>
><summary>쿠키 사용하여 아이디 저장이 잘 되지 않는 문제</summary>
><div markdown="1">
> <br> 문제 : <br> 아이디 저장 체크박스를 해제 한 상태에서도 로그인 화면으로 다시 돌아갔을 때 아이디가 저장되어 있어, 아이디 저장 기능이 제대로 구현하지 못하고 있는 상태. <br><br>
> 
> ![image](https://user-images.githubusercontent.com/98254235/204480508-7ac9bead-3e40-4f53-a122-1b9594c10846.png)
> <br><br>
> 해결 : <br> 아이디 저장 체크박스를 체크했을 때 vs 해제했을 때로 구분하여서 해제하였을 경우에는 cookie의 setMaxage(0); 으로  주어 쿠키가 제거될 수 있도록 함. (setMaxage 로 시간 설정을 해주는 이유는 쿠키에는 remove 메서드가 없으므로)
> <br> 만료 시킨 후에 addCookie를 하면 만료시켰다는 것을 응답 헤더에 추가하여 쿠키가 삭제가 된다.
></div>
></details>
><details>
><summary>깃허브 pull이전에 메인 브랜치에서 커밋 시 대처 방안</summary>
><div markdown="1">
> <br> 문제 : <br> 작업 내용을 merge 한 이후, 통합된 파일 내용을 pull을 받지 않고 프로젝트를 빌드하였을 때, 톰켓 에러가 발생하였음.<br><br>
> 해결 : <br>
> 1. 우선, 메인브랜치에서 풀을 당겨서 못받았던 파일을 다시 모두 받아준다. <br>
> 2. 풀 당긴 메인브랜치에서 새롭게 브랜치 생성한다.  <br>
> 3. 기존 브랜치에 작업한내용을 방금 만든 브랜치에 가져온다 : (기존브랜치 커밋지점 우클릭, 체리픽)
></div>
></details>
><details>
><summary>java.lang.ClassNotFoundException 에러</summary>
><div markdown="1">
><br> 문제 : <br>java.lang.ClassNotFoundException 에러 발생 <br><br>
> 해결 :  <br> Classpath에 로드하고자 하는 Class가 발견되지 않았을 때 발생한다. 보통은 빌드에 문제가 있는 경우로 clean이나 Class파일 삭제 후 재빌드를 수행하여 해결하였음.
> 따라서, 프로젝트의 OverworkVo 클래스를 삭제 후 다시 생성해주니 에러가 발생하지 않고 프로젝트가 잘 실행이 됨
></div>
></details>
><br>
>
> ### `회고`
> [ANBD 프로젝트 회고록](https://velog.io/@noome777/%ED%8C%8C%EC%9D%B4%EB%84%90-%EB%95%8C-%ED%95%A0-%EA%B2%83)
<br>

### <br> ![사본 -사본 -아나바다_로고_화질개선](https://user-images.githubusercontent.com/98254235/204457375-ba9be004-4c79-4ff9-8115-ff492d5134d2.png)
> 경기 침체와 리셀 시장의 확대에 따라 중고 거래 물품의 활성화를 위한 플랫폼 서비스 <br><br>
> 개발 기간 : <br> 2022.07.11~ 2022.08.26 <br><br>
> 개발 인원 : <br> 5명 / 팀 프로젝트 <br><br>
> 기술 스택 : <br>
> Java 11, HTML5, CSS3, Javascript ES6+, Oracle, JSP, Oracle database 21c XE - SQL Developer, jQuery 3.6.1,
JSTL 1.2, JSON 2.8.9, AJAX <br>
><details>
><summary>담당 부분 erd 설계</summary>
><div markdown="1">
>
>![image](https://user-images.githubusercontent.com/98254235/204517687-ffe8d8ab-6c1b-44da-ad63-fce1d745c00d.png)
>
></div>
></details>
>
> [프로젝트 코드  설명](https://github.com/Attadipa/semiGitTestRepo) 참고
><br><br>
>
> ### `트러블 슈팅`
> <details>
><summary>게시글 검색시 조회는 잘 되지만, 페이지를 변경하면 조회한 결과가 잘 반영되지 않는 문제</summary>
><div markdown="1">
> <br>  문제 : <br> 제목, 내용에 따른 검색 시 페이지 수는 잘 노출되지만, 다음 페이지를 누르면 다시 list의 첫 페이지로 이동되는 문제<br><br> 
> 해결 : <br> controller에서 게시글 검색 조건인 condition과 입력할 키워드의 keyword의 값을 setAttribute 하지 않아서 생긴 문제로 판단하여, controller에서 HttpServletRequest 객체를 이용하여 조회한 결과의 값을 view로 넘겨줄 수 있도록 코드를 변경하였음.
></div>
></details>
> <details>
><summary>로그인한 유저가 없을 시, 공지사항에 전혀 접근 하지 못함</summary>
><div markdown="1">
> <br>  문제 : <br> 로그인한 유저가 없을 시 공지사항에 전혀 접근 하지 못하고 있으므로 로그인한 유저가 없을 경우 게시물 상세 조회가 불가능 한 문제<br><br> 
> 해결 : <br> 중첩 if문을 이용하여 jstl 태그를 이용하여 코드를 변경하여 작성하였음. 로그인을 안 한 유저 또는 로그인을 했지만 관리자가 아닌 경우, 글을 삭제할 수 있는 권한이 없으므로 글 삭제 버튼을 보이지 않도록 하였음. 반면, 로그인 한 유저이면서 관리자인 경우, 글을 삭제할 수 있는 버튼을 보일 수 있도록 하였음.
></div>
></details>
><br>
>
> ### `회고`
> [EveryWare 프로젝트 회고록](https://velog.io/@noome777/EveryWare-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%ED%9A%8C%EA%B3%A0%EB%A1%9D)
