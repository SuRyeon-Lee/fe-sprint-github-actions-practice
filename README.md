# fe-sprint-github-actions-practice
기존 아고라스테이츠 서버 연습 코드를 사용하여 깃허브 액션을 연습해봅니다.
[깃헙 액션 공식문서](https://docs.github.com/en/actions)

<br/><br/>

## 알게 된 사실
* Github actions를 무료로 사용하기 위해선 레포지토리가 public 이어야 한다.
* 비공개 레포지토리의 경우 Github Actions가 작동할 때의 용량과 시간이 제한되어있다.
* GitHub Actions는 Github가 공식적으로 제공하는 빌드, 테스트 및 배포 파이프라인을 자동화할 수 있는 CI/CD 플랫폼이다.
* 레포지토리에서 Pull Request 나 push 같은 이벤트를 트리거로 GitHub 작업 워크플로(Workflow)를 구성할 수 있다.
* 워크플로는 하나 이상의 작업이 실행되는 자동화 프로세스로, 각 작업은 자체 가상 머신 또는 컨테이너 내부에서 실행된다.
* 워크플로는 .yml (혹은 .yaml ) 파일에 의해 구성되며, 테스트, 배포 등 기능에 따라 여러개의 워크플로도 만들 수 있다.
* 생성된 워크플로는 .github/workflows 디렉토리 이하에 위치한다.