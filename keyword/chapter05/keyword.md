# 📝 학습 목표

---

1. **`유효성 검사`**에 대해 학습합니다.
2. **`input 태그`**의 여러가지 속성에 대해 학습합니다.
3. **`Custom Hook`**을 만들었을 떄의 장점에 대해 알아봅니다.
4. **`Custom Hook`**을 활용하여, 효율적으로, 유효성 검사를 하며, 폼 데이터를 관리하는 방법에 대해 알아봅니다.

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

# 🎯 핵심 키워드

---

<aside>
💡 주요 내용들에 대해 조사해보고, 자신만의 생각을 통해 정리해보세요!
레퍼런스를 참고하여 정의, 속성, 장단점 등을 적어주셔도 됩니다.
조사는 공식 홈페이지 **Best**, 블로그(최신 날짜) **Not Bad**

</aside>

### 키워드 정리 🍠

- useRef 🍠
    
    `useRef`는 React에서 DOM 요소나 컴포넌트의 특정 값을 참조하고자 할 때 사용하는 훅입니다. `useRef`는 크게 두 가지 경우에 유용하게 쓰입니다.
    
    1. **DOM 요소에 접근하기 위해**: `useRef`는 직접적으로 DOM 요소에 접근하고 조작하고자 할 때 사용됩니다. 예를 들어, 특정 버튼이나 입력 필드에 포커스를 설정할 때 `useRef`를 통해 DOM 요소에 접근하여 작업할 수 있습니다.
        
        ```jsx
        javascript
        코드 복사
        import { useRef } from 'react';
        
        function TextInputWithFocusButton() {
          const inputRef = useRef(null);
        
          const handleFocus = () => {
            inputRef.current.focus();
          };
        
          return (
            <div>
              <input ref={inputRef} type="text" />
              <button onClick={handleFocus}>Focus the input</button>
            </div>
          );
        }
        
        ```
        
        위 코드에서 `inputRef`는 `<input>` 요소를 가리키고 있으며, 버튼을 클릭할 때 `inputRef.current.focus()`를 호출하여 해당 입력 필드에 포커스를 맞춥니다.
        
    2. **값을 저장하기 위해**: `useRef`는 렌더링 사이에 값이 유지되길 원할 때도 사용됩니다. `useState`와 달리 `useRef`의 값이 바뀌어도 컴포넌트가 다시 렌더링되지 않으며, 렌더링 사이에 값이 그대로 유지됩니다. 예를 들어, 특정 값을 저장하지만 렌더링에 영향을 주지 않도록 할 때 유용합니다.
        
        ```jsx
        javascript
        코드 복사
        import { useRef, useState } from 'react';
        
        function Counter() {
          const countRef = useRef(0);
          const [renderCount, setRenderCount] = useState(0);
        
          const increment = () => {
            countRef.current += 1;
            console.log(`CountRef value: ${countRef.current}`);
            setRenderCount(renderCount + 1);
          };
        
          return (
            <div>
              <p>CountRef: {countRef.current}</p>
              <p>Rendered count: {renderCount}</p>
              <button onClick={increment}>Increment</button>
            </div>
          );
        }
        
        ```
        
        여기서 `countRef.current`는 값이 업데이트되어도 컴포넌트가 재렌더링되지 않지만, `renderCount`를 `useState`로 설정했기 때문에 버튼을 누를 때마다 렌더링이 이루어지며 화면에 값이 반영됩니다.
        
    
    **정리하자면**, `useRef`는 컴포넌트의 재렌더링에 영향을 주지 않으면서 특정 값을 참조하거나 유지할 때 매우 유용하게 쓰이는 훅입니다.
    
- input의 주요 프로퍼티 🍠
    - 아래 내용 이외에, 자주 사용하는 프로퍼티가 있으면 추가로 더 정리해주세요! 🍠
        
        ### `pattern`
        
        - 입력값이 정규 표현식과 일치해야 하는 패턴을 지정합니다.
        - `type="text"`, `type="email"` 등 텍스트 입력 필드에서 유효성 검사를 위해 사용됩니다.
        - 예: `<input type="text" pattern="[A-Za-z]{3,}" />` (3글자 이상의 영문만 허용)
        
        ### `step`
        
        - 숫자 입력 시 `step` 속성을 통해 값의 증분을 설정할 수 있습니다.
        - `type="number"`, `type="range"`와 함께 사용됩니다.
        - 예: `<input type="number" step="0.5" />` (0.5 단위로 증가/감소)
        
        ### `size`
        
        - 입력 필드의 표시 크기를 설정합니다. 이 값은 입력 필드의 실제 폭을 변경하지는 않지만, 표시 크기를 조절하는 데 사용됩니다.
        - 예: `<input type="text" size="30" />`
    
    ### 1. `type`
    
    - **설명**: 입력 필드의 종류를 설정합니다.
    - **값 예시**: `"text"`, `"password"`, `"email"`, `"number"`, `"checkbox"`, `"radio"` 등
    - **예시**: `<input type="text" />`
    
    ### 2. `value`
    
    - **설명**: 입력 필드의 값을 설정하고 제어할 때 사용됩니다. **Controlled Component**에서 자주 사용됩니다.
    - **값 예시**: 문자열 또는 숫자
    - **예시**: `<input type="text" value={value} />`
    
    ### 3. `defaultValue`
    
    - **설명**: 초기값을 설정하는 데 사용됩니다.
    - **값 예시**: 문자열 또는 숫자
    - **예시**: `<input type="text" defaultValue="초기값" />`
    
    ### 4. `onChange`
    
    - **설명**: 사용자가 입력 필드에 값을 입력하거나 변경할 때 호출되는 이벤트 핸들러입니다.
    - **값 예시**: 함수
    - **예시**: `<input type="text" onChange={(e) => setValue(e.target.value)} />`
    
    ### 5. `placeholder`
    
    - **설명**: 입력 필드가 비어 있을 때 표시되는 힌트 텍스트입니다.
    - **값 예시**: 문자열
    - **예시**: `<input type="text" placeholder="여기에 입력하세요" />`
    
    ### 6. `checked`
    
    - **설명**: 체크박스나 라디오 버튼이 선택되었는지 여부를 제어합니다.
    - **값 예시**: `true` 또는 `false`
    - **예시**: `<input type="checkbox" checked={isChecked} />`
    
    ### 7. `defaultChecked`
    
    - **설명**: 체크박스나 라디오 버튼의 초기 상태를 설정합니다.
    - **값 예시**: `true` 또는 `false`
    - **예시**: `<input type="checkbox" defaultChecked />`
    
    ### 8. `disabled`
    
    - **설명**: 입력 필드를 비활성화하여 사용자 입력을 막습니다.
    - **값 예시**: `true` 또는 `false`
    - **예시**: `<input type="text" disabled />`
    
    ### 9. `readOnly`
    
    - **설명**: 입력 필드의 값을 읽기 전용으로 설정합니다. 사용자는 값을 변경할 수 없습니다.
    - **값 예시**: `true` 또는 `false`
    - **예시**: `<input type="text" readOnly />`
    
    ### 10. `name`
    
    - **설명**: 폼 데이터를 제출할 때 서버로 전송되는 데이터의 이름을 지정합니다.
    - **값 예시**: 문자열
    - **예시**: `<input type="text" name="username" />`
    
    ### 11. `maxLength`
    
    - **설명**: 입력할 수 있는 최대 글자 수를 지정합니다.
    - **값 예시**: 숫자
    - **예시**: `<input type="text" maxLength={10} />`
    
    ### 12. `min` / `max`
    
    - **설명**: 숫자 또는 날짜 입력에서 사용할 수 있는 최소/최대 값을 지정합니다.
    - **값 예시**: 숫자 또는 날짜
    - **예시**: `<input type="number" min={1} max={10} />`
    
    ### 13. `autoFocus`
    
    - **설명**: 페이지가 로드될 때 자동으로 입력 필드에 포커스를 줍니다.
    - **값 예시**: `true` 또는 `false`
    - **예시**: `<input type="text" autoFocus />`
    
    ### 14. `required`
    
    - **설명**: 입력 필드를 필수 입력으로 설정합니다. 폼을 제출할 때 이 필드가 비어 있으면 제출이 거부됩니다.
    - **값 예시**: `true` 또는 `false`
    - **예시**: `<input type="text" required />`

### **`Controlled Input`** vs **`UnControlled Input`**

- Controlled Input
    
    ### Controlled Input
    
    **`Controlled Input`**은 React의 상태(state)에 의해 폼의 값을 관리하는 방식입니다. Input의 value가 컴포넌트의 상태에 연결되어 있고, 상태값이 달라질 떄 마다, 입력 필드의 값도 갱신됩니다.
    
    쉽게 말해서, Input의 값은, **`React Component가 제어`**하고, 모든 입력 변화 또한, **`컴포넌트의 상태로 반영`**되어집니다.
    
    특징
    
    - Input의 value는, React의 **`state`**로 관리됩니다.
    - 상태 값이, **`Input의 value 속성에 직접적으로 연결`** 됨.
    - **`Input`**의 **`Value`**가 **`변경`**되면, **`상태가 업데이트`**되고, **`상태가 다시 렌더링을 Trigger`** 함.
    - **`React`**가 **`Form 요소의 현재 값을 항상 알고 있기에 제어가 용이`**.
    
    ```tsx
    import { useState } from 'react';
    
    function ControlledInput() {
      const [inputValue, setInputValue] = useState('');
    
      const handleChange = (event) => {
        setInputValue(event.target.value);
      };
    
      return (
        <div>
          <input type="text" value={inputValue} onChange={handleChange} />
          <p>입력: {inputValue}</p>
        </div>
      );
    }
    
    export default ControlledInput;
    
    ```
    
    ### 장점:
    
    - 상태를 통해 값이 직접적으로 제어되기 때문에 **`폼 데이터를 검증`**하거나 **`조작`**하기가 쉽습니다.
    - **`사용자 입력을 실시간으로 검증`**하거나 **`포맷을 조정`**할 수 있습니다.
    
    ### 단점:
    
    - **`컴포넌트에서 상태 관리가 복잡`**해질 수 있으며, 특히 폼 데이터에 너무 많은 value들을 관리하는 경우 **`성능에 부담`**이 될 수 있습니다.
    
- UnControlled Input
    
    ### UnControlled Input
    
    **`Uncontrolled Input`**은 React의 state가 아닌 DOM 자체에서 입력 값을 관리하는 방식입니다. 폼의 값은 **`React 컴포넌트가 직접 관리하지 않고`**, 필요할 때 DOM에서 직접 값을 참조하는 방법입니다. 이를 위해 `ref`를 사용하여 **`DOM 요소에 직접 접근`**할 수 있습니다.
    
    ### 특징
    
    - 입력값이 `state`에 의존하지 않고, React의 제어 밖에서 관리됩니다.
    - 폼 요소의 값은 사용자가 입력하는 대로 DOM에 저장되며, 필요할 때만 값을 읽어 옵니다.
    - React의 상태를 사용하지 않기 때문에 폼을 간단하게 유지할 수 있습니다.
    
    ```tsx
    import { useRef } from 'react';
    
    function UncontrolledInput() {
      const inputRef = useRef(null);
    
      const handleSubmit = () => {
        console.log(`입력: ${inputRef.current.value}`);
      };
    
      return (
        <div>
          <input type="text" ref={inputRef} />
          <button onClick={handleSubmit}>제출</button>
        </div>
      );
    }
    
    export default UncontrolledInput;
    
    ```
    
    ### 장점
    
    - 상태 관리가 필요 없으므로 간단한 폼에 적합하며, **`성능적으로도 유리`**할 수 있습니다.
    - 작은 폼이나 **`상태가 필요 없는 경우 사용하기 쉽습니다.`**
    
    ### 단점
    
    - 입력 값을 **`실시간으로 검증하거나 조작하기 어려우며`**, 폼 데이터와 관련된 논리를 관리하는 데 제약이 있을 수 있습니다.
    - **`DOM에 직접 접근`**하기 때문에 **`React의 단방향 데이터 흐름을 벗어나는 경우`**가 생길 수 있습니다.
    

### react-hook-form & yup 🍠

**`react-hook-form`**과 **`yup`**은 React에서 폼을 간편하게 관리하고, 유효성 검사를 수행하는 데 유용한 라이브러리 입니다. 두 개의 라이브러리를 함께 사용하면, 폼 입력 관리와 검증 과정을 매우 효율적으로 처리할 수 있습니다.

현재, 여기서는 **`yup`**을 통한, **`validation`**을 설명하지만, 혹시라도, 본인이 작업하시는 프로젝트가 **`TypeScript`**시라면, **`zod`**를 사용하는 것이 조금 더 유리할 수도 있으니, **`zod`**를 더욱 추천드립니다!

- **`react-hook-form`** 공식문서 설명
    
    ### react-hook-form
    
    https://react-hook-form.com/get-started
    
    주요 특징
    
    1. DX (개발자 경험)
        
        직관적이고, 기능이 완벽한 API로, 개발자가 폼을 구축할 떄 매끄러운 경험을 제공합니다.
        
    2. HTML 표준
        
        기존의 HTML 마크업을 활용하여 제약 기반 검증 API로 폼을 검증합니다.
        
    3. 가벼움
        
        패키지 크기는 매우 중요합니다. React Hook Form은 의존성이 없는 작은 라이브러리이다.
        
    4. 성능
        
        리렌더링 횟수를 최소화하고, 검증 계산을 줄이며, 더 빠른 마운팅을 제공.
        
    5. 채택 가능성
        
        폼 상태는 본질적으로 로컬에 있기 떄문에 다른 의존성 없이도 쉽게 채택 가능하다.
        
    6. UX (사용자 경험)
        
        최상의 사용자 경험을 제공하기 위해 일관된 검증 전략을 지향.
        
- **`yup`** 공식문서 설명
    
    ### yup
    
    https://github.com/jquense/yup
    
    **`Yup`**은 런타임 값 파싱 및 검증을 위한 스키마 빌더입니다. 스키마를 정의하고, 값을 변환하여 일치시키거나, 기존 값의 형태를 검증하거나, 두 작업을 모두 수행할 수 있습니다. **`Yup 스키마`**는 매우 표현력이 뛰어나며 복잡하고 상호 의존적인 검증이나 값 변환을 모델링할 수 있습니다.
    
    주요 기능:
    
    1. 간결하면서도 표현력이 뛰어난 스키마 인터페이스로, 간단한 데이터 모델부터 복잡한 데이터 모델까지 설계 가능
    2. 강력한 TypeScript 지원: 스키마에서 정적 타입을 추론하거나, 스키마가 올바르게 타입을 구현하는지 확인
    3. 내장된 비동기 검증 지원: 서버 측 및 클라이언트 측 검증을 동일하게 모델링 가능
    4. 확장성: 타입 안정성이 보장된 메서드와 스키마를 추가할 수 있음
    5. 풍부한 오류 세부 정보 제공으로 디버깅이 쉬움
- **react-hook-form & yup validation 실습 🍠**
    
    ### 실습
    
    아래와 같이 **`라이브러리를 설치`**해줍니다.
    
    ```tsx
    yarn add react-hook-form yup
    ```
    
    그 이후 **`useForm`** hook을 불러옵니다.
    
    ```tsx
    import {useForm} from 'react-hook-form'
    
    const SignUpPage = () => {
        const {register, handleSubmit} = useForm();
    
        const onSubmit = () => {
            console.log('폼 데이터 제출')
        }
    
        return (
            <form onSubmit={handleSubmit(onSubmit)}>
                <input type={'email'}/>
                <input type={'password'}/>
                <input type={'submit'}/>
            </form>
        );
    };
    
    export default SignUpPage;
    
    ```
    
    1. **`register`**를 통해서, 각 **`input`**에 연결해줍니다. 이 떄 **`spread operator`**를 통해서, 원하는 **`name`**과 함께 연결을 해주면 된다고 이해하시면 됩니다.
    2. form 태그 안에는 자체적으로 **`onSubmit`** 내부에 함수를 연결해줄 수 있습니다. 이 떄, **`useForm`** Hook에서 제공해주는 **`handleSubmit`**을 연결해주고, 자체적으로 **`onSubmit`** 함수를 통해서, data를 전달 받아, **`data 호출`**하면 됩니다.
    
    ```tsx
    import {useForm} from 'react-hook-form'
    
    const SignUpPage = () => {
        const {register, handleSubmit} = useForm();
    
        const onSubmit = (data) => {
            console.log('폼 데이터 제출')
            console.log(data);
        }
    
        return (
            <form onSubmit={handleSubmit(onSubmit)}>
                <input type={'email'} {...register("email")}/>
                <input type={'password'} {...register("password")}/>
                <input type={'submit'}/>
            </form>
        );
    };
    
    export default SignUpPage;
    
    ```
    
    제가 만약 **`formData`**의 **`register`**에 아래와 같이 **`email`**, **`password`** 라는 이름으로, 연결했으니 아래와 같이 데이터가 출력됩니다.
    
    ![스크린샷 2024-09-17 오후 4.12.51.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/e2a62981-5cb1-4703-aed2-d758f6bde89d/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-17_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_4.12.51.png)
    
    우리가 위에서, 설명하기에는 **`yup`**을 활용해서, 유효성 검사를 진행한다고 했습니다. 이를 하기 위해서는 우리가 만든, **`schema`**를 **`resolve`** 하는 과정이 필요한데, 이를 위해 아래 라이브러리가 하나 더 필요합니다.
    
    ```tsx
    yarn add @hookform/resolvers
    ```
    
    먼저, 이메일과 비밀번호 관련해서 **`schema`**를 생성해보겠습니다. 여기서 말하는 **`schema`**는 쉽게 생각해서 **`유효성 검사`**라고 생각하시면 됩니다.
    
    우리의 **`회원가입 유효성 검사 조건`**은 아래와 같다는 가정하에 진행해보겠습니다.
    
    ### 이메일 유효성 검사 조건
    
    - [ ]  문자열이어야 한다.
    - [ ]  필수로 입력되어야 한다.
    
    ### 비밀번호 유효성 검사 조건
    
    - [ ]  문자열이어야 한다.
    - [ ]  최소 8글자이어야 한다.
    - [ ]  최대 16자이어야 한다.
    - [ ]  필수로 입력되어야 한다.
    
    **`yup`**의 **`object`**를 통해, **`schema`**의 **`shape을 정의`**할 수 있습니다.
    
    ```tsx
    import {useForm} from 'react-hook-form'
    import * as yup from 'yup'
    // TIP: zod를 사용하신다면 @hookform/resolvers/zod 를 import 하시면 됩니다!
    import {yupResolver} from '@hookform/resolvers/yup'
    
    const SignUpPage = () => {
        const schema = yup.object().shape({
            email: yup.string().email().required(),
            password: yup.string().min(8).max(16).required(),
        })
    
        const {register, handleSubmit} = useForm();
    
        const onSubmit = (data) => {
            console.log('폼 데이터 제출')
            console.log(data);
        }
    
        return (
            <form onSubmit={handleSubmit(onSubmit)}>
                <input type={'email'} {...register("email")}/>
                <input type={'password'} {...register("password")}/>
                <input type={'submit'}/>
            </form>
        );
    };
    
    export default SignUpPage;
    
    ```
    
    실제로, 이렇게 하면 적용이 되지 않습니다. 추가적인 처리를 해주어야 합니다. 우리가, 위에서 패키지로 설치한 **`yupResolver`**를 통해, 우리가 만든 **`schema`**를 연결시켜주면 됩니다.
    
    ```tsx
        const {register, handleSubmit} = useForm({
            resolver: yupResolver(schema)
        });
    ```
    
    그럼 이제 유효성 검사가 매우 잘되는 것을 확인할 수 있습니다.
    
    에러 메시지를 확인하고 싶으시면, **`useForm`** hook에서 **`formState`**를 추가로 불러와야 합니다.
    
    ```tsx
        const {register, handleSubmit, formState: {errors}} = useForm({
            resolver: yupResolver(schema)
        });
    ```
    
    아래와 같이 전체 코드를 구성하면 에러메시지를 볼 수 있습니다.
    
    ```tsx
    import {useForm} from 'react-hook-form'
    import * as yup from 'yup'
    import {yupResolver} from '@hookform/resolvers/yup'
    
    const SignUpPage = () => {
        const schema = yup.object().shape({
            email: yup.string().email().required(),
            password: yup.string().min(8).max(16).required(),
        })
    
        const {register, handleSubmit, formState: {errors}} = useForm({
            resolver: yupResolver(schema)
        });
    
        const onSubmit = (data) => {
            console.log('폼 데이터 제출')
            console.log(data);
        }
    
        return (
            <form onSubmit={handleSubmit(onSubmit)}>
                <input type={'email'} {...register("email")}/>
                // register 한 이름에 맞게 연결해주세요!
                <p style={{color: 'red'}}>{errors.email?.message}</p>
                <input type={'password'} {...register("password")}/>
                <p style={{color: 'red'}}>{errors.password?.message}</p>
                <input type={'submit'}/>
            </form>
        );
    };
    
    export default SignUpPage;
    
    ```
    
    ![스크린샷 2024-09-17 오후 5.07.41.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/6b74818d-e5d1-4b3f-b151-04c085b46578/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-17_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.07.41.png)
    
    위와 같이 에러메시지가, 나옵니다. 하지만, 우리는 한국인이기에, 영어로 된 에러메시지를 원하는 사람은 많지 않을 것 입니다.
    
    **`커스텀 에러 메시지 또한 선언`**해줄 수 있습니다.
    
    ```tsx
    const schema = yup.object().shape({
        email: yup.string().email().required('이메일을 반드시 입력해주세요.'),
        password: yup.string().min(8, '비밀번호는 8자 이상이어야 합니다.').max(16, '비밀번호는 16자 이하여야 합니다.').required(),
    })
    ```
    
    ![스크린샷 2024-09-17 오후 5.09.24.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/7b8d8f7d-4579-4511-928d-495857e9990e/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-17_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.09.24.png)
    
    특정 조건에 맞지 않는경우에 우리가 **`지정한 커스텀 에러`**를 넘겨줄 수 있습니다.
    

# ✅ 실습 1.  - 로그인 페이지 유효성 검사 구현 🍠

<aside>
💡

이번 실습은, 실제로 로그인 페이지를 만들어보는 것 입니다. 유효성 검사를 통해, 로그인 페이지를 구현해 보는 것 입니다.

여러분들은 2가지 방식으로, 해당 실습 미션을 제출해주셔야 합니다.

1. 강의 영상 없이, 본인이 스스로 작성한 코드.

2. 강의 영상을 참고한 후, 본인이 개선한 코드.

저의 코드가, 항상 정답이 아니기에, 여러분들이 직접 작성해보시고 그 이후에 제 코드를 참고하셔서, 코드를 수정해주셔도 좋습니다!
더 좋은 방식이 있으면 공유해주세요~ 😀

- Web 중앙 파트장 매튜 / 김용민 - 

</aside>

![스크린샷 2024-09-16 오후 9.28.39.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/f848035a-91b4-4f6a-8738-78d927da4e4f/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-16_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_9.28.39.png)

### UI

- [x]  이메일과, 비밀번호 **`type`**의 **`input`**을 2개 만들어주세요.
- [x]  모든 값을 입력한 후, 로그인 할 수 있는 **`로그인 버튼`**을 만들어주세요.

[화면 기록 2024-09-17 오후 3.31.03.mov](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/b4fd6547-f18d-4d29-bf8d-d77cbeb5ef1b/%E1%84%92%E1%85%AA%E1%84%86%E1%85%A7%E1%86%AB_%E1%84%80%E1%85%B5%E1%84%85%E1%85%A9%E1%86%A8_2024-09-17_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_3.31.03.mov)

### 기능 체크

- [x]  이메일은 **`올바른 이메일 형식이 아닐 경우`**, 위와 같이 에러 메시지와, UI상 변화가 나타나도록, 구현해주세요.
- [x]  비밀번호도, **`8자리 이상 16자리 이하가 아닌 경우`**, 에러메시지가 나오게 구현해주세요.
- [x]  에러 메시지는, **`실시간으로 조건이 충족하면, 사라져야 합니다.`**
- [x]  실제로, **`input 창을 클릭했을 경우`**, **`에러메시지가 나오게 동작`**해주세요. input 창을 누르지도 않았는데, 바로 에러메시지가 나오면, UX 측면에서 기분 좋지 않겠죠?

### 이것도 해보면 좋아요

- [x]  **`모든 조건을 충족하지 않았을 떄는, 로그인 버튼을 gray 색상으로 비활성화 되게 해주세요.`** (disabled props 활용)
    - [x]  실제로, 버튼 동작도 비활성화 되어야 합니다.
    - [x]  단 조건 충족시, 원래 색상(핑크)로 색상이 변경되게 합니다.

```jsx
LoginPage.jsx

import { useForm } from 'react-hook-form';
import * as yup from 'yup';
import { yupResolver } from '@hookform/resolvers/yup';
import * as S from './LoginPage.style';

const LoginPage = () => {
    const schema = yup.object().shape({
        email: yup.string().email('올바른 이메일 형식이 아닙니다. 다시 확인해주세요!').required('이메일을 입력해주세요.'),
        password: yup.string().min(8, '비밀번호는 8자 이상이어야 합니다.').max(16, '비밀번호는 16자 이하여야 합니다.').required('비밀번호를 입력해주세요.'),
    });

    const { register, handleSubmit, trigger, formState: { errors, isValid } } = useForm({
        resolver: yupResolver(schema),
        mode: 'onBlur', // 블러(포커스 아웃) 시에만 검증
        reValidateMode: 'onChange', // 조건 충족 시 실시간 검증
    });

    const onSubmit = (data) => {
        console.log('폼 데이터 제출');
        console.log(data);
    };

    return (
        <S.LoginForm onSubmit={handleSubmit(onSubmit)}>
            <S.Input 
                type="email" 
                {...register("email", {
                    onBlur: () => trigger('email') // 이메일 입력란을 벗어날 때 검증
                })} 
                placeholder="이메일을 입력해주세요!" 
            />
            <S.ErrorText>{errors.email?.message}</S.ErrorText>

            <S.Input 
                type="password" 
                {...register("password", {
                    onBlur: () => trigger('password') // 비밀번호 입력란을 벗어날 때 검증
                })} 
                placeholder="비밀번호를 입력해주세요!" 
            />
            <S.ErrorText>{errors.password?.message}</S.ErrorText>

            <S.SubmitButton type="submit" disabled={!isValid}>로그인</S.SubmitButton>
        </S.LoginForm>
    );
};

export default LoginPage;

```

```jsx
import styled from 'styled-components';

export const LoginForm = styled.form`
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: black;
    padding: 2rem;
    border-radius: 8px;
    color: white;
`;

export const Input = styled.input`
    width: 300px;
    padding: 10px;
    margin-bottom: 1rem;
    font-size: 16px;
    border: 2px solid #333;
    border-radius: 4px;
    background-color: white;

    &:focus {
        border-color: #3498db;
        outline: none;
    }
`;

export const ErrorText = styled.p`
    color: red;
    font-size: 14px;
    margin-top: -0.5rem;
    margin-bottom: 1rem;
`;

export const SubmitButton = styled.button`
    width: 300px;
    padding: 10px;
    font-size: 16px;
    color: white;
    background-color: ${props => (props.disabled ? '#b0b0b0' : '#e74c3c')};
    border: none;
    border-radius: 4px;
    cursor: ${props => (props.disabled ? 'not-allowed' : 'pointer')};

    &:hover {
        background-color: ${props => (props.disabled ? '#b0b0b0' : '#c0392b')};
    }
`;

```

### 실습 1 제출

- 실습 1 깃허브 링크 제출
- 실습 1 실행 영상 제출

# ✅ 실습 2.  useForm Hook을 통한 유효성 검사 🍠

<aside>
💡

위에서, 본인 코드로, 유효성 검사를 성공적으로 마치셨다면, 아래 영상을 보며, 코드를 리팩토링 해주세요!

저의 코드가, 정답은 아니니, 본인 코드에서 개선시킬 수 있는 점은 개선시켜봐도 좋고, 한 번 동일하게 만들어보는 과정도 좋습니다!

</aside>

https://www.youtube.com/watch?v=gWSAYvBH16I

### 구현 유의사항

- [x]  **`useForm`** hook을 사용했는가?

### 실습 2 제출

- 실습 2 깃허브 링크 제출
- 실습 2 실행 영상 제출

# 🔥 미션 - 회원 가입 페이지 제작 🍠

<aside>
💡

이번에는, 위에서 실습한, **`react-hook-form`**과 **`yup`**을 바탕으로 회원가입 페이지를 만들어보고자 합니다.

</aside>

![스크린샷 2024-09-17 오후 5.24.27.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/067e2dad-e8d9-4200-bdce-208932d73547/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-17_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.24.27.png)

### 유효성 검사 조건

- [x]  **`Email`** input을 만들어줍니다.
    - [x]  문자열이어야 합니다.
    - [x]  유효한 이메일 형식이어야 합니다.
    - [x]  이메일은 필수 입력요소입니다.
- [x]  **`Password`** input을 만들어줍니다.
    - [x]  문자열이어야 합니다.
    - [x]  비밀번호는 8자 이상이어야 합니다.
    - [x]  비밀번호는 16자 이하여야 합니다.
    - [x]  비밀번호는 필수 입력요소입니다.
- [x]  **`PasswordCheck`** input을 만들어줍니다.
    - [x]  **`Password input에 들어간 요소`**와, **`PasswordCheck input 요소`**에 들어간 요소의 **`value가 다를때`** **`비밀번호가 일치하지 않습니다. 라는 에러가 발생`**합니다.
    - [x]  비밀번호 검증은 필수 입력 요소입니다.

### 구현 유의 사항

- [x]  **`Input`** 컴포넌트를 만들어 잘 활용했는가?
- [x]  **`react-hook-form`** 과 **`yup`**의 라이브러리를 잘 활용했는가?
- [x]  모든 input의 value가, 원하는 **`{ key: value }`** 형태로 잘 출력되었는가?

### 이것도 해보면 좋아요 (필수 X)

- [ ]  실습 2에서 함께 만든 **`useForm hook을 활용`**해서, 위의 내용을 동일하게 만들어보세요!
    - **`useForm`** Hook으로 만든, 깃허브 링크 제출
    - **`useForm`** Hook으로 만든, 실행 영상 제출
- [ ]  성별이나, 생년월일 등 **`실제로 있을 법한 Form 요소들을 만들어, 추가적으로 더 만들어보시고 스터디원들과 공유`**해보세요!
- [ ]  **`zod`** 라이브러리도 한번 사용해보세요!

### 미션 제출

- 실습 2 깃허브 링크 제출
- 실습 2 실행 영상 제출

# ⚡ 트러블 슈팅

---

<aside>
💡 실습하면서 생긴 문제들 또는 어려웠던 내용에 대해서, **이슈 - 문제 - 해결** 순서로 작성해주세요.

</aside>

- ⚡이슈 No.1 (예시, 서식만 복사하시고 지워주세요.)
    
    **`이슈`**
    
    👉 앱 실행 중에 노래 다음 버튼을 누르니까 앱이 종료되었다.
    
    **`문제`**
    
    👉 노래클래스의 데이터리스트의 Size를 넘어서 NullPointException이 발생하여 앱이 종료된 것이었다. 
    
    **`해결`**
    
    👉  노래 다음 버튼을 눌렀을 때 데이터리스트의 Size를 검사해 Size보다 넘어가려고 하면 다음으로 넘어가는 메서드를 실행시키지 않고, 첫 노래로 돌아가게끔 해결
    
    **`참고레퍼런스`**
    
    - 링크

# 📢 학습 후기

---

- 이번 주차 워크북을 해결해보면서 어땠는지 회고해봅시다.
- 핵심 키워드에 대해 완벽하게 이해했는지? 혹시 이해가 안 되는 부분은 뭐였는지?

<aside>
📢

</aside>

# 🤔 참고 자료

---

Copyright © 2024 Kim Yongmin (Matthew) All rights reserved.