<template>
    <div>
        <ul class="u">
            <li :class="item.flag ? 'li_active' : ''" v-for="(item, index) in list" :key="index" @click="fun(index)"
                style="cursor: pointer;" >
                <span class="xvc" v-show="item.flag"></span>
                <span style="height: 32px;display: inline-block;">
                    <a v-html="item.img" style="padding-left: 10px;"></a>
                    &nbsp;
                    <span style="width: 120px;height: 32px;display: inline-block;" @dblclick="toggleText(index)"
                        @click="dianjiaaa(item.name,index)">
                        <a v-show="!item.inpflag">{{ item.name }}</a>
                        <input @blur="lichange(index)" @input="dianji(inpval)" v-show="item.inpflag" type="text"
                            v-model="inpval" style="width: 130px;display: inline-block;height: 20px;border: none;">
                    </span>
                </span>
                <span style="cursor: pointer;" class="el-icon-delete"></span>
                <span>{{ 0 }}</span>
            </li>
        </ul>
        &nbsp;
        <div
            style="display: flex; width: 184px; height: 11px; align-items: center; padding-bottom: .75rem;margin-left: 10px;">
            <i class="el-icon-plus"></i>
            &nbsp;
            <span style="font-size: 16px; cursor: pointer;" @click="addNewList">新建列表</span>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            list: [
                {
                    img: '<svg t="1692262794704" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="8765" width="16" height="16"><path d="M0 505.135c0-0.723 0.723-2.168 0.723-2.89 3.613-18.79 13.007-33.243 29.628-42.637 7.227-4.336 15.176-5.782 23.125-6.504H961.13c20.234 0 35.41 8.672 46.973 24.57 8.671 12.285 12.285 25.293 10.84 40.469-2.891 23.124-18.79 43.359-42.637 49.14-6.504 1.445-13.008 2.168-20.234 2.168H58.535c-23.848 0-39.746-11.563-51.308-31.074-3.614-5.781-5.059-12.285-6.504-18.79 0-0.722-0.723-2.167-0.723-2.89v-11.562zM0 205.234c0-0.723 0.723-2.168 0.723-2.891 3.613-18.789 13.007-33.242 29.628-42.637 7.227-4.335 15.176-5.78 23.125-6.503H961.13c20.234 0 35.41 8.671 46.973 24.57 8.671 12.285 12.285 25.293 10.84 40.468-2.891 23.125-18.79 43.36-42.637 49.14-6.504 1.446-13.008 2.169-20.234 2.169H58.535c-23.848 0-39.746-11.563-51.308-31.074-3.614-5.782-5.059-12.285-6.504-18.79 0-1.445-0.723-2.89-0.723-3.613v-10.84zM51.308 862.848c-1.445 0-2.168-0.722-3.613-0.722-16.62-3.614-28.183-13.008-36.855-27.461-6.504-10.84-9.395-22.402-8.672-34.688 2.168-24.57 19.512-46.25 44.804-52.03 5.06-1.446 10.84-1.446 16.622-1.446h899.703c19.512 0 34.687 8.672 46.25 23.848 7.226 10.117 11.562 22.402 11.562 34.687 0 14.453-5.058 27.46-14.453 38.3-9.394 10.84-21.68 17.344-36.132 18.79-0.723 0-1.446 0-2.168 0.722H51.308zM1024 189.335c-0.723-2.168-0.723-5.058-1.445-7.226l1.445 7.226z" p-id="8766" fill="#bfbfbf"></path></svg>',
                    name: '待办事项',
                    flag: true,
                    inpflag: false,
                },
                {
                    img: '<svg t="1692262794704" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="8765" width="16" height="16"><path d="M0 505.135c0-0.723 0.723-2.168 0.723-2.89 3.613-18.79 13.007-33.243 29.628-42.637 7.227-4.336 15.176-5.782 23.125-6.504H961.13c20.234 0 35.41 8.672 46.973 24.57 8.671 12.285 12.285 25.293 10.84 40.469-2.891 23.124-18.79 43.359-42.637 49.14-6.504 1.445-13.008 2.168-20.234 2.168H58.535c-23.848 0-39.746-11.563-51.308-31.074-3.614-5.781-5.059-12.285-6.504-18.79 0-0.722-0.723-2.167-0.723-2.89v-11.562zM0 205.234c0-0.723 0.723-2.168 0.723-2.891 3.613-18.789 13.007-33.242 29.628-42.637 7.227-4.335 15.176-5.78 23.125-6.503H961.13c20.234 0 35.41 8.671 46.973 24.57 8.671 12.285 12.285 25.293 10.84 40.468-2.891 23.125-18.79 43.36-42.637 49.14-6.504 1.446-13.008 2.169-20.234 2.169H58.535c-23.848 0-39.746-11.563-51.308-31.074-3.614-5.782-5.059-12.285-6.504-18.79 0-1.445-0.723-2.89-0.723-3.613v-10.84zM51.308 862.848c-1.445 0-2.168-0.722-3.613-0.722-16.62-3.614-28.183-13.008-36.855-27.461-6.504-10.84-9.395-22.402-8.672-34.688 2.168-24.57 19.512-46.25 44.804-52.03 5.06-1.446 10.84-1.446 16.622-1.446h899.703c19.512 0 34.687 8.672 46.25 23.848 7.226 10.117 11.562 22.402 11.562 34.687 0 14.453-5.058 27.46-14.453 38.3-9.394 10.84-21.68 17.344-36.132 18.79-0.723 0-1.446 0-2.168 0.722H51.308zM1024 189.335c-0.723-2.168-0.723-5.058-1.445-7.226l1.445 7.226z" p-id="8766" fill="#bfbfbf"></path></svg>',
                    name: '待办事项',
                    flag: false,
                    inpflag: true,
                }
            ],
            inpval: '',
        }
    },
    methods: {
        deleteItem(index) {
      this.list.splice(index, 1);
    },
        saveToLocalStorage() {
            localStorage.setItem('listData', JSON.stringify(this.list));
        },
        loadFromLocalStorage() {
            const data = localStorage.getItem('listData');
            if (data) {
                this.list = JSON.parse(data);
            }
        },
        dianjiaaa(arr) {
            console.log(arr);
            this.list.name = arr
        },
        dianji(a,i) {
            // let arr = {
            //     user: 'asd '
            // }
            this.$bus.emit("eventName", a)
            this.$bus.emit("index", i)

        },
        fun(sindex) {
            this.list.forEach((item, index) => {
                if (index == sindex) {
                    item.flag = true
                } else {
                    item.flag = false
                }
            })
        },
        toggleText(sindex) {
            this.list[sindex].inpflag = true
            this.inpval = this.list[sindex].name

        },
        lichange(index) {
            this.list[index].name = this.inpval
            this.list[index].inpflag = false
        },
        addNewList() {
            this.list.push({
                img: '<svg t="1692262794704" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="8765" width="16" height="16"><path d="M0 505.135c0-0.723 0.723-2.168 0.723-2.89 3.613-18.79 13.007-33.243 29.628-42.637 7.227-4.336 15.176-5.782 23.125-6.504H961.13c20.234 0 35.41 8.672 46.973 24.57 8.671 12.285 12.285 25.293 10.84 40.469-2.891 23.124-18.79 43.359-42.637 49.14-6.504 1.445-13.008 2.168-20.234 2.168H58.535c-23.848 0-39.746-11.563-51.308-31.074-3.614-5.781-5.059-12.285-6.504-18.79 0-0.722-0.723-2.167-0.723-2.89v-11.562zM0 205.234c0-0.723 0.723-2.168 0.723-2.891 3.613-18.789 13.007-33.242 29.628-42.637 7.227-4.335 15.176-5.78 23.125-6.503H961.13c20.234 0 35.41 8.671 46.973 24.57 8.671 12.285 12.285 25.293 10.84 40.468-2.891 23.125-18.79 43.36-42.637 49.14-6.504 1.446-13.008 2.169-20.234 2.169H58.535c-23.848 0-39.746-11.563-51.308-31.074-3.614-5.782-5.059-12.285-6.504-18.79 0-1.445-0.723-2.89-0.723-3.613v-10.84zM51.308 862.848c-1.445 0-2.168-0.722-3.613-0.722-16.62-3.614-28.183-13.008-36.855-27.461-6.504-10.84-9.395-22.402-8.672-34.688 2.168-24.57 19.512-46.25 44.804-52.03 5.06-1.446 10.84-1.446 16.622-1.446h899.703c19.512 0 34.687 8.672 46.25 23.848 7.226 10.117 11.562 22.402 11.562 34.687 0 14.453-5.058 27.46-14.453 38.3-9.394 10.84-21.68 17.344-36.132 18.79-0.723 0-1.446 0-2.168 0.722H51.308zM1024 189.335c-0.723-2.168-0.723-5.058-1.445-7.226l1.445 7.226z" p-id="8766" fill="#bfbfbf"></path></svg>',
                name: '待办事项123123',
                flag: false,
                lista:{
                    nameaa:'123123'
                }
            })
            console.log(this.list);
        }
    },
    created() {
        this.loadFromLocalStorage();
    },
    watch: {
        list: {
            handler() {
                this.saveToLocalStorage(); // 监听数据变化，在数据更新时保存到本地存储
            },
            deep: true // 监听数组中每个对象的变化
        }
    }
}
</script>
<style lang="less" scoped>
.li_active {
    background-color: #1890ff1a !important;
}

.u {
    padding-right: 0.5rem;
    padding-left: 0.5rem;
    height: 365px;
    overflow: auto;
}

.u::-webkit-scrollbar {
    width: 0.5em;
    /* 设置滚动条宽度 */
}

.u::-webkit-scrollbar-track {
    background-color: transparent;
    /* 设置滚动条背景颜色 */
}

.u::-webkit-scrollbar-thumb {
    background-color: #888;
    /* 设置滚动条的颜色 */
    border-radius: 10px;
    /* 设置滚动条的圆角 */
}

.xvc {
    content: "";
    border-radius: 3px;
    width: 3px;
    height: 14px;
    color: #1890ff;
    display: inline-block;
}
</style>