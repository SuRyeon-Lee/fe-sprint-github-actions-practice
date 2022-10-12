# 🔥 fe-sprint-github-actions-practice
* 기존 아고라스테이츠 서버 연습 코드를 사용하여 깃허브 액션을 연습해본다.
[깃헙 액션 공식문서](https://docs.github.com/en/actions)
* .yaml(.yml) 문법을 정리한다.

<br/><br/>

## 💡 깃헙 액션에 대하여
* Github actions를 무료로 사용하기 위해선 레포지토리가 public 이어야 한다.
* 비공개 레포지토리의 경우 Github Actions가 작동할 때의 용량과 시간이 제한되어있다.
* GitHub Actions는 Github가 공식적으로 제공하는 빌드, 테스트 및 배포 파이프라인을 자동화할 수 있는 CI/CD 플랫폼이다.
* 레포지토리에서 Pull Request 나 push 같은 이벤트를 트리거로 GitHub 작업 워크플로(Workflow)를 구성할 수 있다.
* 워크플로는 하나 이상의 작업이 실행되는 자동화 프로세스로, 각 작업은 자체 가상 머신 또는 컨테이너 내부에서 실행된다.
* 워크플로는 .yml (혹은 .yaml ) 파일에 의해 구성되며, 테스트, 배포 등 기능에 따라 여러개의 워크플로도 만들 수 있다.
* 생성된 워크플로는 .github/workflows 디렉토리 이하에 위치한다.

<br/><br/>

## 🤔 YAML이란
* **Yet Another Markup Language**의 약자로, json같이 사람이 읽을 수 있는 데이터 직렬화 언어를 말한다.
*  .yaml 혹은 .yml 확장자를 가진다.
* 읽고 이해하기 쉬우며 다른 프로그래밍 언어와 함꼐 사용하기 좋다. 
* 설정 파일(configure file 등)에 사용하기에 좋다.
* 유연성과 접근성 덕분에 깃헙 액션과 같은 자동화 프로세스를 생성하는 데에도 사용된다.(ex. 쿠버네티스)

<br/><br/>

## 🥊 JSON vs YAML
* 아래는 Github actions 설정을 위해 작성된 YAML 파일 예제이다.
```yaml
name: Bare Minimum Requirements
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Bare Minimum Requirements
        uses: actions/setup-node@v1
        with:
          node-version: '16'
      - run: npm install
      - run: npm test
```
* 아래는 MDN의 JSON 파일이다.
```json
{
  "squadName": "Super hero squad",
  "homeTown": "Metro City",
  "formed": 2016,
  "secretBase": "Super tower",
  "active": true,
  "members": [
    {
      "name": "Molecule Man",
      "age": 29,
      "secretIdentity": "Dan Jukes",
      "powers": [
        "Radiation resistance",
        "Turning tiny",
        "Radiation blast"
      ]
    }
  ]
}
```
**💙공통점**
* JSON 파일과 YAML 파일은 key-value 형태로 작성된 파일이다.
* JSON 파일과 YAML 파일은 계층 구조를 가진다.

<br/>

**💎차이점**
* YAML 파일은 "" (큰따옴표, double quotation marks) 없이 문자열 작성이 가능해, 설정을 위한 스펙이나 프로퍼티 값 등이 JSON 파일에 비해 한 눈에 들어온다.
* SON 파일처럼 {} 형태로 감싸줄 필요도 없기 때문에 스코프의 압박(잘못 쓰면 일일이 어디가 처음이고 끝인지 찾아야 하는 등)에서 벗어날 수도 있다.
*  YAML 파일은 JSON 파일과 다르게 주석을 작성할 수 있다. 😮
* YAML은 JSON의 상위 호환 격이므로, 기존 json문서를 그대로 yaml파일로 사용하거나 원하는 부분만 손볼 수 있다. (반대로 yaml을 json으로 변환해 사용할 수도 있다)

<br/><br/>

## 🥊 YAML 문법

#### ♦️ 문서시작, 끝, 주석
```yaml
#이런 식으로 앞에 '#'을 적어 주석을 작성

--- #문서 시작 (optional)

#이 사이에 내용 (---와 ...사이)

... #문서 끝 (optional)
```
<br/>

#### ♦️ 들여쓰기
들여쓰기는 기본적으로 2칸 또는 4칸을 지원하나, 보통 2칸씩 들여쓰는 것을 추천한다. 탭 키가 아닌 스페이스 키로 들여써야 함.
<br/>

#### ♦️ 기본표현
```yaml
key: value
# 이런식으로 적고 🛑 ':' 다믐엔 무조건!! 공백 문자가 와야함
```
<br/>

#### ♦️ 자료형
* **int, string, boolean, 리스트, 매핑**을 지원
* 여기서 int와 string 타입은 스칼라(Scalar)라고 한다.
* 배열 혹은 리스트는 시퀀스(Sequence)라고 한다.
* 매핑에는 기본 표현인 key-value 쌍 및 hash, dictionary가 포함된다.
```yaml
#int(숫자)
int_type: 1

#string(문자열)
string_type: "1"

#blooean(참/거짓)
boolean_true_type: true
boolean_false_type: false

#이외에 yes, no로 작성하기도 함.
yaml_easy: yes
yaml_difficult: no

#리스트(배열 형태) '-'로 표현.
person:
  name: Chungsub Kim
  job: Developer
  skills: 
    - docker
    - kubernetes
  # JSON 형식의 "skill" : [docker, kubernetes]와 같음.
```
<br/>

#### ♦️ 객체
* 객체 표현은 key 작성 후 **두 칸을 들여써서** key-value 형태로 작성을 해주거나, key를 작성 후 **중괄호({})**로 한 번 묶고 key-value 형태로 작성한다.
```yaml
key: 
  key: value
  key: value

#또는 이렇게도 작성한다. 가독성을 위해 사용한다.
key: {
  key: value,
  key: value
}
```
<br/>

#### ♦️ Text
* 줄바꿈 표현(|)과 줄바꿈 무시 표현(>)이 있다.
```yaml
# |: 줄바꿈 표현
# JSON 형식의 "comment_line_break": "Hello codestates.\nIm kimcoding.\n"과 동일
comment_line_break: |
  Hello codestates.
  Im kimcoding.

# >: 줄바꿈 무시 표현
# JSON 형식의 "comment_single_line": "Hello world my first coding."와 동일
comment_single_line: >
  Hello world
  my first coding.
```
<br/>

#### ♦️ 문자열 따옴표
* key-value 쌍에서 value에 :가 들어간 경우는 **반드시 따옴표가 필요**
```yaml
# ❌ error 남
windows_drive: c:

# ⭕️ 이렇게 써야 함
windows_drive: "c:"
windows_drive: 'c:'
```