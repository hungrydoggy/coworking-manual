# 개요
협업을 함에 있어, 개발에 필요한 형식을 일치 시키기 용이하도록, 이 문서를 작성한다.

# 네이밍
## 파일과 폴더 네이밍
| 대분류 | 분류 | 형식 | 비고
| --- | --- | --- | ---
| directory | all | `snake_case` | 
| file | React Component | `PascalCase` | 컴포넌트와 1:1 매칭이 쉽도록
| | other files | `snake_case` |

## 코드 요소 네이밍
| 대분류 | 분류 | 형식 | 비고
| --- | --- | --- | ---
| class | public class name | `PascalCase` |
| | private class name | `_PascalCase` |
| | public method | `camelCase` |
| | private method | `_camelCase` | 용도가 private (내부 사용) 이면
| | public variable | `snake_case` |
| | private variable | `snake_case_` | 용도가 private (내부 사용) 이면
| etc | local variable | `snake_case` |
| | parameter | `snake_case` |

# 코드 작성
## 기본 규칙
- tab은 space 2개로 사용한다.
- 코드는 public 할 수록 위에, private 할 수록 아래에 둔다.
- public은 꼭 필요한 곳에만 사용gksek.
- static을 최 상단에, constructor는 그 다음에, 나머지는 그 다음에 둔다.
- 주석은 꼭 필요한 때만 사용한다.  
(대부분 주석이 필요한 긴 코드는, 함수화 하고 함수 이름을 잘 지어서 해결하기.)  
주석이 없어도 잘 읽히는 코드가 좋은 코드다.
- 함수 내에 의미적으로 그룹이 같은 줄 끼리는 줄을 붙이거나, 사이에 한 줄만 띄운다.  
의미적으로 분리된 것 끼리는 두 줄 이상 띄운다.  
그룹이 큰 경우는 함수로 따로 빼는 것이 좋은 경우가 많다.
- 변수와 함수 네이밍의 경우, 해당 변수/함수가 영향을 미치는 범위가 넓을 수록 이름을 길게 한다.
- 의미적으로 연관이 있을 때, vertical alignment를 한다.
- 함수를 선언할 때는 괄호 앞뒤에 공백을 넣는다.  
`abc (a, b, c) {`
- 함수를 호출할 때는 괄호 앞뒤에 공백을 넣지 않는다.  
`abc(a,b,c).result`
- 함수의 파라미터나 jsx가 너무 길어지면, 여러줄로 표시한다. 들여쓰기는 한번만 한다.
- if, for, while 등등의 구문의 괄호 앞뒤에 공백을 넣는다.  
`if (a === b) {`
- lambda나 arrow function의 경우, 한줄 일때는 공백을 최대한 줄여서 사용하고, 여러줄일때는 공백을 넣는다.  
`(v)=>v+1`, `(v)=>{return v+2;}`  
```
(v) => {  // 여러 줄일 때
  let w = v + 3
  return w + 4;
}
```

## 코드 작성 순서
```
//import parts
//// no-local-code import part : 기본이나, npm으로 받은 모듈 들. 정렬은 from 이후 기준, 디렉토리 -> 파일 순으로.
import uuid from 'uuid/v4';
import $ from 'jquery';
import fetch from 'node-fetch';


//// local-code import part : 로컬에 있는 코드들. 항상 상대적 경로로 작성. 정렬은 from 이후 기준, 디렉토리 -> 파일 순으로. (..이 최우선 그 다음이 .)
import TextComponent from '../snippet/test/TestComponent';
import AbcComponent from '../snippet/AbcComponent';
import GeneralTable from '../snippet/GeneralTable';
import test_util from './test/test_util';
import world_test from './test/world';
import abc from './abc';


//// other import part : css나 그림 파일 등등. 순서는 같다.


// class parts
class MyClass {

}


// 나머지 코드들 (일반 함수 등등)


// export parts : 어찌보면 제일 public 하지만, export 할 내용을 먼저 써야 하므로, 어쩔 수 없이 맨 아래에
export defualt MyClass;
```

## Vertical Alignment
```
// 세미콜론을 제외한 기호와, word 기준으로 정렬한다.
const animal    = 'Animal';
const human     = 'Human';
const anonymous = 'Anonymous';

// 만일 코드 라인이 서로 빈줄 없이 붙어있더라도, 의미적/형식적으로 연관이 있는 것 끼리만 정렬 한다.
const name    = 'Bunny';
const age     = 4;
const address = 'Rabbit hole';  // 이 라인 기준 위로 3개끼리 정렬됨
const animal_res    = findAnimal   (name    , age , address   );
const humna_res     = findHuman    (name    , age , address   );
const anonymous_res = findAnonymous('noname', 1000, 'no where'); // 이 라인 기준 위로 3개끼리 정렬됨

// 숫자는 소숫점 위치를 맞추어 정렬한다.
const first  = findFirst  ('first one' , 1000   , 'other options'         );
const second = findSecond ('second one',  -30   , 'my second long options');
const third  = findThird  ('third one' ,    3.14, '...'                   );
const fourth = findFourth ('fourth one',  -10.1 , '...'                   );
```
