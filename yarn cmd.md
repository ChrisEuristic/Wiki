# Yarn 세팅 명령

### 최초 설정
```bash
$ npm install -g yarn
$ yarn set version berry
# .yarnrc.yml 파일에 nodeLinker: node-modules 추가
$ yarn install
```

### Next.js 프로젝트에서 Jest 사용하기

1. 의존성 추가
```bash
$ yarn add jest @types/jest --dev
$ jest --init
$ yarn add --dev ts-node
$ yarn add --dev ts-jest
$ yarn add --dev jest-environment-jsdom
```
2. jest.config.ts 파일 생성
```bash
$ jest --init
```
3. jest.config.ts 파일에 아래 내용 추가
```javascript
export default {
/* ... 생략 ... */
  preset: 'ts-jest',        // 기본값이 있지만 주석처리 되어있음.
  testEnvironment: 'node',  // 기본값 jsdom으로 되어있음.
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

```javascript
{
/* ... 생략 ... */
  "test": "jest",
/* ... 생략 ... */
}
```
