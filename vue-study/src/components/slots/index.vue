<template>
    <div>
        <h1>匿名插槽</h1>
        <slot1>
            大大方方的方式
           <template #todo>插槽内容todo text container</template> 
           <!-- 作用域插槽 -->
           <template  #item2="propName">{{propName.pw}}</template>
           <!-- 解构对象 -->
           <template  #item="{pw,m}">{{pw}}{{m}}</template>
           

        </slot1>
        <!---->
    </div>
</template>

<script>
import slot1 from './s1.vue'
    export default {
        name:'slots',
        components: {
            slot1,
        }
    }
</script>

<style lang="scss" scoped>

</style>