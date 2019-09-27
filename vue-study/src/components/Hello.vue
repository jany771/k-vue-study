<template>
    <div class="hello">
        <h1>{{message}}</h1>
        <p>{{$attrs.foo}}</p>
        <p>我的名字是{{name}}</p>
    </div>
  
</template>

<script>
    export default {
        name:'hello',
        props: {
            message: String
        },
        data () {
            return {
                name:"yiwa"
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>