# 📝 학습 목표

---

1. 리액트의 동작 방식에 대해 알아봅니다.
2. JSX 문법에 대해 알아봅니다.
3. 리액트 훅 중 useState에 대해 심도있게 알아봅니다.

<aside>
💡 이번 주차는 리액트에 대해 학습해보는 시간입니다. 전체적인 HTML, CSS, JS에 대한 기초 지식이 필요하므로, 0주차~1주차 학습을 필요로 합니다.

</aside>

# ⚠️  스터디 진행 방법

---

1. 스터디를 진행하기 전, 워크북 내용들을 모두 채우고 스터디에서 서로 모르는 내용들을 스터디원과 함께 공유해 주세요.
2. 실습과 미션은 워크북 내용들을 모두 완료한 후, 스터디 전에 진행해 오세요!
    - 1주 차 스터디 이전에 1주 차 워크북을 완성한 후 스터디를 진행해 주세요.
3. 스터디 시간에는 각자 해 온 미션들을 공유하고, 아래의 과정을 진행합니다.
    1. 스터디원과 함께 코드 리뷰 진행.
    2. 코드 리뷰 이후, 본인의 코드의 문제가 있는 경우 리팩토링 진행.
    3. 팀원들과, 조금 더 코드를 깔끔하게 작성할 수 있는 개선점이 있을지 고민 후, 리팩토링 진행.
    4. 각자 미션을 진행하면서 해결하지 못한 이슈를 공유 후, 해당 이슈를 도움받아 해결.
4. 매주 주어진 미션을 성실하게 제출합니다.
5. 🍠 이모지가 붙어있는 곳은, 직접 여러분들이 채워 넣으셔야 하는 부분입니다. 꼭 Google을 통한 검색을 하시고, VSCode를 활용하여, 실행 결과를 눈으로 보시면서 정리해 주세요!

# 📸 잠깐 ! 스터디 인증샷은 찍으셨나요?📸

---

* 스터디리더께서 대표로 매 주차마다 한 장 남겨주시면 좋겠습니다!🙆💗
 (사진을 저장해서 이미지 임베드를 하셔도 좋고, 복사+붙여넣기해서 넣어주셔도 좋습니다!)

[]()

# 🍠  React Vite 초기 세팅 방법

---

<aside>
💡

아래 키워드를 진행하시기 전에, 꼭 초기 세팅을 진행하고 해주세요!

</aside>

[React Vite 초기 세팅 (1)](https://www.notion.so/React-Vite-1-a136377f6b254c5cbd4cf2bbc3a60106?pvs=21)

# 🎯 핵심 키워드

---

<aside>
💡 주요 내용들에 대해 조사해보고, 자신만의 생각을 통해 정리해보세요!
레퍼런스를 참고하여 정의, 속성, 장단점 등을 적어주셔도 됩니다.
조사는 공식 홈페이지 **Best**, 블로그(최신 날짜) **Not Bad

추가로, 위에서 초기 세팅 한 App.jsx 파일을 바탕으로 핵심 키워드를 정리해 볼 예정입니다.
초기 세팅 먼저하고 진행해주세요!**

</aside>

- React의 동작 원리
    
    ### React의 동작 원리
    
    React는 User Interface Library이다. 리액트의 핵심적인 특징은 아래와 같다.
    
    <aside>
    💡
    
    각 특징들이 무엇인지, 어떠한 이점이 있는지 정리해주세요
    
    - UMC 웹 파트장 매튜 / 김용민 - 
    
    </aside>
    
    1. SPA (Single Page Application)
    - 정리
        
        SPA는 하나의 HTML 페이지를 로드한 후, 사용자 상호작용에 따라 동적으로 필요한 컴포넌트만 업데이트하는 웹 애플리케이션입니다.
        
        장점
        
        - **빠른 로딩 속도**: 초기 로딩 이후, 페이지 전환이 빠르게 이루어져 사용자에게 더 나은 경험을 제공합니다.
        - **효율적인 리소스 사용**: 전체 페이지를 다시 로드할 필요가 없기 때문에 네트워크 대역폭과 서버 리소스를 절약할 수 있습니다.
        
        단점
        
        - **SEO 문제**: SPA는 서버 측 렌더링(SSR)보다 SEO(Search Engine Optimization) 최적화에 어려움이 있을 수 있습니다. 검색 엔진 크롤러가 JavaScript를 제대로 처리하지 못할 수 있기 때문입니다. 이를 해결하기 위해서는 SSR이나 프리렌더링을 고려할 수 있습니다.
        - **초기 로딩 시간**: 초기 로딩 시 많은 JavaScript 파일을 다운로드해야 하므로, 첫 페이지 로드 시간이 길어질 수 있습니다.
        - **복잡성**: SPA는 상태 관리, 라우팅, API 호출 등 다양한 기술을 다루어야 하므로, 프로젝트가 복잡해질 수 있습니다.
        
        **SEO: 검색 엔진 최적화를 의미합니다.
        
        **검색 엔진 크롤러: 웹을 자동으로 탐색하고 색인화하는 프로그램
        
    1. User Interface Library 
    - 정리
        
        User Interface (UI) Library는 사용자 인터페이스를 구축하기 위한 재사용 가능한 컴포넌트 모음입니다.
        
        **정의**
        
        - 미리 디자인되고 구축된 UI 요소들의 집합
        - 버튼, 폼, 메뉴, 아이콘 등 다양한 컴포넌트 포함
        - 애플리케이션 개발을 위한 일관된 디자인 시스템 제공
        
        **주요 기능**
        
        1. 재사용 가능한 컴포넌트 제공
        2. 일관된 디자인 및 사용자 경험 보장
        3. 개발 시간 단축
        4. 코드 중복 감소
        
        **장점**
        
        - 빠른 개발 속도
        - 디자인 일관성 유지
        - 협업 효율성 향상
        - 테스트 및 최적화된 컴포넌트 사용
    1. Functional Component (함수형 컴포넌트)
    - 정리
        
        Functional component(함수형 컴포넌트)는 React 엘리먼트를 반환하는 JavaScript함수입니다. 이 함수는 props라는 객체를 인자로 받아 UI를 렌더링합니다.
        
        **주요 특징:**
        
        - UI에 집중된 방식으로 구현됩니다[2](https://allblack0811.tistory.com/36).
        - 상태를 저장할 수 없으며, 함수 실행 후 메모리에서 사라집니다.
        - 클래스형 컴포넌트에 비해 선언이 간편하고 메모리 사용이 적습니다.
        - Hooks를 사용하여 로직을 state와 분리할 수 있어 재사용성이 높습니다.
        
        **작성 방법**
        
        Functional component는 일반 함수나 화살표 함수로 작성할 수 있습니다. 예를 들어:
        
        ```jsx
        function Welcome(props) {
        	return <h1>Hello, {props.name}</h1>
        }
        ```
        
        또는 화살표 함수를 사용할 수 있습니다.
        
        ```jsx
        const Welcome = (props) => {
        	return <h1>Hello, {props.name}</h1>
        };
        ```
        
    1. Virtual DOM (가상 DOM)
    - 정리
        
        실제 DOM 조작을 최적화하기 위해서 사용합니다.
        
        1. 상태나 속성 값이 변경되면 React는 Virtual DOM을 새로 생성합니다.
        2. 새로운 Virtual DOM을 이전 Virtual DOM과 비교합니다.
        3. 변경된 부분만 실제 DOM에 반영합니다.
        
        *DOM(Document Object Model)은 HTML 문서 구조를 객체로 표현한 것
        
    1. 동시성 렌더링
    - 정리
        
        **렌더링이란 컴포넌트를 화면에 표시하는 과정입니다.
        
        단일 스레드 환경에서 작업의 우선순위를 조절하고 작업을 작은 단위로 나누어 번갈아 수행함으로써 React가 여러 작업을 동시에 처리할 수 있게 해줍니다.
        
        **주요 특징**
        
        1. **중단 가능한 렌더링**: 렌더링 과정을 중단하고 재개할 수 있어, 더 중요한 업데이트가 발생하면 즉시 처리할 수 있습니다.
        2. **우선순위 기반 렌더링**: 작업의 중요도에 따라 우선순위를 부여하여 처리합니다.
        3. **백그라운드 렌더링**: 메인 스레드를 차단하지 않고 백그라운드에서 새로운 화면을 준비할 수 있습니다.
        
        **동시성 렌더링의 이점**
        
        1. **향상된 반응성**: UI가 더 빠르게 반응하여 사용자 경험이 개선됩니다.
        2. **부드러운 애니메이션**: 여러 프레임을 동시에 렌더링하여 애니메이션이 더 매끄럽게 표현됩니다.
        3. **효율적인 리소스 활용**: CPU와 메모리 사용을 최적화합니다.
    

### JSX 문법에 대해 배워보자! 🍠

- JSX 사용시 유의 사항 (기초)
    
    ### 1. React에서 JSX를 반환할 때 꼭 하나의 태그만 반환해야한다.
    
    **`⭕️ 가능한 경우`**
    
    ```jsx
    function App() {
      return (
         <strong>상명대학교</strong>
      )
    }
    
    export default App
    ```
    
    **`❌ 불가능한 경우`**
    
    ```jsx
    import './App.css'
    
    function App() {
      return (
         <strong>상명대학교</strong>
         <p>매튜/김용민</p>
      )
    }
    
    export default App
    
    ```
    
    <aside>
    💡
    
    여러 개를 반환하고 싶은 경우는 어떻게 해야 할까요?
    코드와, 이유를 간략하게 작성해주세요.
    
    </aside>
    
    - 답변 🍠
        1. 단일 부모 요소로 감싸기
        
        ```jsx
        // 코드 아래 첨부
        
        function App() {
          return (
        		<div>
        			<strong>상명대학교</strong>
        			<p>매튜/김용</p>
        	  </div>
        
          )
        }
        
        export default App
        ```
        
        1. React Fragment 사용하기
        
        불필요한 HTML요소를 추가하지 않기 위해`<Fragment>` 또는 축약형 `<>...</>`으로 작성할 수 있습니다. 이렇게 하면 DOM에 불필요한 요소를 추가하지 않을 수 있습니다.
        
        ```jsx
        function App() {
          return (
        		<>
        			<strong>상명대학교</strong>
        			<p>매튜/김용</p>
        	  </>
        
          )
        }
        
        export default App
        ```
        
        ```jsx
        function App() {
          return (
        		<React.Fragment>
        			<strong>상명대학교</strong>
        			<p>매튜/김용</p>
        	  </React.Fragment>
        
          )
        }
        
        export default App
        ```
        
        1. 배열로 반환하기
        
        ```jsx
        function App() {
          return [
        		<strong>상명대학교</strong>,
        		<p>매튜/김용</p>
          ]
        }
        
        export default App
        ```
        
        <aside>
        💡
        
        이유: 
        
        1. **가상 DOM 구조 유지**: React는 가상 DOM 트리 구조를 관리하며 이 구조가 한 개의 루트 요소로 구성되어야 전체 컴포넌트 트리를 효율적으로 업데이트하고 렌더링할 수 있습니다.
        2. **일관성**: 여러 요소가 단일 부모 요소로 감싸져 있어야 트리 구조가 일관성 있게 유지되며, 이후 작업에서 예측 가능하고 안정적인 트리 구조를 보장합니다.
        
        따라서 여러 JSX 요소를 반환할 때는 항상 하나의 부모 요소로 감싸야 합니다.
        
        </aside>
        
    - 해설
        
        ```jsx
        function App() {
          return (
             <>
              <strong>상명대학교</strong>
              <p>매튜/김용민</p>
             </>
          )
        }
        
        export default App
        ```
        
        많은 분들이 `<> 빈 태그(Fragment)`를 활용할 수 있다는 부분을 모르실 것 같습니다. 스타일링을 하거나, 부모태그가 필요한 경우가 아닌, 다수의 태그를 반환하고 싶은 경우는 `<> 빈 태그를 활용`해도 좋습니다.
        
    
    또한 React에서는 HTML에서 사용하신 다양한 태그를 사용할 수 있습니다~!!
    
    ### 2. React에서 스타일링 방법
    
    1. className을 활용한 스타일링
    
    ```jsx
    import './App.css'
    
    function App() {
      return (
         <>
          <strong className='school'>상명대학교</strong>
          <p>매튜/김용민</p>
         </>
      )
    }
    
    export default App
    
    ```
    
    이런식으로, `className`을 지정해주겠습니다. App.jsx 코드 상단을 보면 ‘./App.css’를 import하여 사용하고 있습니다.
    
    `App.css` 파일로 가서 아래와 같이 코드를 입력해주겠습니다.
    
    ```jsx
    .school {
      background-color: blue;
      color: white;
      font-size: 10rem;
    }
    ```
    
    ![스크린샷 2024-09-09 오후 4.58.48.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/2d957261-4c70-4d89-bf9c-549fbfc1aca7/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_4.58.48.png)
    
    1. Inline-Styling을 활용한 스타일링
    
    ```jsx
    import './App.css'
    
    function App() {
      return (
         <>
          <strong className='school'>상명대학교</strong>
          <p style={{color: 'purple', fontWeight:'bold', fontSize:'3rem'}}>매튜/김용민</p>
         </>
      )
    }
    
    export default App
    ```
    
    위와 같이, **`style`** 이후 중괄호를 두번 연 후, 카멜 표기법을 사용하여, css 코드를 작성할 수 있습니다.
    
    중괄호를 두개 쓰는 이유는, 아래와 같습니다.
    
    1. 바깥쪽 중괄호는 자바스크립트 문법임을 나타낸다.
    2. 안쪽 중괄호는 자바스크립트의 객체임을 나타낸다.
    
    **`HTML 방식과 유사하지만 살짝 다르므로, 주의해주세요!!`**
    
    ```jsx
    // HTML 방식 (케밥 표기법)
    <div style="background-color: purple">
    	고구마
    </div>
    
    // JSX 방식 (카멜 표기법)
    <div style={{backgroundColor: 'purple'}}>
    	고구마
    </div>
    ```
    
    ### 3. local variable (로컬 변수) 선언
    
    ```jsx
    import './App.css'
    
    function App() {
      return (
         <>
          <strong className='school'>상명대학교</strong>
          <p style={{color: 'purple', fontWeight:'bold', fontSize:'3rem'}}>매튜/김용민</p>
         </>
      )
    }
    
    export default App
    ```
    
    여기서, 이제 매튜라는 이름을, `nickname` 이라는 변수를 할당 받아서, 사용해보고자 합니다.
    
    ```jsx
    import './App.css'
    
    function App() {
      const nickname = '매튜'
      return (
         <>
          <strong className='school'>상명대학교</strong>
          <p style={{color: 'purple', fontWeight:'bold', fontSize:'3rem'}}>매튜/김용민</p>
         </>
      )
    }
    
    export default App
    
    ```
    
    매튜/김용민 → 이 부분을 **`nickname/김용민`** 이렇게 쓴다면 당연히, 문자열로 인식 할 것 입니다.
    
    `nickname`이라는 변수에 접근해서, `nickname`의 변수가 갖고 있는 매튜라는 닉네임에 접근하고 싶기에 이러한 경우에는 **`중괄호{}`** 를 사용하면 됩니다.
    
    ```jsx
    import './App.css'
    
    function App() {
      const nickname = '매튜'
      return (
         <>
          <strong className='school'>상명대학교</strong>
          <p style={{color: 'purple', fontWeight:'bold', fontSize:'3rem'}}>
    	      {nickname}/김용민
    	     </p>
         </>
      )
    }
    
    export default App
    
    ```
    
    제대로 동작함을 확인할 수 있고, `nickname` 안의 값도 자유롭게 변경하면, 그에 맞춰서 `nickname`이 변경됨을 확인할 수 있습니다.
    
- JSX 사용시 유의 사항 (심화)
    
    ### 1. 문자열과 함께 변수 사용하기
    
    `중괄호{}`와 ```를 활용`하여, 문자열과 함께 변수를 사용할 수 있습니다.
    
    자주 사용하는 패턴이니 꼭 익숙해지시길 바랍니다!
    
    ```jsx
    import './App.css'
    
    function App() {
      const nickname = '매튜'
      const sweetPotato = '고구마'
      return (
         <>
          <strong className='school'>상명대학교</strong>
          <p style={{color: 'purple', fontWeight:'bold', fontSize:'3rem'}}>{nickname}/김용민</p>
          <h1>{`${nickname}는 ${sweetPotato} 아이스크림을 좋아합니다.`}</h1>
         </>
      )
    }
    
    export default App
    
    ```
    
    ![스크린샷 2024-09-09 오후 5.16.19.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/da56da7b-3210-4644-b4fd-4872afd15bad/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.16.19.png)
    
    ### 2. 배열의 요소를 나타내는 방법.
    
    array안의 요소를 각각 나타내고 싶은 경우는 **`map`**을 활용합니다.
    
    map에 대해 잘 모르는 분들은, JS 관련 워크북을 다시 한번 보시거나, 구글링 하여 공부 후 진행해주세요.
    
    ```jsx
    import './App.css'
    
    function App() {
      const nickname = '매튜'
      const sweetPotato = '고구마'
      const array = ['REACT', 'NEXT', 'VUE', 'SVELTE', 'ANGULAR', 'REACT-NATIVE']
      return (
         <>
          <strong className='school'>상명대학교</strong>
          <p style={{color: 'purple', fontWeight:'bold', fontSize:'3rem'}}>{nickname}/김용민</p>
          <h1>{`${nickname}는 ${sweetPotato} 아이스크림을 좋아합니다.`}</h1>
          <ul>
            {array.map((yaho, idx) => {
              return <li key={idx}>{yaho}</li>
            })}
          </ul>
         </>
      )
    }
    
    export default App
    
    ```
    
    map은 yaho를 인자로 받아서, 값을 반환합니다. **`중괄호를 사용한 경우에는 꼭 return을 적어주어야`** 반환하는 값이 제대로 보입니다. 많은 분들이, 이 부분에서 어려움을 많이 겪기에, 혹시라도 본인이 작업한 내용이 잘 보이지 않는다면 중괄호인지, 소괄호인지를 먼저 찾아보세요!
    
    ```jsx
          <ul>
            {array.map((yaho, idx) => {
              return <li key={idx}>{yaho}</li>
            })}
          </ul>
    ```
    
    소괄호를 활용한 경우에는 return을 생략할 수 있습니다.
    
    ```jsx
          <ul>
            {array.map((yaho, idx) => (
               <li key={idx}>{yaho}</li>
            ))}
          </ul>
    ```
    
    map을 활용하는 경우에는, `key`라는 `props를 설정`해야 함. key값은 각 원소들마다 가지고 있는 **`고유값`**으로 설정을 해야 합니다.
    
    현재는 map 함수에서, 제공해주는 index를 활용해주었지만, 실제로 인덱스를 활용한 경우, 값이 삭제되는 기타 동작의 경우, 문제가 발생하기 떄문에 보통 서버에서 제공해주는 고유한 id 값을 사용하기는 합니다.
    
    `yaho`와, `idx`와 같은 경우는 정해진 이름은 없습니다. 본인이 원하는 이름을 사용해서 반환해주어도 좋습니다.
    
    ```jsx
    // 보통은 복수와 단수를 잘 활용하는게 좋습니다.
    const numbers = [1, 2, 3, 4, 5];
    
    // 단수를 인자로.
    numbers.map((number, index) => return { // 작업들 } ));
    ```
    
    ![스크린샷 2024-09-09 오후 5.27.56.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/7a3741ba-5f49-4af9-95a1-0c773825accf/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.27.56.png)
    
- 첫 컴포넌트 만들어보기
    
    ### 첫 컴포넌트 만들어보기
    
    React에서는 컴포넌트를 통해 UI를 재사용 가능한 개별적인 여러 조각으로 나누고, 각 조각을 개별적으로 관리할 수 있습니다.
    
    위에서 순서대로 진행했더라면, 현재 우리의 코드는 아래와 같습니다.
    
    ```jsx
    import './App.css'
    
    function App() {
      const nickname = '매튜'
      const sweetPotato = '고구마'
      const array = ['REACT', 'NEXT', 'VUE', 'SVELTE', 'ANGULAR', 'REACT-NATIVE']
      return (
         <>
          <strong className='school'>상명대학교</strong>
          <p style={{color: 'purple', fontWeight:'bold', fontSize:'3rem'}}>{nickname}/김용민</p>
          <h1>{`${nickname}는 ${sweetPotato} 아이스크림을 좋아합니다.`}</h1>
          <ul>
            {array.map((yaho, idx) => (
               <li key={idx}>{yaho}</li>
            ))}
          </ul>
         </>
      )
    }
    
    export default App
    ```
    
    실제로, yaho를 반환하는 부분을 **`List 컴포넌트`**로 만들어 보겠습니다.
    
    ```jsx
    <li key={idx}>{yaho}</li>
    ```
    
    **`src 폴더 내부`**에 **`components`** 폴더를 하나 만들어주겠습니다. 그 후 **`List.jsx 파일`**을 만들어보겠습니다.
    
    ![스크린샷 2024-09-09 오후 5.35.51.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/d9a6330d-3f0b-43c1-b1b1-d39ad37f85c6/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.35.51.png)
    
    우리가 궁극적으로 만들고 싶은 내용은 아래와 같습니다.
    
    ![스크린샷 2024-09-09 오후 5.37.05.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/e20d1131-591b-4581-802f-03a75ebb4fa2/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.37.05.png)
    
    기존에 작업하던, App.jsx로 가서
    
    ```jsx
    import './App.css'
    // 1. List Component를 Import 해줍니다.
    import List from './components/List';
    
    function App() {
      const nickname = '매튜'
      const sweetPotato = '고구마'
      const array = ['REACT', 'NEXT', 'VUE', 'SVELTE', 'ANGULAR', 'REACT-NATIVE']
      return (
         <>
          <strong className='school'>상명대학교</strong>
          <p style={{color: 'purple', fontWeight:'bold', fontSize:'3rem'}}>{nickname}/김용민</p>
          <h1>{`${nickname}는 ${sweetPotato} 아이스크림을 좋아합니다.`}</h1>
          <ul>
            {array.map((yaho, idx) => (
              // 2.  <li key={idx}>{yaho}입니다.</li> -> List 컴포넌트를 호출합니다.
              <List />
            ))}
          </ul>
         </>
      )
    }
    
    export default App
    
    ```
    
    각각의 **`컴포넌트는 props`**를 활용하여 데이터를 전달 받을 수 있습니다.
    
    저희는, 일단 map 방식은 키를 전달해주어야 하기 때문에 List 컴포넌트에 key를 전달해 줄 것 입니다.
    
    ```jsx
    <List key={idx} />
    ```
    
    추가적으로, 각 List에 화면에 보여줄 데이터를 전달해주기 위해 특정 이름으로 데이터를 전달해 줄 것입니다.
    
    기술 스택을 전달해주므로, **`문맥상 맞게 tech라는 props의 이름`**으로 전달해주겠습니다.
    
    ```jsx
    <List key={idx} tech={yaho} />
    ```
    
    이렇게 하고 화면을 실행시켜 봅시다.
    
    ![스크린샷 2024-09-09 오후 5.41.47.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/7bd5e857-40f6-401f-b9fa-178e46ce149e/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.41.47.png)
    
    당연히 현재 List 컴포넌트는 아래와 같기에 아무것도 반환되지 않습니다.
    
    ```jsx
    const List = () => {
      return (
        <>
          
        </>
      )
    }
    
    export default List
    
    ```
    
    전달받은 props를 활용해보고자 합니다.
    
    ```jsx
    const List = (props) => {
       console.log(props)
      return (
        <>
          
        </>
      )
    }
    
    export default List
    
    ```
    
    앞으로 프론트엔드 개발을 진행하시면서, **`console.log()`**를 통하여, 자주 본인이 하는 것들을 확인하는 습관이 매우 중요합니다. props의 내용이 무엇이 들었는지 **`Chrome → F12`** 개발자도구를 통해 만든 웹사이트에서 확인해보겠습니다.
    
    ![스크린샷 2024-09-09 오후 5.43.17.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/99ecfc9e-0a76-462f-8174-a3fd8a0a6a41/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.43.17.png)
    
    우리가 아까 **`<List key={idx} tech={yaho} />`** 이런 식으로 값을 전달해주었기에 props를 호출 했을 때 tech라는 이름에 요소 하나하나의 값이 들어가 있음을 확인할 수 있습니다.
    
    여기서 주의하셔야 합니다.
    
    실제로 우리가 props를 호출 했을 때 { tech: ‘REACT’ } 라는 결과값이 나왔습니다.
    
    그럼 우리가 해당 값을 활용할 떄는 {tech}를 활용하는 것이 아닌, **`{props.tech}`**를 통해 값에 접근해야 합니다. **`(해당 내용이 이해가 안가면, 자바스크립트 워크북 객체에 대해 공부하셔야 합니다.)`**
    
    ```jsx
    // props를 호출했을 때 
    const List = (props) => {
       console.log(props)
      return (
        <li>
          {props.tech}
        </li>
      )
    }
    
    export default List
    
    ```
    
    ![스크린샷 2024-09-09 오후 5.46.22.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/765780fd-dd7d-483a-a8c4-cba2f856fae9/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.46.22.png)
    
    여기서 현재는 [props.tech](http://props.tech) 하나밖에 없기에 불편함을 크게 못느끼기겠지만, 전달받은 props가 tech 이외에, name, food 등 여러가지라면 매번 props.tech, props.name, [props.food](http://props.food) 이런식으로 값을 활용하는 것은 매우 귀찮을 것 입니다.
    
    우리는 이것을 해결하기 위해 **`JS 구조분해 할당에 대해 이전에 학습`**했습니다. 어떤 식으로 활용하면 좋을지 본인이 직접 해보고 아래에 **`List.jsx`** 파일을 넣어주세요.
    
    - 구조분해 할당 활용 **`List.jsx`**
        
        ```jsx
        const List = ({tech, food, yaho}) => {
            return (
                <li>
                    {tech}
                </li>
            )
        }
        
        export default List;
        ```
        
    - 해설
        
        첫번째 방식
        
        ```jsx
        // 직접 props를 받는 부분에서 구조 분해 할당을 진행하는 방법.
        const List = ({tech, food, yaho}) => {
          return (
            <li>
              {tech}
            </li>
          )
        }
        
        export default List
        
        ```
        
        두번쨰 방식
        
        ```jsx
        // props를 전달 받고, 그 이후에 구조 분해 할당을 하는 방법.
        const List = (props) => {
          const { tech, food, yaho } = props;
          return (
            <li>
              {tech}
            </li>
          )
        }
        
        export default List
        
        ```
        
    
    이제 각 컴포넌트에 해당하는 스타일링을 진행하면 좋습니다. 스타일링은 크게 많이 하지 않을 것이고, 거슬리는 부분만 제거해보고자 합니다.
    
    일단은 **`<ul>`**일때 자동으로 부여해주는 **`﹒`**이 좀 거슬리므로, 해당하는 것들을 삭제해보겠습니다.
    
    ```jsx
    const List = (props) => {
      const { tech } = props;
      return (
    	  // listStyle을 통해 제거할 수 있습니다.
        <li style={{listStyle: 'none'}}>
          {tech}
        </li>
      )
    }
    
    export default List
    
    ```
    
    이런식으로, 컴포넌트를 분리하여, 스타일링이 가능하다. 구조 분해 할당을 통해 조금 더 깔끔하게 코드를 작성할 수 있다를 알아주시면 됩니다!
    

### 나의 첫 번째 react-hook 🍠

<aside>
💡

리액트 함수 컴포넌트에서 가장 중요한 개념은 훅입니다.

함수형 컴포넌트 이전에 클래스 컴포넌트에서 가능했던, state, ref와 같은 리액트의 핵심 기능들을 함수에서도 간결하게 사용 가능하게 만들었습니다.

우선, 다양한 Hook 중 **`useState`**에 대해서 배워보고자 합니다.

</aside>

- **`useState` 기초**
    
    ### useState 기초
    
    `useState`는 함수형 컴포넌트 안에서 상태를 정의하고, 이 상태를 관리할 수 있게 하는 훅입니다.
    
    기본적인 사용법은 아래와 같습니다.
    
    ```jsx
    import { useState } from 'react';
    
    const [state, setState] = useState('초기값');
    ```
    
    `useState`의 반환 값은 배열입니다. 배열의 첫 번쨰 원소로 state를 사용할 수 있습니다. 그냥 `state`를 사용하게 된다면, 당연히 `useState`의 괄호안에 정의한 초기값이 나오게 됩니다.
    
    두번째 `setState`를 활용한다면, `state의 값을 변경`할 수 있습니다.
    
    ### useState 실습 진행
    
    글로만 보면 잘 이해가 되지 않을 것 입니다. 간단한 카운터를 만들어보며 실습을 진행해보겠습니다.
    
    App.jsx에 아래와 같이 내용을 수정해봅시다.
    
    ```jsx
    import './App.css'
    import { useState } from 'react';
    
    function App() {
      const [count, setCount] = useState(0)
      return (
         <>
          <h1>{count}</h1>
         </>
      )
    }
    
    export default App
    
    ```
    
    우리가 **`useState`**의 초기값을 0이라고 했기에, 당연히 현재 웹을 실행시켜보면, 0이 화면에 출력됩니다.
    
    그럼 해당 숫자를 어떠한 방식으로 증가 시킬까요?
    
    `react`에서는, `JS`의 `onclick`과 같은, 기능을 제공해줍니다.
    
    ```jsx
    import './App.css'
    import { useState } from 'react';
    
    function App() {
      const [count, setCount] = useState(0)
      return (
         <>
          <h1>{count}</h1>
          <button onClick={() => {}}>숫자 증가</button>
         </>
      )
    }
    
    export default App
    
    ```
    
    **`onClick`**을 활용하여, 클릭할 때 추가적인 행동을 정의 할 수 있다. 우리가 값(상태)을 변화하고 싶을 때는 `useState` 배열의 두 번쨰 인자를 사용한다고 했다.
    
    ```jsx
    import './App.css'
    import { useState } from 'react';
    
    function App() {
      const [count, setCount] = useState(0)
      return (
         <>
          <h1>{count}</h1>
          <button onClick={() => setCount(count + 1)}>숫자 증가</button>
         </>
      )
    }
    
    export default App
    
    ```
    
    ![스크린샷 2024-09-09 오후 6.24.59.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/5862b26a-8b90-4d41-86de-dc6801be00e9/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_6.24.59.png)
    
    이러한 식으로, `setState`를 활용하여 값을 증가 시켜줄 수 있다.
    
- **`useState`** 심화
    
    ### useState 심화
    
    일단, 이전에 기초에서 만든 코드를 살짝 수정해보겠습니다. **`handleIncreaseNumber`**라는 함수를 만들어, **`onClick`**에 인자로 전달해주고자 합니다.
    
    ```jsx
    import './App.css'
    import { useState } from 'react';
    
    function App() {
      const [count, setCount] = useState(0)
      const handleIncreaseNumber = () => {
        setCount(count + 1)
      }
      return (
         <>
          <h1>{count}</h1>
          <button onClick={handleIncreaseNumber}>숫자 증가</button>
         </>
      )
    }
    
    export default App
    ```
    
    동일하게 동작함을 확인 할 수 있을 것 입니다!! 간단한 작업인 경우, 이전과 같이 작성해도 크게 문제 없으나, 뭔가 복잡한 작업이 많은 경우에는 이러한 식으로, 따로 함수를 만들어 관리하면 다른 사람이 **`해당 코드를 읽기에 숫자를 증가하는 기능`**이구나 하고 이해하기 쉬울 것 입니다.
    
    아래 코드의 동작을 예측해봅시다. 버튼을 누를 때 마다, 몇 씩 증가하게 될 까요?
    
    ```jsx
    import './App.css'
    import { useState } from 'react';
    
    function App() {
      const [count, setCount] = useState(0)
      const handleIncreaseNumber = () => {
        setCount(count + 1);
        setCount(count + 1);
        setCount(count + 1);
        setCount(count + 1);
        setCount(count + 1);
        setCount(count + 1);
      }
      return (
         <>
          <h1>{count}</h1>
          <button onClick={handleIncreaseNumber}>숫자 증가</button>
         </>
      )
    }
    
    export default App
    
    ```
    
    **`setCount`**를 6번 호출 했기에, 6씩 증가할 것 같으나, 실제로는 1씩 증가합니다 .이는 자바스크립트의 **`클로저`**와 깊은 연관이 있습니다. 
    
    https://developer.mozilla.org/ko/docs/Web/JavaScript/Closures
    
    ![스크린샷 2024-09-09 오후 6.35.30.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/2bb27390-3b77-4ae1-9781-7713b9189b88/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_6.35.30.png)
    
    먼저 왜 그런지 설명하기에 앞서서 **`Lexical Environment`**에 대해서 설명하고자 합니다.
    
    **`Lexical Environment`**란 함수가 실행될 때, 그 함수 안에서 참조할 수 있는 **변수나 상태 값의 저장소**라고 생각하면 됩니다. 이 환경은 함수가 호출될 때마다 새로운 환경이 생성되는 것이 아니라, 함수가 선언될 당시의 변수를 기억하고 있습니다. (즉, count = 0)
    
    React는 상태를 즉시 업데이트하지 않고, 함수를 실행할 당시의 상태를 기억해 두는 **`렉시컬 환경(Lexical Environment)`**이라는 것을 사용합니다. 그래서, `handleIncreaseNumber` 함수가 실행될 때마다 함수가 실행된 시점의 상태(여기서는 `count = 0`)를 기준으로 값을 계산하게 됩니다.
    
    쉽게 말해, **`handleIncreaseNumber` 함수 안에서 `count`는 0으로 고정된 것처럼 작동**하는 거죠.
    
    ```jsx
    setCount(count + 1); -> 0 + 1
    setCount(count + 1); -> 0 + 1
    setCount(count + 1); -> 0 + 1
    setCount(count + 1); -> 0 + 1
    setCount(count + 1); -> 0 + 1
    setCount(count + 1); -> 0 + 1
    
    // 최종 결과: 1
    ```
    
    우리가 원하는 것은 버튼 클릭 하나에 6씩 증가하는 동작을 원합니다. 
    
    `setState`의 업데이트를 하는 두번째 방식을 활용하면, 지금 문제점을 해결할 수 있습니다!
    
    ```jsx
    // setState는 두가지 방식으로 활용할 수 있다.
    
    // 1. 한번에 값을 업데이트 (batch 방식)
    setCount(count + 1);
    
    // 2. 이전 상태 값을 인자로 전달하여 업데이트 (prev라는 이름은 자유롭게 변경 가능);
    setCount(prev => prev + 1);
    ```
    
    아래와 같이 활용하면 됩니다.
    
    ```jsx
    import './App.css'
    import { useState } from 'react';
    
    function App() {
      const [count, setCount] = useState(0)
      const handleIncreaseNumber = () => {
        setCount(prev => prev + 1);
        setCount(prev => prev + 1);
        setCount(prev => prev + 1);
        setCount(prev => prev + 1);
        setCount(prev => prev + 1);
        setCount(prev => prev + 1);
      }
      return (
         <>
          <h1>{count}</h1>
          <button onClick={handleIncreaseNumber}>숫자 증가</button>
         </>
      )
    }
    
    export default App
    
    ```
    
    정상적으로 6씩 증가함을 확인하시면 됩니다.
    
- **`useState`** 객체 상태 업데이트
    
    ### useState로 객체 상태 변화하기
    
    **`useState`**는 위에서 실습해본 숫자가 아닌, 객체 또한 변화 시킬 수 있습니다.
    
    이 때 사용되는 개념이 얕은 복사, 깊은 복사 개념과 이전에 자바스크립트 워크북에서 배운 전개 연산자를 활용하면 매우 유용하게 값을 업데이트 할 수 있습니다.
    
    객체는 숫자와 다르게 **참조 타입**이기 때문에, 객체 상태를 업데이트할 때 **얕은 복사**와 **깊은 복사** 개념을 잘 이해하는 것이 중요합니다.
    
    ### 1. 얕은 복사
    
    얕은 복사는 **한 단계만 복사**하는 방식입니다. 
    
    복사된 객체는 원래 객체와 같은 참조를 가지기 때문에, **내부에 중첩된 객체가 변경되면 원본 객체에도 영향을 미칠 수 있습니다.**
    
    ```jsx
    const [person, setPerson] = useState({
      name: "김용민",
      age: 26,
      nickname: "매튜"
    });
    
    const newPerson = {...person}; // 얕은 복사
    newPerson.nickname = "야호";
    
    console.log(person.nickname); // 여전히 "매튜" 임을 확인할 수 있다.
    ```
    
    ### 2. 깊은 복사
    
    깊은 복사는 객체 내부의 중첩된 모든 값까지 **완전히 새로운 복사본**을 만드는 방식입니다. 이 경우, 복사본을 수정해도 **원본 객체에는 전혀 영향이 없습니다.**
    
    깊은 복사는 **재귀적으로** 객체의 모든 속성을 복사해야 하므로, 직접 구현하거나 `lodash`와 같은 라이브러리의 `cloneDeep`을 활용하거나, **`JSON 방식을 이용`**해서 **`깊은 복사`**를 진행합니다.
    
    ```jsx
    const newPersonDeep = JSON.parse(JSON.stringify(person)); // 깊은 복사
    ```
    
    객체가 단순한 경우 이 방법을 사용할 수 있지만, 함수나 `undefined` 값이 있을 때는 적합하지 않습니다.
    
    ### 실습. useState를 활용하여 객체를 업데이트하기
    
    ```jsx
    import { useState } from 'react';
    
    function App() {
      // 초기 상태로 '김용민', 26, '매튜'를 가진 person 객체를 초기값으로 생성합니다.
      const [person, setPerson] = useState({
        name: "김용민",
        age: 26,
        nickname: "매튜"
      });
    
      // city 값을 새로 추가하여 업데이트하는 함수
      const updateCity = () => {
        setPerson(prevPerson => ({
          ...prevPerson,   // 이전 person 객체의 복사본 생성
          city: "서울"      // 새로 city 값을 추가하거나 업데이트
        }));
      };
    
      // age 값을 1씩 증가시키는 함수
      const increaseAge = () => {
        setPerson(prevPerson => ({
          ...prevPerson,   // 이전 person 객체의 복사본을 생성합니다.
          age: prevPerson.age + 1  // 다른 key의 value는 유지, age 값을 기존 값에서 1 증가
        }));
      };
    
      return (
        <>
          <h1>이름: {person.name}</h1>
          <h2>나이: {person.age}</h2>
          <h3>닉네임: {person.nickname}</h3>
          {person.city && <h4>도시: {person.city}</h4>}
          <button onClick={updateCity}>도시 추가</button>
          <button onClick={increaseAge}>나이 증가</button>
        </>
      );
    }
    
    export default App;
    
    ```
    
    ![스크린샷 2024-09-09 오후 7.03.11.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/510e5b89-e5c0-4da9-baa6-01ad4d4ca7ab/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-09_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_7.03.11.png)
    
    버튼을 눌렀을 때, 객체의 상태를 안전하게 업데이트 할 수 있습니다. **`전개 연산자를 활용`**하여, **`기존 상태를 복사`**하면서, 일부 속성만 업데이트 할 수 있기에 **`불변성을 유지`**하며 상태를 관리할 수 있습니다.
    

# 🔥 실습 - ToDoList 만들며 useState 익히기 🍠

<aside>
💡

이번 실습은 위에서 학습한 jsx 문법과 **`useState`**를 활용하여 TodoList를 만들어보고자 합니다.

개발 하면서 필수라고 말할 수 있는

1. 추가
2. 수정
3. 삭제

3 가지 요소를 배워보고자 합니다.

스스로 만들어 보는 것이 매우 좋으나, WEB 파트 같은 경우, 아직 HTML, CSS, JS에 익숙하지 않은 사람이 매우 많기에, 여러 번 되돌려서 볼 수 있도록 강의 형태로 제공해 드리는 점 참고 바랍니다.

처음부터 막히고, 매우 어려운 것이 당연하며, 좌절하지 마시고, 여러 번 만들어 보시면 금방 이해하실 수 있습니다!

최대한 자세하게 설명을 드리려고, 강의 영상 자체가 조금 깁니다.

너무 강의 영상에 의존하지 말고, 혼자 구글링을 하시며, 만들어 보고자 노력하시면 좋겠습니다!

**- UMC 7th 중앙 WEB 파트장 매튜/김용민 -**

</aside>

https://www.youtube.com/watch?v=8pm6o5dXtw0&t=3182s

https://www.youtube.com/watch?v=8pm6o5dXtw0&t=1032s

수정하기 부분에서 자바스크립트의 얕은 복사, 깊은 복사에 대해 많이 헷갈리시는 분이 있을 것 이라고 생각합니다. 이에 대해 한번 정리해주시면 좋을 것 같습니다!

- 얕은 복사 🍠
    
    얕은 복사는 변수가 저장된 메모리 주소를 복사한다. 따라서 변수가 변경되면 복사한 값, 복사된 값 모두 변경된다.
    
- 깊은 복사 🍠
    
    새로운 메모리 주소를 할당하여 변수 내에 있는 값을 복사한다. 