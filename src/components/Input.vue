<template>
    <input v-model="input" @input="isTyping" type="text" :placeholder="name"> 
</template>

<script>
export default {
    name:'Input-Comp',
    props:{
        name:String
    },
    data(){
        return{
            input:''
        }
    },
    methods:{
        isTyping(){
            this.$emit('isTyping',this.input)
        }
    }

}
</script>