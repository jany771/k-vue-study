<template>
    <div>
        
        <h3>todo slots</h3>
        <slot></slot><br>
        <slot name="todo">11</slot>
       <p> <slot name="item" :pw="password" :m="true"></slot></p>
       <p> <slot name="item2" :pw="jk" ></slot></p>
      
    </div>
</template>

<script>
    export default {
        name:'s1',
        data () {
            return {
                password:"9999999",
                jk:"jjjjkkk"
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>