
# Singleton in JavaScript
```js
let Singleton = (function(){
    let instance;

    function createInstance(){
        let obj = new Object("I am an instance");
        return obj;
    }

    return{
        getInstance:function(){
            if(!instance){
                instance = createInstance();
            }
            return instance;
        }
    };
})();

let i1 = Singleton.getInstance();
let i2 = Singleton.getInstance();

console.log(i1===i2) // --> true
```