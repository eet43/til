소셜 로그인 여행기
==


카카오 소셜 로그인하며 얻은 지식 기록
--


우선 `'/`' 로 들어오는 요청에 `index.html` 파일을 렌더링 해준다. <br><br>
물론 `index.html` 파일 안에는 카카오톡으로 연결되는 로그인 버튼이 생성되어 있어야 한다. <br><br>
카카오톡 로그인 버튼을 누르게 되면, 카카오 공식 문서에 나와 있는 대로 `REST_API_KEY`, `CLIENT_KEY` 값이 들어있는 `url` 로 요청 신호를 보낸다.<br><br>
카카오 서버 로직에 의해, 개인정보 동의를 하게 되면, 자동으로 `redirect` 가 될 `url` 을 매핑해주어야 한다. <br><br>
url 을 타고 들어가면, `accessToken`, `refreshToken` 을 얻을 수 있게끔 코드를 작성한다. 대부분 문서에 나와있다.<br><br>
그 후의 로직은 어떤 서비스를 설계하냐에 따라 다르다. 유저 정보가 필요하다면 원하는 데이터를 `accessToken` 을 헤더에 담아 카카오톡 서버에 요청하면 된다.<br><br><br>
다만, 카카오톡 토큰은 쭉 사용하는걸 권장하지 않는다. 때문에 카카오 정보를 통한 본인 서비스만의 토큰을 발급한 뒤, 그 토큰으로 데이터를 주고 받는게 좋다.<br><br>
또한 회원가입, 로그아웃, 탈퇴 서비스는 따로 제공하지 않기 때문에 직접 작성해야한다.<br><br>
대부분 쿠키, 세션으로 자동 로그인 상태와 로그아웃 상태를 관리한다.<br><br>
