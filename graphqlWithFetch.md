# Apollo 를 사용하지않고 JS만으로 graph ql을 사용해보자.


```js
function GetPost(){
 async function fetching(){
   return await fetch('https://graphqlzero.almansi.me/api',{
     'method':'POST',
     'headers':{'content-type':'application/json'},
     'body':JSON.stringify({
       query:`{
         user(id:1){
           id
           name
         }
       }`
     })
   }).then(res=>res.json()).then(console.log)

  }

  return(
    <div>
      <button onClick={fetching}>click</button>
    </div>
  )
}
```
