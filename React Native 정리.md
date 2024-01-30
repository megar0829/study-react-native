## React Native 정리

1. Web : `div` => App: `View`

   - 앱에서는 웹에서 Elements를 담아서 틀을 구성했던 div 태그는 사용이 불가능하고 `View` 라는 새로운 틀을 사용해야 한다. 
   - View 뿐만이 아니라 Text, StyleSheet 등 기존 React Web 에서 사용했던 개념들과는 조금 다르게 사용해야 하는 컴포넌트 구성들이 있다.

2. React Native Layout

   - Layout을 구성하기 위해서는 View를 사용해서 구조를 잡아야 하는데 모바일 App 의 경우 View의 기본 display style은 Flex 이고 Flex Direction은 Column 방향이다.

   - 하나의 View에 여러 개의 Element를 작성했다면 화면 상으로 세로 정렬되어 보이게 된다. 이를 조작하여 우리가 원하는 Layout을 구성한다.

   - Layout 비율 구성

     => View style 속성에 `flex: {상수}` 값을 넣어서 부모 Element에 대하여 비율을 조절할 수 있다. 예를 들어 부모 Element의 height 값이 400 이라면 두 개의 자식 Element에 `flex: 1` 을 입력했을 때 각 Element 들이 200 의 height 값을 갖게 된다. 즉, flex 뒤에 들어가는 상수로 부모 Element의 값을 비율로 나눌 수 있다.

3. Libraries

   - 외부 API, Icon 들은 react-native-community, Expo-docs 등 공식 문서나 커뮤니티 사이트에서 서드파티 라이브러리로 import 한 후 사용할 수 있다. 

     => react native는 공부할 양이 방대하기 때문에 모두 외워서 사용하는 것이 아니라 필요한 기능들을 그때그때 찾아서 가져오면 된다.

4. Styles

   - react native 에는 `StyleSheet` 라는 내부 Library가 있다. 
   - 해당 라이브러리의 create 메서드를 통해서 react의 class style 속성 처럼 사용할 수 있다.
   - Inline Style 속성을 사용해도 되지만 코드의 가독성이 떨어지며 재사용성이 떨어질 수 있으므로 따로 styles 변수를 만들어서 사용하는 것을 권장한다.

5. Button

   - react native 에서 button 사용을 위해서는 TouchableOpacity, TouchableHighlight,  TouchableNativeFeedback, Pressable를 사용해야 한다.
     - TouchableOpacity : 클릭 시 투명도가 생겼다가 사라진다.
     - TouchableHighlight : 클릭 시 밝아졌다가 다시 돌아온다.
     - TouchableNativeFeedback : 클릭 시 외형의 변화가 없고 callback 함수를 실행시키는 용도로 사용된다.
     - pressable : 위 세가지의 특성을 모두 가질 수 있는 컴포넌트로 props 속성을 통해서 커스텀할 수 있다.
   - React : onClick, onSubmit 등의 이벤트 함수 
     => React Native : onPress, onSubmitEditing 등 이름은 조금씩 다르지만 같은 기능을 한다.
     - onPress : onPressIn (사용자의 터치가 박스 안으로 들어왔을 때) + onPressOut (사용자의 터치가 박스 밖으로 나갔을 때) 둘이 합쳐진 것 (클릭 그 자체)

6. Text Input

   - returnKey Type : 키보드의 제출 버튼 타입을 선택
   - onChangeText : 값이 변할때 호출되는 함수

7. 