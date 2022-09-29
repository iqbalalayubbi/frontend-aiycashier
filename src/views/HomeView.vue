<template>
  <div class="home flex flex-col items-center">
    <div class="flex items-center justify-center md:justify-between w-full h-20 bg-primary px-10">
      <img src="../assets/logo.svg" class="hidden md:block" width="200">

      <div class="w-[90%] md:w-[40%] flex flex-col relative">
        <div class="flex items-center w-full h-10">
            <Input class="input border-white border-2" name="cari item . . ." @isTyping="onTyping"/>
            <div class="bg-primary h-full flex items-center justify-center w-10 rounded-tr-md rounded-br-md border-t-2 border-white border-b-2 border-r-2">
              <Icon-elit icon="akar-icons:search" class=" text-white "></Icon-elit>
            </div>
        </div>
        <div v-show="isSearch" class="absolute top-12 bg-white w-[90%] border-2 border-primary px-3 py-2 rounded-md z-10">
          <h1 v-for="(item,i) in items" :key="i" :class="[i == 0 ? 'bg-gray-200' : '']">{{item.name}}</h1>
        </div>
      </div>

      <div class="flex gap-5">
        <Button name="Login" class="bg-white"/>
        <Button name="Register" class="bg-black text-white"/>
      </div>

    </div>
    <Banner class="mt-6"/>
    <div class="mt-20 mb-10 flex justify-center gap-y-5 gap-5 w-full  md:px-10 flex-wrap">
      <Card v-for="(item,i) in items" :key="i" :name="item.name" :harga="item.harga" :stok="item.stok" class="w-40 md:w-52"/>
    </div>
  </div>
</template>

<script>
import Input from '@/components/Input.vue'
import Banner from '@/components/Banner.vue'
import Button from '@/components/Button.vue'
import Card from '@/components/Card.vue'

export default {
  name: 'HomeView',
  data(){
    return{
      isSearch:false,
      data:[
        {
          name :'laptop ROG 3080',
          harga : 200000,
          stok : 5
        },
        {
          name :'mouse gaming',
          harga : 300000,
          stok : 10
        },
        {
          name :'keyboard mechanical',
          harga : 80000,
          stok : 90
        },
        {
          name :'mouse fantech rgb',
          harga : 99000,
          stok : 10
        },
        {
          name :'pc gaming',
          harga : 2500000,
          stok : 90
        },
      ],
      items:[]
    }
  },
  components:{Input,Banner,Button,Card},
  methods:{
    onTyping(input){
      if (input.length !== 0){
        const itemsFind = []
        this.data.forEach(item => {
          if(item.name.startsWith(input)){
            console.log('benar')
            itemsFind.push(item)
            this.items = itemsFind
            this.isSearch = true
          }
        })
      }else{
        this.isSearch = false
        this.items = this.data
      }
    }
  },
  created(){
    this.items = this.data
  }

}
</script>
