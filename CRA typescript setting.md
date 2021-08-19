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
"compilerOptions":{
	...
	"jsx":"react-jsx",
	"baseUrl":"src"
	},
	...
}
```
