<template>
    <div>
        <input :type="type" :value="value"  @input="onInput"
         v-bind="$attrs"/>
         <!-- v-bind会展开$attrs对象 -->
    </div>
</template>

<script>
    export default {
        props: {
            type:{
                type: String,
                default: "text"
            },
            value: {
                type: String,
                default: ''
            }
        },
        mounted(){
            console.log(this.$attrs);
        },
        methods: {
            onInput(e){
                //仅派发事件 把值传给老爹
                //v-model
                this.$emit('input',e.target.value);
                //.sync
                 this.$emit('update:value',e.target.value)
            }
        }
        
    }
</script>

<style lang="scss" scoped>

</style>