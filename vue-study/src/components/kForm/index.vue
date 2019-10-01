<template>
    <div>
        <h3>FormInput</h3>
        <FormInput  v-model="model.username" placeholder="请输入用户名"></FormInput>
        <FormInput  :value.sync="model.username"></FormInput>
        <p>{{model}}</p>
    </div>
</template>

<script>
import FormInput from './FormInput'

    export default {
        components: {
            FormInput
        },
        data () {
            return {
                model:{ username:"yiwa",password:"8888888"}
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>