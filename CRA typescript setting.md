## 설치와 

- 사용 툴 : yarn

yarn create react-app my-app --template=typescript

yarn add -D husky lint-staged prettier

---
- root/prettierrc.js

```js
module.exports={
	jsxBracketSameLine:true,
	singleQuote:true,
	trailingComma:'all',
	printWidth:100,
};
```

---

- package.json
```js
"scripts":{
...
},
  "husky":{
    "hooks":{
      "pre-commit":"lint-staged"
    }
  },
  "lint-staged":{
    "src/**/*.{js,jsx,ts,tsx,json,css,scss,md}":[
      "prettier --write"
    ]
  },
  ...
  
  ```
  
- tsconfig.json
```json
{
  "compilerOptions": {
    "target": "es5",
    "lib": [
      "dom",
      "dom.iterable",
      "esnext"
    ],
    "allowJs": true,
    "skipLibCheck": true,
    "esModuleInterop": true,
    "allowSyntheticDefaultImports": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noFallthroughCasesInSwitch": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx"
  },
  "include": [
    "src"
  ]
}

```
