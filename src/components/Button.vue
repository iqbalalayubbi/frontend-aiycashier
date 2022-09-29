<template>
    <button class="rounded-md px-3 py-2 hidden md:block">{{name}}</button>
</template>

<script>
export default {
    name:'Button-Comp',
    props:{
        name : String
    }
}
</script>

<style>

</style>