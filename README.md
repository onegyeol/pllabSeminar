# 📖 PL LAB Seminar 발표 자료 업로드
매 학기마다 진행된 PL LAB 세미나의 발표 자료를 업로드하는 공간입니다. <br/><br/><br/>

![Elixir](https://img.shields.io/badge/Elixir-4B275F?style=for-the-badge&logo=elixir&logoColor=white) <br/>
Elixir는 Erlang VM(BEAM) 위에서 작동하는 함수형 프로그래밍 언어로, 동시성, 분산 처리, 가독성 높은 문법을 특징으로 웹 애플리케이션 개발에 적합합니다. 또한, 경량 프로세스와 패턴 매칭 등으로 높은 생산성과 유지 보수성을 제공합니다.
Elixir라는 단어 자체가 생소하기도 했고 처음 배우는 함수형 언어라 어려움이 많았지만 덕분에 다른 언어들을 비교적 쉽게 배울 수 있었던 것 같습니다.<br/><br/>


![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white) <br/>
C언어는 시스템 소프트웨어와 임베디드 시스템 개발에 주로 사용되는 절차적 프로그래밍 언어로, 메모리 관리와 포인터 연산 등 저수준 제어가 가능해 고성능 애플리케이션 개발에 적합합니다. 이식성이 뛰어나고 다양한 플랫폼에서 컴파일러 지원을 받아 폭넓게 활용됩니다.
C언어에 대해 기초적인 지식을 알고있었으나 이번 세미나를 통해 심화적인 C언어의 기능까지 배울 수 있었습니다. <br/><br/>


![Next.js](https://img.shields.io/badge/Next.js-000?logo=nextdotjs&logoColor=fff&style=for-the-badge) <br/>
Next.js는 React를 기반으로 한 오픈소스 프레임워크로, 서버사이드 렌더링(SSR)과 정적 사이트 생성(SSG)을 지원하여 SEO 및 성능이 향상된 웹 애플리케이션을 쉽게 개발할 수 있게 해줍니다. 또한, 라우팅, 데이터 페칭, 이미지 최적화 등 다양한 기능을 제공하여 개발자 경험을 개선합니다.<br/><br/>


![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white) <br/>
Node.js는 자바스크립트 엔진을 기반으로 하는 자바스크립트 런타임 환경으로, 이벤트 기반, 비동기 I/O를 지원하여 높은 동시성과 확장성을 갖춘 서버 애플리케이션을 개발할 수 있게 합니다. 서버 측 애플리케이션 개발에 널리 사용되며, npm 패키지 관리자를 통해 다양한 라이브러리와 도구를 사용할 수 있습니다.
이번 세미나는 개념 위주가 아닌 실습 위주로 진행되었기에 Node.js로 서버를 구축하는 방법에 대해서도 배울 수 있었습니다. <br/><br/>


![GO](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)


### 트러블 슈팅
1. 실행 오류
```
main.go:1:1: expected 'package', found 'EOF'
```
이 에러는 Go 컴파일러가 package 키워드를 예상했는데 파일이 비어 있다고(EOL, end-of-file) 판단한 경우 발생한다고 한다.
```
rm main.go
touch main.go
```
다음과 같은 명령어를 차례대로 적어준 뒤, 삭제된 파일의 코드를 옮겨적으니 실행이 되었다.

2. 실행 중 포인터 리시버 오류
```
# methodsAndInterfaces
./main.go:38:3: cannot use Product{…} (value of struct type Product) as Expense value in array or slice literal: Product does not implement Expense (method getCost has pointer receiver)
```
이 에러는 
- Product의 getCost 메서드가 포인터 리시버로 정의되었지만,
- 인터페이스에 값 타입(Product) 을 넘겨 인터페이스 구현에 실패하여 오류가 난 것이다.

포인터로 값을 넘기도록 수정해주니 제대로 실행되었다.
```
expenses := []Expense{
    &Product{"kayak", "waterSports", 275},
}
```
포인터 리시버에 대해 처음 사용하다보니 이런 오류가 발생했던 것 같다.


