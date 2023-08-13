<template>
    <div style="width: 210px;height: 513px;border-right: 1px solid rgba(var(--alpha-color),.04);overflow: auto;">
        <div class="a">
            <input type="text" placeholder="搜索" v-model="searchQuery">
        </div>
        <ul>
            <li  v-for="(item, index) in filteredArr" class="li1" :key="index"  :class="{ li1: true, 'li-selected': selectedItemIndex == index }" @click="dianjai(item.name,item.img,index)">
                <img :src="item.img" alt="">
                {{ item.name }}
            </li>
        </ul>
    </div>
</template>
<script>
import Da from './da.json'
export default {
    props: [
        'arr'
    ],
    data() {
        return {
            users: [],
            list: '.li1',
            cla: 'background-color: red;',
            searchQuery: '',
            selectedItemIndex: 0,
        }
    },
    methods: {
        dianjai(name,img,index){
            let dataList={
                name: name,
                img: img,
                index:index
            }
            this.selectedItemIndex = index
            this.$emit('dataList',dataList)
     
        }
    },
    updated() {
        

    },
    computed: {
        filteredArr() {
            if (this.searchQuery) {
                return this.arr.filter(item => item.name.toLowerCase().includes(this.searchQuery.toLowerCase()));
            } else {
                return this.arr;
            }
        },
    },
    mounted() {

        this.users = Da[0].books
    }
}
</script>
<style lang="less" scoped>
.li1 {
    width: 140px;
    height: 20px;
    padding: 10px 20px;
    font-size: 13px;
    cursor: pointer;
}
.a {
    --el-input-bg-color: var(--bg-input);
    --el-input-border-color: transparent;
    --el-input-focus-border-color: var(--el-border-color-hover);
    padding: 1px 7px;
    font-size: inherit;
}
.li-selected {
    background: #1890ff;
     color: #fff;
}
input {
    width: 174.09px;
    height: 22px;
    border-radius: 20px;
    border: none;
    padding-left: 10px;
    background: #F0F1F4;
    font-size: 14px;
}

img {
    display: inline-block;
    width: 20px;
    height: 20px;
    vertical-align: middle;
}</style>