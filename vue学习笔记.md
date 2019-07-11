#### 6.30-iview demo

```js
<template>
    <Input v-model="switch1" @on-change="printHandler" />
    <Input v-model="switch1" @on-change="change" />
    <br><br>
    <Button type="primary" @click='printHandler'>打印</Button>
    <br><br>
    <p>{{this.switch1}}</p>
</template>
<script>
    export default {
        data () {
            return {
                switch1: 'hahah '
            }  
        },
        methods: {
            change (status) {
                this.$Message.info('开关状态：' + status)
            },
          printHandler() {
            console.log(this.switch1)
          }
        }
    }
</script>
```

* 使用 ivew 复制模板

* 点击事件 >> @click='printHandler'

  ```js
  <Button type="primary" @click='printHandler'>打印</Button>
  
  methods: {
            printHandler() {
              console.log(this.switch1)
            }
          }
  ```

  

* 数据绑定 >> v-model="switch1"

  ```js
  <Input v-model="switch1" @on-change="printHandler" />
      
  data () {
              return {
                  switch1: 'hahah '
              }  
          }
  ```

* on-change事件【仅表单使用 form input ...】 >>  @on-change

  ```
  <Input v-model="switch1" @on-change="change" />
  ```

  data () {
              return {
                  switch1: 'hahah '
              }  
          },
          methods: {
              change (status) {
                  this.$Message.info('开关状态：' + status)

  ```js
          },
        printHandler() {
          console.log(this.switch1)
        }
      }
  ```

* 运行 iview 的命令：npm run dev

* 大括号插入变量中数据【数据双向绑定】：

  **input 的 v-model 绑定，影响 data 的值，所以 this.switch1 中 this.获取当前对象的值**

  ```js
  <template>
      <Input v-model="switch1" @on-change="printHandler" />
      <p>{{this.switch1}}</p>
  </template>
  
  <script>
      export default {
          data () {
              return {
                  switch1: 'hahah '
              }  
          },
      }
  </script>
  ```

* $Message 会话框的文字修改

  $ 内置DOM对象的 info 方法（）内是文字内容

```vue
	change (status) {
                this.$Message.info('开关状态：' + status)
            }
```

#### 7.8-iview 初次使用

1.使用router文档

​	打开源码，需要模仿修改路由

2.按照复制的其他组件的代码，进行修改

3.复制青焓同学的表单代码

``` vue
	<Table border :columns="columns1" :data="data1">
            <template slot-scope="{ row, index }" slot="name">
                <span>{{ row.name}}</span>
            </template>

            <template slot-scope="{ row, index }" slot="age">
                <span>{{ row.age}}</span>
            </template>

            <template slot-scope="{ row, index }" slot="address">
                <span>{{ row.address}}</span>
            </template>

            <template slot-scope="{ row, index }" slot="action">
                <Button class='btn' type="success" >删除</Button>
                <Button class='btn' type="info" >编辑</Button>
            </template>
      </Table>
```

​	1）绑定数据，

​	2）row 表示一列的所有内容，slot 表示对应下面的列内容

​	3） button的按键样式修改，修改margin-left，注意CSS的使用

​	4）v-for的使用

``` vue
		<h1 v-for='item in msg'>{{item.id}}={{item.name}}</h1>
```

##### 7.10-iview路由配置和vue语法基础

1.iview布局

​	使用iview的栅栏，布局

2.iview路由配置

​	需要在router文件中配置，如果不是在第一个界面就显示的页面，hideInMenu：true，使用跳转，到这个界面

​	写作步骤：

​		1）配路由

​		2）写对应的vue文件

3.读懂vue的语法

​	1）