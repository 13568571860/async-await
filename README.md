#async解决回调地狱
```
async function demo () {
  for (let i = 0; i < 5; i++) {
    console.log(1)
    await new Promise((reslove, reject) => {
      setTimeout(function(){
        console.log(i)
        reslove()
      }, 2000)
    })
    console.log(2)
  }
}
demo()
```