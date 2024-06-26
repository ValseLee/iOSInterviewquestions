1. 컴퓨터 구조와 관련하여 CPU, RAM, 저장장치의 역할과 상호 작용에 대해 설명해 주세요.
- CPU는 명령을 처리하고 실행한다.
- RAM은 일시적 데이터 저장소로 빠른 읽기/쓰기를 제공하며 저장장치는 데이터를 영구적으로 보관한다.
- CPU는 RAM과 저장장치에서 데이터와 명령어를 불러와 처리한다.

2. 캐시 메모리의 개념과 종류, 역할에 대해 설명해 주세요.
- 캐시 메모리는 버퍼라고 불리기도 하는 CPU와 RAM **사이의 고속 데이터 저장소**이다.
- 자주 사용되는 데이터를 임시로 저장해 빠른 접근을 지원한다.
- L1, L2, L3 등의 다양한 레벨이 있으며, 내부에 가까울수록 속도가 빠르다.

3. CPU 아키텍처의 종류(예: ARM, x86)와 특징에 대해 설명해 주세요.
- ARM은 저전력, 고효율에 적합한 구조로 모바일 기기에 주로 사용하고, x86은 고성능을 제공하는 구조로 PC와 서버에 주로 사용한다.
- ARM은 RISC 기반, x86은 CISC 기반의 명령어 세트를 사용한다.

4. iOS 기기에서 사용되는 AP(Application Processor)의 특징과 역할에 대해 설명해 주세요.
- Application Processor(AP)는 iOS 기기의 중심으로 앱 실행, 그래픽 처리, 데이터 관리 등을 담당하며, 효율성과 성능을 극대화하기 위해 설계되었다.
- Apple의 A시리즈 칩이 해당된다.

5. 운영체제의 역할과 iOS에서의 운영체제 구조에 대해 설명해 주세요.
- 운영체제는 하드웨어와 소프트웨어 사이의 인터페이스이다.
- 자원과 프로세스 및 메모리 관리, 보안 확보 등의 기능을 제공한다.
- iOS는 샌드박스 환경을 제공함으로서 보안과 안정성을 강화한다.

6. 프로세스와 스레드의 차이점, iOS에서의 프로세스와 스레드 관리 방법에 대해 설명해 주세요.
- 프로세스는 CPU에 의해 처리되는 작업의 단위이며, Thread는 프로세스의 각 실행 단위이다.
- 프로세스는 각 작업의 상태와 넘버, 명령어 주소 등을 갖는 Context를 PCB에 저장하여 프로세스 전환하고,
- Thread는 자체 스택에서 명령어를 실행하고 메모리의 코드, 데이터, 힙을 공유하여 명령을 실행할 수 있다.
- iOS는 GCD(Grand Central Dispatch)를 통해 멀티 스레드 환경을 구축할 수 있으며, 최적화할 수 있다.

7. 메모리 관리 기법 중 iOS에서 사용되는 방식과 그 특징에 대해 설명해 주세요.
- iOS는 자동 참조 카운팅(ARC)을 사용하여 메모리 관리를 자동화하고, 직접 메모리를 관리하는 수고를 덜었다.
- ARC는 객체의 참조 횟수를 추적하여 더 이상 필요 없을 때 자동으로 객체를 할당 해제한다.
- 컴파일러의 기능에 해당하며, 런타임에 retain 과 release를 실행한다.

8. iOS의 샌드박스(Sandbox) 개념과 역할, 앱 간 데이터 공유 방법에 대해 설명해 주세요.
- 샌드박스는 앱이 시스템의 다른 부분이나 다른 앱과 격리된 환경에서 실행되도록 하는 보안 기술이다.
- 앱 간 데이터 공유는 URL 스킴, 공유 확장 기능 등을 통해 제한적으로 가능하다.

9. (+10. +11.) iOS에서의 메모리 구조와 관리 방식에 대해 자세히 설명해 주세요.
- iOS 메모리는 코드, 데이터, 힙, 스택으로 구성되어 있다.
- 데이터 영역은 정적 데이터(static)를 저장하고 프로그램의 시작부터 끝까지 메모리에 할당되어 있다.
- 힙은 동적 할당되는 객체 타입을 저장하며, 스택은 함수의 스택 프레임, 로컬 변수 등을 저장하는 데에 사용된다.
- 힙에 저장된 객체 타입의 메모리 해제는 ARC에 의해 관리된다.
  - 객체(class)의 인스턴스가 애플리케이션의 런타임에 동적으로 할당되며, 

10. 스택 영역에서 함수 호출과 로컬 변수의 메모리 할당 및 해제 과정을 설명해 주세요.
- 메소드가 호출되면 스택 프레임이 형성되고, 스택 프레임 내부에 로컬 변수의 메모리가 할당된다.
- 메소드의 처리가 종료되면, return 되어 다른 메소드로 제어권이 넘어가면 로컬 변수 메모리가 할당 해제된다.
- 위 메모리 할당 및 관리 과정은 개발자가 개입할 여지없이 자동으로 컴파일러가 해결해 주지만, 최근 Swift 업데이트를 통해 consume 오퍼레이터가 추가되면서 로컬 변수의 메모리 관리에 접근할 여지가 생겼다.

11. 네트워크 프로토콜 스택과 iOS에서의 네트워크 통신 방식에 대해 설명해 주세요.
- 네트워크 프로토콜 스택은 통신을 위한 계층화된 아키텍처를 제공하며, iOS는 TCP/IP 프로토콜 스택을 사용한다.
- iOS 앱은 URL세션(`URLSession`) 등의 API를 통해 HTTP(HyperText Transfer Protocol) 요청을 보내고, TCP/IP 스택을 통해 데이터를 송수신한다.
- 통신을 위해 `URL`, `URLRequest`를 생성한 후, Task를 생성하여 resume 한다.
- 기존엔 `JSONSerialization` 을 썼었으나 현재는 `JSONDecoder` 등을 활용하여 HTTP body를 파싱할 수 있다.

12. HTTP와 HTTPS의 차이점, iOS에서의 보안 통신 방법에 대해 설명해 주세요.
- HTTP는 암호화되지 않은 텍스트로 데이터를 전송하는 반면, HTTPS는 SSL/TLS 프로토콜을 사용하여 데이터를 암호화한다.
- iOS에서는 ATS(App Transport Security)을 적용 및 HTTPS 통신을 강제함으로써 보안을 강화했다.

13. TCP와 UDP의 차이점에 대해서 설명해 주세요.
- TCP(Transmission Control Protocol)는 연결 지향적이고 신뢰성 있는 데이터 전송을 제공하는 반면, UDP(User Datagram Protocol)는 비연결성이며 최소한의 오버헤드로 빠른 데이터 전송을 가능하게 한다.
- TCP는 데이터의 순서와 무결성을 보장하지만, UDP는 그렇지 않다.
- **TCP(Transmission Control Protocol)**
  - 신뢰성 있는 데이터 전송: TCP는 데이터가 정확하게, 순서대로, 손실 없이 목적지에 도달하도록 보장. 이를 위해 데이터 패킷의 송수신을 확인하고, 필요한 경우 **재전송 수행**
  - 연결 지향적: 데이터 전송을 시작하기 전에 클라이언트와 서버 간의 연결 설정이 필요(3-way handshake 과정). 이 연결은 데이터 전송이 완료될 때까지 유지
  - 흐름 제어 및 혼잡 제어: 네트워크의 혼잡 상태나 수신자의 처리 능력을 고려하여 데이터 전송 속도 조절
  - 사용 사례: 이메일, 웹 페이지 로딩, 파일 전송 등 데이터의 정확성과 순서가 중요한 애플리케이션
- **UDP(User Datagram Protocol)**
  - 비신뢰성 있는 데이터 전송: UDP는 **데이터의 도착을 보장하지 않음**. 데이터 패킷이 손실되거나 순서가 바뀌어 도착할 수 있으며, 이에 대한 복구 메커니즘이 없음
  - 비연결 지향적: 연결 설정 없이 데이터를 바로 전송하여 오버헤드를 줄이고 데이터 전송 속도 향상
  - 간단하고 효율적: 흐름 제어나 혼잡 제어 기능이 없어 구현이 간단하며, 네트워크 오버헤드 낮음
  - 사용 사례: 실시간 비디오 스트리밍, 온라인 게임, VoIP(Voice over Internet Protocol) 등 실시간성이 중요하며 일부 데이터 손실이 허용되는 애플리케이션

14. 소켓 통신에 대해 설명해 주세요.
- 네트워크 상에서 데이터를 교환하기 위한 엔드포인트이다.
- TCP와 UDP 프로토콜을 사용하여 통신하며, 클라이언트-서버 모델에서 서로 다른 시스템 간에 데이터를 주고받는 데 사용한다.
- iOS에서는 BSD 소켓이나 고수준 API를 사용하여 소켓 통신을 구현할 수 있다.

15. REST API(Representational State Transfer Application Programming Interface)와 iOS에서의 네트워크 요청 및 응답 처리 방법에 대해 설명해 주세요.
- REST API는 네트워크 상에서 클라이언트와 서버 간의 통신을 위해 설계된 아키텍처 스타일이자 HTTP 메서드를 사용하여 서버에 자원을 요청하는 방식이다.
- iOS에서는 `URLSession`을 사용하여 REST API 요청을 보내고 JSON 형식으로 응답을 받아 처리할 수 있다.
- HTTP 프로토콜을 사용하여 구현되며, **자원(Resource)의 상태를 전송**하는 데 초점을 맞춘다.
- REST API를 통해 클라이언트는 서버에 있는 데이터를 생성, 읽기, 수정, 삭제(CRUD)할 수 있다.

16. REST API에서 Method들의 차이점을 설명해 주세요.
- GET: 조회. 서버의 데이터를 가져오기만 하며, 데이터에 변경을 가하지 않는다.
- POST: 생성. 서버에 데이터를 보내 새로운 항목을 생성하기 위해 사용한다.
- PUT: 업데이트. POST와 비슷하지만, 주로 기존 자원의 **전체 업데이트에 사용**한다.
- PATCH: 부분 업데이트. PUT과 비슷하지만, **일부 속성만 업데이트**하기 위해 사용한다.
- DELETE: 삭제. 지정된 URI의 자원을 삭제하기 위해 사용한다.

17. HTTP 상태 코드에 대해서 설명해 주세요.
- HTTP 상태 코드는 서버 응답의 상태를 나타내는 코드로, 200번대는 성공, 300번대는 리다이렉션, 400번대는 클라이언트 오류, 500번대는 서버 오류를 의미한다.

iOS에서 메모리 사이즈와 관련된 개념과 고려 사항에 대해 설명해 주세요.
iOS 디바이스의 메모리 제약과 앱 메모리 제한에 대해 설명해 주세요.
메모리 워드(word) 크기와 데이터 정렬(alignment)이 메모리 액세스 성능에 미치는 영향에 대해 설명해 주세요.
포인터 크기(32비트, 64비트)에 따른 메모리 사용량 차이와 고려 사항에 대해 설명해 주세요.
iOS 앱에서 대용량 데이터를 다룰 때 메모리 사이즈를 고려한 최적화 방안에 대해 설명해 주세요.

18. 알고리즘의 시간 복잡도와 공간 복잡도의 개념, 빅오 표기법에 대해 설명해 주세요.
- 시간 복잡도: 알고리즘을 실행하고 완료할 때까지 소요되는 시간을 의미하며, 입력 크기에 따라 결졍되는 실행 단계의 '수'로 측정한다.
  - 최선, 평균, 최악 경우에 따라 시간 복잡도를 분류할 수 있고, 대체로 최악 케이스로 평가한다.
  - Linear, Logarithmi, exponential scale 등으로 시간 복잡도를 평가할 수 있다.
- 공간 복잡도: 알고리즘 실행에 필요한 총 메모리 공간의 양을 의미한다.
  - 고정 공간(알고리즘에 필요한 입력 및 출력 변수, 상수 공간 등)과 가변 공간(동적으로 할당되는 메모리의 크기, 재귀 호출에 의한 스택 공간 등)을 합한 값으로 측정한다.
- 빅오 표기법: 알고리즘의 시간 복잡도와 공간 복잡도를 수학적으로 표현하는 데 사용되는 표기법이다.
  - 이는 최악의 경우에 대한 성능을 나타내며, 알고리즘의 성능을 입력 크기의 함수로서 근사치로 표기한다.
  - 빅오 표기법은 알고리즘의 상한을 설명하는 데 사용되며, 입력 크기가 커질 때 알고리즘의 성장률을 나타낸다.

19. 자주 사용되는 정렬 알고리즘(예: 퀵 정렬, 병합 정렬)의 동작 원리와 시간 복잡도를 설명해 주세요.
- 퀵 정렬과 병합 정렬 모두 분할 정복 알고리즘을 따르는 정렬 방식이다.
  - 분할 정복: 큰 문제를 더 나누어지지 않는 작은 문제(기저사례)로 분할한 다음, 해당 케이스에서의 솔루션을 큰 문제에 적용하는 알고리즘
- 퀵 정렬: 기준점과 다른 원소들을 비교하여 더 작은 원소는 왼쪽, 더 큰 원소는 오른쪽으로 옮기는 방식의 정렬이다.
  1. pivot을 0번째 원소로 정한다.
  2. 주어진 배열에 대해 pivot 보다 작은 값들을 좌측 배열로, pivot 보다 큰 값들을 우측 배열로 분할한다.
    - Partition: pivot과 각 값들을 비교하고, 기준점을 제공하는 메소드.
    ```swift
    var arr = [4,2,6,1,5]
    func partition(l, h) -> Int {
      var pivot = arr[l] // 4
      var i = l, j = h // 0, 4
      while i < j {
        while arr[i] <= pivot {
          i += 1
        }
        // i == 2
        while arr[j] > pivot { j -=  1 }

        // j == 3
        if i < j {
          arr.swapAt(i, j) // [4,1,6,2,5]
        }  
      }

      arr.swapAt(l, j) // [2,1,6,4,5]
      return j // 3
    }
    ```
  3. 분할한 배열에 대해 1-2번 과정을 반복한다.
  4. 배열 인수의 length가 1이 되면 분할된 값들을 재귀적으로 되먹인다.
  - 최선 O(nlogn)
  - 최악 O(n^2) | 이미 정렬된 배열이거나 0번 인덱스에 제일 크거나 작은 원소가 있을 때
  
- 병합 정렬: 배열을 전부 단위 원소로 분할한 후, 배열을 머지할 때 각 원소를 비교하여 정렬하는 알고리즘
  1. 가운데 원소를 기준으로 배열을 더 나눌 수 없을 때까지 분할한다.
  2. 머지하는 시점에 각 배열의 원소를 비교하여 만든 배열을 다시 재귀적으로 리턴한다.
  - 최선 O(nlogn)
  - 최악 O(nlogn)
  
이진 탐색의 원리와 시간 복잡도에 대해 설명해 주세요.
- 정렬된 배열의 중간 요소를 기준으로, 값을 비교하여 배열의 첫번째 요소를 가리키는 포인터와 끝 요소를 가리키는 포인터를 이동해가며 탐색하는 알고리즘이다.
- 최선의 경우: O(1) 첫 번째 비교에서 바로 찾고자 하는 요소를 발견하는 경우.
- 최악의 경우 및 평균적인 경우: O(logN) 이진 탐색은 각 단계에서 탐색 범위를 절반으로 줄이기 때문에, 최악의 경우에도 탐색에 필요한 비교 횟수는 로그 스케일로 증가한다.

다이나믹 프로그래밍(Dynamic Programming)의 개념을 설명해 주세요.
자료구조의 종류와 iOS 개발에서 자주 사용되는 자료구조에 대해 설명해 주세요.
배열, 연결 리스트, 스택, 큐의 특징과 iOS에서의 구현 방법을 설명해 주세요.

해시 테이블의 개념, 충돌 해결 방법을 설명해 주세요.
- 해시 테이블은 키를 기준으로 value를 인덱싱하는 자료구조이다. 
- 해시 함수를 통해 value에 대한 key를 매핑하며, 삽입, 삭제, 검색이 O(1)으로 수행된다.
- 해시 함수에서 나온 해시 값이 중복될 경우, Collision이 발생하며, Open Address 혹은 Chaining 기법으로 해결할 수 있다.
- Chaining:
  - 중복된 키값의 value를 Linked List로 저장한다. 구현이 편리하지만, worst case일 경우, 해쉬 테이블이 Linked List가 되는 마법(...)을 볼 수 있다.
- Open Address:
  - Double Hashing: 빈 슬롯이 나올 때까지 해시를 재진행한다. 해시 시도 횟수에 따라 서로 다른 해시 값이 나오도록 알고리즘을 구성한다.
  - Probing을 통해 빈 슬롯을 탐색할 수 있으나, 선형 Probing의 경우 슬롯이 뭉치게 되는 Clustering 문제를 야기할 수 있다.
    - 이 경우, 클러스터링이 두터워질 수록 빈 슬롯 탐색의 효율이 저하된다.

트리 자료구조의 종류(예: 이진 트리, 이진 탐색 트리, AVL 트리)을 설명해 주세요.
동시성 프로그래밍의 개념과 iOS에서의 동시성 처리 방식에 대해 설명해 주세요.
병렬 처리와 동시 처리의 차이, iOS에서의 멀티코어 활용 방안에 대해 설명해 주세요.

암호화와 보안의 기본 개념, iOS 앱 보안을 위한 방안에 대해 설명해 주세요.
- 암호화는 데이터를 암호로 변환해 비인가자의 접근으로부터 보호하는 기술이다.
- iOS 앱 보안을 강화하기 위해 암호화된 데이터 저장(예: Keychain 사용), 코드 서명, 앱 샌드박스 환경, HTTPS 통신 등을 사용한다.
  - App Transport Security (ATS): 네트워크 통신에서 HTTPS를 강제하여 데이터 전송 과정의 보안 강화
  - 데이터 암호화: 사용자 데이터 및 중요 정보는 Keychain과 같은 안전한 저장소에 암호화하여 저장
  - 코드 서명 및 앱 샌드박싱: 앱의 무단 변경을 방지하고, 앱 간 데이터 접근 제한
  - 앱 강화(App Hardening): 리버스 엔지니어링을 어렵게 하는 기술(예: 코드 난독화) 적용

대칭키 암호화와 비대칭키 암호화의 차이에 대해 설명해 주세요.
- 대칭키 암호화는 '같은 키'를 암호화와 복호화에 사용하는 방법이며, 비대칭키 암호화는 공개키로 암호화하고 개인키로 복호화하는 방법이다.
- 대칭키는 속도가 빠르지만 키 관리와 교환이 까다롭다(AES).
- 비대칭키(공개키)는 암호화와 복호화를 서로 분리하여 암호화 하는 방식이며, 주로 안전한 키 교환과 디지털 서명에 사용한다.(RSA)
  - 처리속도가 비교적 느리기 때문에, 대칭키 방식과 비대칭키 방식을 혼용하는 경우가 종종 있다.
  - 공공인증서가 비대칭키의 대표적인 예시
  - SSL 인증서를 통해 서버의 공개키를 브라우저(CA)에 전달하는 등, 네트워크 보안에도 활용된다.

해시 함수의 개념과 활용 사례에 대해 설명해 주세요.
- 해시 함수는 임의의 크기의 데이터를 고정된 크기의 데이터로 매핑하는 함수이다.
- 비밀번호 저장, 무결성 검증, 데이터 검색 최적화, 암호화 등에 주로 사용한다.
  - 비밀번호 저장: 사용자의 비밀번호를 직접 저장하지 않고, 비밀번호의 해시 값을 저장하여 보안성 향상. 로그인 시 입력된 비밀번호를 해시하여 저장된 해시 값과 비교하는 과정으로 사용자 인증
  - 데이터 무결성 검증: 소프트웨어나 파일 다운로드 시 제공되는 해시 값으로 파일의 변경 여부나 손상 여부 검증
  - 블록체인: 각 블록의 무결성을 보장하기 위해 전 블록의 해시 값을 현재 블록 포함.
- 해시는 원본 데이터를 복원할 수 없으며(일방향성), 연산의 속도가 빠르고 중복된 결과를 내지 않을수록 좋다.
- 대표적인 암호화 해싱 알고리즘의 경우, SHA-1(160비트) 과 SHA-2 그리고 이론의 영역인 SHA-3 족이 있다.
  - 아래의 모든 특징은 "**실제 계산 상황을 가정한다**".
  - 결정성(Deterministic): 동일한 입력에 대해 항상 동일한 출력(해시 값) 반환
  - 고속 연산(Fast Computation): 어떤 크기의 데이터에 대해서도 빠르게 해시 값 연산
  - 충돌 방지(Pre-image Resistance): **주어진 해시 값**에 대해, 해당 해시 값을 생성한 원본 데이터의 발견이 불가능해야 함
  - 약한 충돌 방지(Weak Collision Resistance): **주어진 입력 값**에 대해, 동일한 해시 값을 생성하는 다른 입력 값의 발견이 불가능해야 함
  - 강한 충돌 방지(Strong Collision Resistance): 서로 다른 두 입력 값이 동일한 해시 값을 생성할 수 없어야 함

**비밀번호 해싱 시나리오**
- 해싱은 비밀번호를 고정된 길이의 해시 값으로 변환하는 과정을 의미한다.
- 비밀번호 저장 시:
  - 사용자가 비밀번호를 생성하거나 변경할 때, 서버는 비밀번호를 받아 SHA-256 또는 SHA-512와 같은 안전한 해시 함수를 사용하여 해싱한다.
    - 연산 가능 속도에 따라 적합한 알고리즘을 선택한다.
  - 생성된 **해시 값**을 데이터베이스에 저장한다. 이때, 추가 보안을 위해 "솔트(Salt)"라는 무작위 데이터를 비밀번호에 추가하고 해싱할 수 있다.
  - 솔트는 해시 값에 대한 무작위성을 증가시켜, 같은 비밀번호라도 다른 해시 값을 생성하게 한다.
- 로그인 시:
  - 사용자가 로그인 시 자신의 비밀번호를 입력한다.
  - 서버는 입력된 비밀번호에 해싱할 때와 동일한 솔트를 추가하고, 동일한 해시 함수(SHA-256 또는 SHA-512)를 사용하여 해싱한다.
  - 이 해시 값을 데이터베이스에 저장된 해시 값과 비교한다.
  - 해시 값이 일치하면 로그인이 성공하며, 그렇지 않으면 로그인이 실패한다.

가상 메모리(Virtual Memory)의 개념과 동작 원리에 대해 설명해 주세요.
가상 메모리의 필요성과 장점에 대해 설명해 주세요.
페이징(Paging) 기법의 개념과 동작 원리, 페이지 테이블의 역할에 대해 설명해 주세요.
세그먼테이션(Segmentation) 기법의 개념과 페이징과의 차이점에 대해 설명해 주세요.
iOS 앱의 메모리 사용량 최적화를 위한 방안과 고려 사항에 대해 설명해 주세요.
메모리 캐싱 기법(예: NSCache, 이미지 캐싱)의 개념과 iOS에서의 구현 방법을 설명해 주세요.
대용량 데이터(예: 이미지, 비디오) 처리 시 메모리 최적화 방안(예: lazy loading, 썸네일 활용)에 대해 설명해 주세요.

데이터베이스의 종류와 iOS에서 주로 사용되는 데이터베이스에 대해 설명해 주세요.
- 관계형 데이터베이스: 테이블 간의 관계를 통해 데이터를 저장하고 조회한다. SQLite.
- 비관계형 데이터베이스: 키-값 쌍, 도큐먼트, 와이드 컬럼, 그래프 등 다양한 데이터 모델을 사용한다. Realm.
- iOS에서 주로 사용되는 데이터베이스에는 SQLite, Core Data(내부적으로 SQLite 사용 가능), Realm 등이 있다.

iOS에서 사용되는 SQLite, Core Data, Realm 등의 특징과 사용 사례를 설명해 주세요.
- SQLite:
  - 직접적인 SQL 쿼리를 사용하여 데이터 관리
  - 가볍고 로컬 저장소에 적합
  - 설정이 간단하고 직접적인 데이터베이스 관리가 필요한 경우 선택
  - SQL 쿼리를 사용하여 데이터를 저장, 조회, 수정할 수 있으며, 스키마 변경이 비교적 유연
  - Core Data보다 낮은 수준에서 작동하며, 데이터베이스 관리에 대한 더 세밀한 제어 가능
- Core Data(고수준 객체 관계 매핑 프레임워크):
  - 객체 그래프 관리자, 데이터 모델의 객체를 SQL로 자동 변환
  - 앱의 데이터 모델 관리
  - 대량의 데이터와 복잡한 데이터 구조를 가진 앱에서 주로 선택
  - 객체의 생명주기 관리, 객체 간 관계, 객체 상태의 영속성 관리 등을 제공
  - 복잡한 데이터 모델과 대량의 데이터를 효율적으로 관리할 수 있도록 설계됨
- Realm:
  - 빠르고, 직관적인 API 제공
  - 실시간 데이터베이스 데이터가 변경되면 UI가 반응하는 반응형 UI
  - 멀티 스레드 환경과 대규모 데이터를 다루는 앱에서 주로 선택

iOS 데이터의 저장 방식과 각 방식의 비교
- UserDefaults: 간단한 사용자 설정이나 소량의 데이터를 키-값 쌍으로 저장, 구조화된 데이터 관리에는 비효율적
- Keychain: 사용자의 로그인 정보나 개인 정보와 같이 보안이 중요한 데이터를 암호화를 거쳐 안전하게 저장, 앱이 삭제되더라도 보존
- 파일 시스템: 문서, 이미지, 비디오 등의 파일을 디바이스의 파일 시스템에 직접 저장합니다.

관계형 데이터베이스의 ACID 특성과 트랜잭션의 개념에 대해 설명해 주세요.
- DB에 저장된 데이터를 저장,삭제,수정하는 등의 액션을 '트랜잭션'이라 일컫는다.
- ACID는 데이터를 안정적인 처리에 고려해야 하는 특성을 의미한다.
- 트랜잭션은 완전히 수행되거나, 아예 수행되지 말아야 하며, 유효하게 시작하여 유효하게 끝나야 하며, 각 트랜잭션이 독립적이어야 하며, 트랜잭션이 완료되면 해당 결과가 영속적이어야 함을 의미한다.

iOS에서 데이터베이스 스키마 버전 관리와 마이그레이션을 처리하는 방법을 설명해 주세요.

iOS에서 자동 참조 카운팅(ARC)과 가비지 컬렉션(Garbage Collection)의 차이점에 대해 설명해 주세요.
가비지 컬렉션의 동작 원리와 장단점에 대해 설명해 주세요.
iOS에서 가비지 컬렉션을 사용하지 않는 이유와 ARC를 선택한 배경에 대해 설명해 주세요.