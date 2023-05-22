# 문제 해결 사전

## next.js 프로젝트를 진행 중, 패키지매니저를 npm에서 yarn으로 변경하는 상황

#### 발생한 문제
- react와 react-dom 모듈을 인식하지 못하는 문제 발생.
- lock 파일을 모두 삭제, 모듈 싹 밀고 yarn install해도 동일한 에러 발생.

#### 해결
```json
{
  "compilerOptions": {
    ...생략,
    "types": ["react"], // 해당 내용 추가
    ...생략,
}

```
```bash
$ yarn add @types/react
```
