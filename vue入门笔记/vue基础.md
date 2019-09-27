
#### 使用vue-cli创建项目

```cmd
npm install -g vue-cli
vue init [webpack] 项目名
```
#### 组件通信

**父组件 => 子组件**
<!-- 
**这是加粗的文字**
*这是倾斜的文字*`
***这是斜体加粗的文字***
~~这是加删除线的文字~~ 
-->

- 属性props
   ```js
    // child 
    props: { msg: String } 
    // parent 
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    ```

- 特性$attrs
  ```js
    // child：并未在props中声明foo
     <p>{{$attrs.foo}}</p> 
     // parent
      <HelloWorld foo="foo"/>
  ```
- 引用refs
  ```js
    // parent
    <HelloWorld ref="hw"/> 
    mounted() { 
         this.$refs.hw.xx = 'xxx' 
    }
  ```

- 子元素$children
  ```js
    // parent 
    this.$children[0].xx = 'xxx'
  ```