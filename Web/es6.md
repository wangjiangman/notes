1. Promise

    1. 含义： 异步编程的一种解决方案，可以将异步操作以同步操作的流程表达出来，避免层层嵌套回调函数。
        ```javascript
        // simple example
        let p = new Promise((resolve, reject) => {
          if(true) {
            resolve('ok')
          } else {
            reject('error')
          }
        })
        p.then((value) => {
          console.log(value)
        }, (error) => {
          console.log(error)
        })
        // ok

        let p1 = new Promise((resolve, reject) => {
          if(false) {
            resolve('ok')
          } else {
            reject('error')
          }
        })
        p1.then((value) => {
          console.log(value)
        }, (error) => {
          console.log(error)
        })
        // error
        ```

    2. Promise.prototype.then()   
      作用是为 Promise 实例添加状态改变时的回调函数,then方法的第一个参数是resolved状态的回调函数，第二个参数（可选）是rejected状态的回调函数。

    3. Promise.prototype.catch()    
      Promise.prototype.catch方法是.then(null, rejection)或.then(undefined, rejection)的别名，用于指定发生错误时的回调函数. **Promise异步操作和then方法回调函数中出现的错误都会被catch所捕获**

        一般来说，不要在then方法里面定义 Reject 状态的回调函数（即then的第二个参数），总是使用catch方法。
        ```javascript
        // bad
        promise
          .then(function(data) {
            // success
          }, function(err) {
            // error
          });

        // good
        promise
          .then(function(data) { //cb
            // success
          })
          .catch(function(err) {
            // error
          });
        ```
    4. Promise.prototype.finally()    
    指定了不管Promise对象最终状态如何(fulfilled , rejected),都会执行的操作。
    5. Promise.all()    
    Promise.all方法用于将多个 Promise 实例，包装成一个新的 Promise 实例。
        ```javascript
        const p = Promise.all([p1, p2, p3]);
        ```
        p的状态由p1、p2、p3决定，分成两种情况。

        （1）只有p1、p2、p3的状态都变成fulfilled，p的状态才会变成fulfilled，此时p1、p2、p3的返回值组成一个数组，传递给p的回调函数。

        （2）只要p1、p2、p3之中有一个被rejected，p的状态就变成rejected，此时第一个被reject的实例的返回值，会传递给p的回调函数。
