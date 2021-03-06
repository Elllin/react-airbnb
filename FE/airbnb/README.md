# airbnb

- 프로젝트 기간 : 5 / 18 ~ 6 / 5 (3주)
- 인원 : 백엔드 1명, 프론트 2명

3주 동안 airbnb 프로젝트를 정신없이 진행했다. 그리고 이번 프로젝트를 통해서 react를 좀 더 깊게 알게 된 것 같다. 지금까지는 react를 얕게 알고 사용해 온 것 같다. 페어 프로그래밍을 하며 느낀 장점은 내가 몰랐던 지식들을 페어를 통해 알게 되어 정말 큰 도움이 되었고 항상 내가 생각하는 방식대로 코딩을 하다가 다른 사람의 생각을 듣고 다른 사람의 생각하는 방식을 듣다 보면 아 이런 방법도 있구나 미처 내가 생각하지 못했던 방법을 알게 되어 항상 같은 방식으로 생각하던 내가 다른 차원으로 생각을 할 수 있게 된 것 같다.

## 구조

[ducks구조](https://github.com/JisuPark/ducks-modular-redux)
ducks 구조로 진행했다. ducks 구조는 간단하게는 actionType, action, reducer를 하나의 파일로 묶는 것인데 왜 이러한 구조를 택했냐하면 위 세 가지를 다른 파일에 각각 관리를 하면 수정을 할 때에는 각각 파일에 들어가 수정을 해야 하고 서로 연관돼있는 내용들이라 각각 파일에 들어가 확인하며 프로그래밍하게 된다면 불편함이 따를 것이라 생각되었고 이렇게 연관된 내용들을 하나의 파일로 묶어 둔다면 서로 응집 도도 높아질 것 같고 프로그래밍하는 데에 있어 편할 것이라 생각했다.

## 페어와 협업

예를 들면 rheostat의 라이브러리를 사용해서 차트 그리는 것을 집에서 각자 연습해보고 생각을 공유하기로 했다. 사용법을 익히고 차트를 그리는데 key 값이 같다는 오류가 발생한 것이었다. 배열로 값을 받고 차트를 그리는 것인데 알고 보니 배열로 받는 값들을 라이브러리 내부 로직에서 key 값으로 쓰고 있었고 그 배열의 값이 중복되면 오류가 발생하는 것이었다. 이 로직을 보고 왜 배열의 값을 key 값으로 했을까? 이상하다는 생각을 했고 여기서 더 나아가지 못하고 그러면 서버에서 값을 받을 때 중복되지 않도록 값을 받으며 중복되는 값은 몇 개가 있는지 받으면 되겠다 하고 생각했다. 예를 들어 [10,10,10,20,25,30]이라면 [10,20,25,30] 이런 식으로 값을 받고 10은 3개라는 값을 서버에서 받으면 오류 없이 동작하지 않을까 하고 생각하고 있었다. 그리고 학원에 가서 페어와 공유하니까 페어의 생각은 달랐다. 배열의 값들을 key 값으로 쓴다는 것은 이 라이브러리는 차트를 그려주는 라이브러리가 아니라고 생각한 것이다. 페어는 key 값을 넣으면 발생하는 오류를 비중 있게 생각하고 고민했고 만약 이들이 차트 그리는 기능을 제공했다면 key 값으로 배열의 값을 넣지 않았을 것이고 story book에도 차트 기능이 있었을 것이라는 생각을 한 것이다. 난 미쳐 거기까지 생각을 못 했는데 머리를 쾅 맞은 기분이었다. 오류를 발견했고 key 값이 이상하다는 것을 발견했지만 더 심도 있게 고민을 못한 것이다. 이로 인해 많은 생각과 반성을 하게 되었고 다른 사람과 생각을 공유하니 나의 사고방식에서 벗어나 더 넓은 영역까지 고민하고 생각할 수 있다는 것이 좋았었다. 결국 페어의 생각을 훔쳐 내 것으로 만들 수 있다는 것이 큰 장점이었다.

단점이라면 제약사항이 많고 서로의 의견이 다르기 때문에 좀 더 양보가 필요하고 하고 그만큼 배려가 더욱 필요한 것 같다. 

## 이번 미션에서 신경쓴 점

1. url의 parameter로 필터링 한 데이터를 붙여서 서버에 보냈다. parameter 처리를 처음 경험해서 예외 처리할 사항도 많고 어려움이 많았다.

2. 새로 고침해도 필터링 한 정보가 유지되어야 한다고 생각되어(사용성 측면) 새로 고침해도 url 정보가 유지되도록 처리했다.

3. 차트와 페이지네이션 기능을 라이브러리의 도움 없이 직접 구현해 보기로 했다. 차트는 페어가 담당하고 나는 페이지네이션을 담당했다.
직접 구현해보니 생각보다 고려해야 할 문제가 많아 어려웠지만 구현하고 나니 뿌듯했다.

## 개선할 점

컴포넌트를 좀 더 잘게 분리했으면 코드가 좀 더 깔끔하고 재사용 측면에서도 높아졌을 것이라는 생각을 했다. 코드를 구현할 당시에는 이 코드는 여기서 한 번만 쓰이니까 따로 컴포넌트로 분리를 안 해도 되겠지 하고 생각했지만 react 공식 문서를 읽어보니 컴포넌트를 더 작은 컴포넌트로 나누는 것을 두려워하지 말라고 했고 그렇게 함으로써 보기에도 훨씬 깔끔하고 나중에 컴포넌트 재사용에도 좋다는 사실을 깨달았다. 다음 미션 때는 좀 더 컴포넌트를 나눠보려고 한다.

## routing처리의 오류

배포 후 데모 날 새로 고침을 하니 404에러가 발생한 것이다. 너무 당황해서 이유를 계속 생각했고 결국 데모가 끝나도 오류를 해결하지 못했다. 데모 당일이라 너무 식은땀이 났고 결국 local 환경에서 데모를 이어 나가야 했다. 데모가 끝난 뒤 계속 팀원들과 머리를 모아 문제를 해결하려 생각했고 문뜩 머릿속에서 떠올랐다. routing을 하면 새로 고침 시 서버에서 설정해 주어야 하는 것이 있다는 게 생각이 났다. 그래서 열심히 검색을 해봤고 결과는 이러했다.

url path가 변경되면 브라우저가 해당 path에 대한 새로운 html을 서버에 요청하는데 spa에서는 index.html 파일이 하라서 생기는 문제다.
특정 html 즉 index.html을 계속 응답하게 해서 해결을 하면 된다. 아니면 서버에서 /를 index.html로 전송하는 설정을 하면 된다.

아래 내용을 읽어보니 금방 이해가 됐다.

>개발서버쪽에서 historyApiFallback 설정을 통하여 어떤 요청으로 들어오던 저희 어플리케이션이 불러와져있는 index.html 을 보여주도록 설정하기 때문입니다.
링크를 이렇게 직접 입력해서 들어갈 때에는, 서버라우트를 한번 타게 됩니다. 그러면 서버쪽에서 리액트앱으로 연결시켜줘야하죠. 실제 서버에서는, 우리가 설정한 라우트에 들어왔을때 리액트 앱이 보여지는 페이지를 보여주게 하거나, 혹은 API 등 사전 준비된 라우트를 제외한 모든 요청을 리액트 앱쪽으로 연결시켜주는 작업을 해야합니다. 그렇게 하지 않으면 서버측에서는 연결 할 라우트가 없어서 404 Not Found 페이지만 뜰 것입니다.

참고 

[VELOPERT.LOG - 리액트 라우터](https://velopert.com/3417)

서버에서는 아래와 같이 설정이 필요한 것 같다.

```
       error_page 404 =200 /index.html;
        error_page 502 =200 /index.html;
        location / {
                # First attempt to serve request as file, then
                # as directory, then fall back to displaying a 404.
                try_files $uri $uri/ =404;
        }
        
   location /api/ {
        rewrite ^/api(/.*)$ $1 break;
        proxy_pass http://localhost:8080;
              }
  ```

참고하면 좋은 자료
[Nginx를 사용하여 프록시 서버 만들기](https://velog.io/@jeff0720/2018-11-18-2111-%EC%9E%91%EC%84%B1%EB%90%A8-iojomvsf0n)
[Nginx로 React를 배포하는 방법](https://blog.naver.com/PostView.nhn?blogId=dilrong&logNo=221497936351)
