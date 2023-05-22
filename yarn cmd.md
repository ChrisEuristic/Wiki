# Yarn 세팅 명령

### 최초 설정
```bash
$ npm install -g yarn
$ yarn set version berry
# .yarnrc.yml 파일에 nodeLinker: node-modules 추가
$ yarn install
```

### 의존성 추가
```bash
$ yarn add jest @types/jest --dev
$ yarn add --dev ts-node
```
