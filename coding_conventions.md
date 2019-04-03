# 개요
협업을 함에 있어, 개발에 필요한 형식을 일치 시키기 용이하도록, 이 문서를 작성한다.

# 파일과 폴더 네이밍
| 대분류 | 분류 | 형식 | 비고
| --- | --- | --- | ---
| directory | all | `snake_case` | 
| file | React Component | `PascalCase` | 컴포넌트와 1:1 매칭이 쉽도록
| | other files | `snake_case` |

# 코드 요소 네이밍
| 대분류 | 분류 | 형식 | 비고
| --- | --- | --- | ---
| class | public class name | `PascalCase` |
| | private class name | `_PascalCase` |
| | public method | `camelCase` |
| | private method | `_camelCase` | 용도가 private (내부 사용) 이면
| | public variable | `snake_case` |
| | private variable | `snake_case_` | 용도가 private (내부 사용) 이면

# 코드 작성 순서
## 기본 규칙
- public 할 수록 위에, private 할 수록 아래에.
- static을 최 상단에, constructor는 그 다음에, 나머지는 그 다음에.
```
//import parts
//// no-local-code import part : 기본이나, npm으로 받은 모듈 들. 정렬은 from 이후 기준, 디렉토리 순으로. (..이 최우선 그 다음이 .)
import uuid from 'uuid/v4';
import fetch from 'node-fetch';
import $ from 'jquery';


//// local-code import part : 로컬에 있는 코드들. 정렬은 from 이후 기준, 디렉토리 순으로. (..이 최우선 그 다음이 .)
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
