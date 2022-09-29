<template>
    <div class="flex flex-col items-center">
        <img src="../assets/laptop.svg">
        <div class="bg-primary flex flex-col justify-center items-center gap-2 w-full h-28">
            <h1 class="text-white text-[13px] md:text-[15px] font-bold mt-2 text-center">{{name}}</h1>
            <span class="bg-green-500 text-[13px] md:text-[15px] px-[4px] py-[3px] rounded-md text-white">Rp.{{harga}}</span>
            <span class="bg-red-500 text-[12px] md:text-[13px] px-2 py-2 rounded-md text-white mb-3">Stok {{stok}}</span>
        </div>
        
    </div>
</template>

<script>
export default {
    name : 'Card-Comp',
    props:{
        name : String, 
        harga : Number,
        stok : Number
    }
}
</script>

<style>

</style>