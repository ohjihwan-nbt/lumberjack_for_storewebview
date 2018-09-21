# 더퀴즈라이브 스토어를 위한 lumberjack 라이브러리

## 개요
- SharedWebView의 getUserProfile 메서드 호출 결과를 Promise를 이용하여 비동기 처리한 뒤, 알맞은 로깅 데이터를 전달합니다.
- stage 환경 (localhost, 192로 시작되는 IP, play-stg 서브도메인)에서의 로그는 info.isStage = true로 설정되어, 프로덕션 환경의 데이터를 선별할 수 있습니다.

## 노드 의존성 설치
```bash
$ npm install
```

## uglify된 파일 생성
```bash
# 아래 명령을 통해 lumberjack_for_storewebview.min.js 파일이 생성됩니다.
$ npm start
```

## 웹 브라우저에서 사용방법
```html
<script src="./lumberjack_for_storewebview.min.js"></script>
<script>
// 빌드된 파일을 로딩하면, window.lumberjack 객체가 생성됩니다.
// lumberjack 객체의 track 함수를 사용하여 elasticsearch에 데이터가 적재되도록 합니다.
var info = { /* info 속성으로 전달할 페이지별 동적 속성을 이곳에 할당합니다. */ };

window.lumberjack.track('event', '페이지명::이벤트이름::event', info);
</script>
```