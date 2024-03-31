1. 구조적 Identity?
- 조건에 따라 그려지는 View의 제너릭 타입을 구조화할 수 있다.
- 이 조건에 따라 암시적 ID를 제공해준다.
```swift
// _ConditionalContent<EmptyView, View> // true, false
var body: some View {
	if users.isEmpty { EmptyView() }
	else { View() }
}
```
2. View Identity
- View의 상태와 identity는 다르다.
- 상태가 업데이트 되어도 identity는 동일하며, View의 수명은 identity 지속시간에 연관된다.
  - State, StateObject를 갖고 있는 View는 그 lifetime 동안 유지된다.
  - 메모리에서 할당해제되는 시점은 if 조건에 의해 분기되거나 onDisappear 등에 의해 조정.
  - View ID 수정 -> 상태 변경

3. Dependency
- State, 속성 모두 dependency라 할 수 있다.
- 의존성이 변경될 때, 해당 의존성과 관련된 View가 새로운 body를 갖도록 인스턴스화 한다.
  - 이 때, Identity가 핵심이 된다. 변경사항을 갖는 View를 제대로 추적하도록 함.

4. 명시적 Identity
- 안정성: 명시적 ID는 성능에 도움을 준다. 저장소를 지속적으로 보관하거나 의존성 그래프를 유지할 수 있기 때문
- 고유성: 고유하지 않으면 의도하지 않은 동작할 수 있다.

5. MVVM
- 비즈니스로직과 UI를 분리, 데이터 바인딩으로 통해 View-ViewModel 동기화를 자동화하는 아키텍쳐 패턴
- 역할을 분리할 수 있고, 확장성과 재사용성, VM에 대한 테스트 용이성을 가질 수 있다.

6. `@main`
- App 프로토콜이 main 함수의 기본 구현을 제공한다.
- App 프로토콜은 body가 Scene을 만족하길 요구하며, Scene의 단계를 Environment 에서 접근할 수 있다.
- 애플리케이션의 시작점을 제공한다.