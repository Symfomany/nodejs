## NodeJS 

* Destructuring Parameter
* Destructuring Object
* Spread Operator
* Rest Parameter
* Enhance Object affectation



 Promises in ES6


 setTimeout(function(){
  console.log('Yay!')
}, 1000)


var wait1000 =  new Promise(function(resolve, reject) {
  setTimeout(resolve, 1000)
}).then(function() {
  console.log('Yay!')
})

avec fonction fléchée:
var wait1000 =  new Promise((resolve, reject)=> {
  setTimeout(resolve, 1000)
}).then(()=> {
  console.log('Yay!')
})


Ainsi je peux chainer

setTimeout(function(){
  console.log('Yay!')
  setTimeout(function(){
    console.log('Wheeyee!')
  }, 1000)
}, 1000)

// No..

var wait1000 =  ()=> new Promise((resolve, reject)=> {setTimeout(resolve, 1000)})

wait1000()
    .then(function() {
        console.log('Yay!')
        return wait1000()
    })
    .then(function() {
        console.log('Wheeyee!')
    });
