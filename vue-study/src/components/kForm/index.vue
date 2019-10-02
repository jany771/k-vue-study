<template>
    <div>
        <!--<h3>FormInput</h3>
         <FormInput  v-model="model.username" placeholder="请输入用户名"></FormInput>
        <FormInput  :value.sync="model.username"></FormInput> 
        
        <p>{{model}}</p>
        -->
        <kForm :model="model" :rules='rules' ref="loginForm">
            <form-item label="用户名：" prop="username">
                <Form-input type="text" v-model="model.username" placeholder="请输入用户名">
                </Form-input>
            </form-item>
            <form-item label="密码：" prop="password">
                <Form-input type="password" v-model="model.password" placeholder="请输入密码">
                </Form-input>
            </form-item>
            <form-item>
                <button @click="submit">登录</button>
            </form-item>
        </kForm>

    </div>
</template>

<script>
import FormInput from './FormInput'
import FormItem from './FormItem'
import kForm from './Form'

    export default {
        components: {
            FormInput,
            FormItem,
            kForm
        },
        data () {
            return {
                model:{ username:"yiwa",password:"8888888"},
                rules:{
                    username:[
                        {required:true,message:"用户名必填！"}
                    ],
                     password:[
                        {required:true,message:"密码不能为空！"}
                    ],
                }
            }
        },
        methods: {
            submit(){
                this.$refs.loginForm.validate(isValidate=>{
                     if (isValidate) {
                      alert("登录中。。。");
                    } else {
                      alert("错误，需重新输入");
                    }

                })
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>