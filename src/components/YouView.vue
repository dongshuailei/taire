<template>
    <div style="width: 770px;height: 503px;margin-top: 10px;margin-left: 20px;">
        <div>
            <h2 style="display: flex;font-size: 18px;width: 764px;height: 31px;">
                <img :src="arrlist.img" alt="">
                <span>{{arrlist.name}}</span>
                <span style="flex: 1;"></span>
                <i>!</i>
            </h2>
            <div v-for="(item, index) in you" :key="index">
                <span 
                style="width: 764px;height: 34px;display: inline-block;line-height: 34px;font-size: 14px;display: flex;align-items: center;cursor: pointer;">
                    <span a
                    :style="{background:index===0?'#fe2d46' : index === 1 ? '#f60' : index === 2 ? '#faa90e' : '#F0F1F4',color:index===0?'#fff' : index === 1 ? '#fff' : index === 2 ? '#fff' : 'block'}"
                        style="width: 18px;line-height: 18px;height: 18px;display: inline-block;text-align: center;border-radius: 4px;font-size: 12px;background-color: var(--bg-input);">{{
                            item.img }}</span>
                    <span style="flex: 1" class="aaaa">{{ item.name }}</span>
                    <span >{{ item.i }}</span>
                </span>
            </div>
        </div>
    </div>
</template>
<script>
import Da from './data.json'
export default {
    props:[
        'you',
        'arrlist',
    ],
    data() {
        return {
            us: [],
        dataList:''
        }
    },
    mounted() {
        this.us = Da[0].books
    }
}
</script>
<style lang="less" scoped>
img {
    width: 20px;
    height: 20px;
    margin-right: 10px;
    border-radius: 50%;
}
.aaaa:hover{
    color: #1890ff;
}
span {
    margin-right: 10px;
}</style>