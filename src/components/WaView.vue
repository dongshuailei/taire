<template>
    <div>
        <div v-for="(item,index) in list" :key="index">
          <img :src="item.url" alt="" style="width: 60px;height: 100px;margin-left: 20px;">
        </div>
    </div>
</template>
<script>
  export default{
    data(){
        return{
            list:[
        {
          url:'https://wfqqreader-1252317822.image.myqcloud.com/cover/492/35742492/t6_35742492.jpg',
        },
      ]
        }
    }
  }
</script>