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
