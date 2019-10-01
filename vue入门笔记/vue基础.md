
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
-----

  ### 作业
**1. 能手写Form、FormItem、Input实现**
**2. 尝试解决Input里面$parent派发事件不够健壮的问题**


**3. 说出.sync和v-model的异同**
*数据双向绑定*
##### v-model
```js
//parent index.vue
<FormInput  v-model="model.username" placeholder="请输入用户名"></FormInput>
 <FormInput  :value.sync="model.username"></FormInput>
```

```js 
//children FormInput.vue
<input :type="type" :value="value"  @input="onInput"
         v-bind="$attrs"/>
```

```js        
  methods: {
    onInput(e){
        //仅派发事件 把值传给老爹
        //v-model
        this.$emit('input',e.target.value);
        //.sync
        this.$emit('update:value',e.target.value)
    }
  }

```
