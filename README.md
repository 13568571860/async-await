###async解决回调地狱
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
#await后的表达式必须返回一个Promise对象, 函数遇到await是会自动停止函数执行直到Promise状态改变在继续执行下一步