<template>
  <div class="h-52 w-screen flex flex-col items-center gap-5 relative bg-green-500">
    <h1 class="pt-5 text-center text-4xl z-8 text-white font-bold">Sumber Jaya Abadi</h1>
    <img src="../assets/thumb.svg" class="z-10" width="200">
  </div>
</template>

<script>
// import banner from '@/assets/banner.png'
export default {
    name : 'Banner-Comp'
}
</script>
<style scoped>
    div{
      background:linear-gradient(rgb(0,0,0,0.6), rgb(0,0,0,0.3)), url("../assets/banner.svg")
    }
</style>