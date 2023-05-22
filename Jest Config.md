### Next.js 프로젝트에서 Jest 사용하기

1. 의존성 추가
> npm
```bash

$ npm install --save-dev jest @types/jest
$ npm install --dev ts-node
$ npm install --dev ts-jest
$ npm install --dev jest-environment-jsdom
```
> yarn
```bash
$ yarn add jest @types/jest --dev
$ yarn add --dev ts-node
$ yarn add --dev ts-jest
$ yarn add --dev jest-environment-jsdom
```
2. jest.config.ts 파일 생성
```bash
$ npx jest --init
$ yarn jest --init

√ Would you like to use Jest when running "test" script in "package.json"? ... yes
√ Would you like to use Typescript for the configuration file? ... yes
√ Choose the test environment that will be used for testing » jsdom (browser-like)
√ Do you want Jest to add coverage reports? ... yes
√ Which provider should be used to instrument code for coverage? » v8
√ Automatically clear mock calls, instances, contexts and results before every test? ... yes
```
3. jest.config.ts 파일에 아래 내용 추가
```javascript
export default {
/* ... 생략 ... */
  preset: 'ts-jest',        // 기본값이 있지만 주석처리 되어있음.
  testEnvironment: 'node',  // node 환경일 경우에 적용.
/* ... 생략 ... */
};
```
4. tsconfig.json 파일에 아래 내용 추가
```javascript
{
  "compilerOptions": {
  /* ... 생략 ... */
    "types": ["jest"], // 추가
  /* ... 생략 ... */
}
```
5. package.json 파일에 아래 명령어 추가
> 위 순서를 잘 따라왔으면 설정되어있을 것.
```javascript
{
/* ... 생략 ... */
  "test": "jest",
/* ... 생략 ... */
}
```
