# 装饰器

>类装饰器

``` typescript
// 无参装饰器
function addProp(constructor: Function) {
  constructor.prototype.someProp = 1
}

// 有参装饰器
function addCustomProp(key: string, value: any) {
  return function(constructor: Function) {
    constructor.prototype[key] = value
  }
}

@addProp
class A {}
const a = new A()
a.someProp == 1			// true

@addCustomProp('name', 'haha')
class B{}
const b = new B()
'name' in b			// true
b.name == 'haha'		// true
```

> 方法装饰器

``` typescript
function method(target: any, methodName: string, descriptor: PropertyDescriptor) {
  console.log(target)
  console.log(methodName)
  console.log(descriptor)
}

class C{
	// 实例方法
  @method
  function test() {}
  
  // 静态方法
  @method
  static function test2() {}
}

const c = new C()
c.test()
// output
// { test: [Function]}
// test
// {
//		writable: true,
//		enumerable: true,
//		configurable: true
// }

c.test2()
// output
// { [Function: ] test2: [Function]}
// test2
// {
//		writable: true,
//		enumerable: true,
//		configurable: true
// }
```

> Getter & Setter 装饰器

``` typescript
function lock(target:any, propertyKey: string, descriptor: PropertyDescriptor) {
  console.log(target, propertyKey, descriptor)
  descriptor.configurable = false
}

class D {
  private name: string
  constructor(name: string) {
    this.name = name
  }
  
  @lock
  get name(){
    return this.name
  }
}
```

