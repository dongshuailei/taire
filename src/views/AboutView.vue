<template>
    <div class="box" style="position: relative;left: 0;top: 0;">
        <div style="height: 190px;background: #FFFFFF;">
            <div class="home">
                <div class="a">
                    <input type="text" placeholder="search" style="cursor: pointer;" v-model="searchTerm" @keyup="seachFun">
                    <i class="el-icon-search"
                        style="line-height: 30px;color: var(--el-input-icon-color,var(--el-text-color-placeholder));"></i>
                </div>
                <ul class="u">
                    <li @click="abc('a')"
                        :style="num == 'a' ? 'background:#1890ff1a;cursor: pointer; border-radius: 0px;' : 'cursor: pointer; border-radius: 0px;'">
                        <span class="xvc" v-if="num == 'a'"></span>
                        <span style="height: 32px;display: inline-block;">
                            <a style="padding-left: 10px;"></a>
                            &nbsp;
                            <span style="width: 130px;display: inline-block;">所有</span>
                        </span>
                        <span>{{ suoArrList.length }}</span>
                    </li>
                    <li @click="abc('b')"
                        :style="num == 'b' ? 'background:#1890ff1a;cursor: pointer; border-radius: 0px;' : 'cursor: pointer; border-radius: 0px;'">
                        <span class="xvc" v-if="num == 'b'"></span>
                        <span style="height: 32px;display: inline-block;">
                            <a style="padding-left: 10px;"></a>
                            &nbsp;
                            <span style="width: 130px;display: inline-block;">今天</span>
                        </span>
                        <span>{{ suoArrList.length }}</span>
                    </li>
                    <li @click="abc('c')"
                        :style="num == 'c' ? 'background:#1890ff1a;cursor: pointer; border-radius: 0px;' : 'cursor: pointer; border-radius: 0px;'">
                        <span class="xvc" v-if="num == 'c'"></span>
                        <span style="height: 32px;display: inline-block;">
                            <a style="padding-left: 10px;"></a>
                            &nbsp;
                            <span style="width: 130px;display: inline-block;">最近七天</span>
                        </span>
                        <span>{{ suoArrList.length }}</span>
                    </li>
                    <p style="border-color: #E5E5E5;" class="asd bt"></p>
                </ul>
            </div>
            <div class="cccccccccccccc">
                <ul class="u">
                    <li :style="num == index ? 'background:#1890ff1a;cursor: pointer; border-radius: 0px;' : 'cursor: pointer; border-radius: 0px;'"
                        v-for="(item, index) in arrList" :key="item.id" @click="bgFun(index)">
                        <span class="xvc" v-if="num == index"></span>
                        <span style="height: 32px;display: inline-block;">
                            <a style="padding-left: 10px;"></a>
                            &nbsp;
                            <span style="width: 105px;height: 32px;display: inline-block;"> <!-- :disabled="!item.flog" -->
                                <a href="javascript:;" style="color: black;" v-if="!item.flog"
                                    @dblclick="dblclickFun(index)">{{ item.content
                                    }}</a>
                                <input type="text" v-model="item.content" class="ipt" @blur="blurFun(index)" v-else>
                                <!-- <input type="text" style="width: 130px;display: inline-block;height: 20px;border: none;"> -->
                            </span>
                        </span>
                        <span style="cursor: pointer;" class="el-icon-delete" @click="del(index)"></span>
                        <span>{{ item.list.length }}</span>
                    </li>
                </ul>
                &nbsp;
            </div>
            <div
                style="display: flex; width: 190px; height: 11px; align-items: center; padding-bottom: .75rem;padding-left: 10px;background: #FFFFFF;">
                <i class="el-icon-plus"></i>
                &nbsp;
                <span style="font-size: 16px; cursor: pointer;" @click="addlist">新建列表</span>
            </div>
        </div>
        <div class="aaaaaaaaaaaa">
            <h2 style="display: flex;align-items: center;justify-content: space-between;width: 680px;height: 26px;">
                {{ title }}
                <el-dropdown>
                    <span class="el-dropdown-link">
                        <i class="el-icon-more"></i>
                    </span>
                    <el-dropdown-menu slot="dropdown">
                        <el-dropdown-item command="a">隐藏已完成</el-dropdown-item>
                        <el-dropdown-item command="b">清理已完成</el-dropdown-item>
                    </el-dropdown-menu>
                </el-dropdown>
            </h2>
            <ul style="width: 760px;height: 495px;margin-top: 12px;overflow-y: scroll;">
                <li class="li" v-for="(item, index) in  typeof (num) == 'number' ? sonArrList : suoArrList" :key="index">
                    <input type="Checkbox" :checked="item.flog" style="width: 16px;height: 16px;margin-top: 10px;">
                    <span style="font-size: 16px;height: 20px;margin-left: 10px;"></span>
                    <div style="width: 614px;height: 55px;">
                        <span
                            style="min-height: 21px;height: 21px !important;font-size: 14px;display: block;padding: 5px 11px;line-height: 1.5;width: 97%;border: none;border-radius: var(--el-input-border-radius,var(--el-border-radius-base));color: var(--el-input-text-color,var(--el-text-color-regular));">
                            {{ item.content }}
                        </span>
                        <div class="block">
                            <el-date-picker v-model="item.data" type="date" placeholder="-">
                            </el-date-picker>
                        </div>
                    </div>
                    <div>
                        <i class="el-icon-more"></i>
                        <i class="el-icon-delete" @click="shanchu(index)"></i>
                    </div>
                </li>
            </ul>
            <div
                style="bottom: 16px;background-color: #fff;border-radius: 6px;box-shadow: 0 -6px 4px #0000000a;width: 700px;height: 45px;position: relative;top: 5px;display: flex;align-items: center;justify-content: center;">
                <i class="el-icon-plus"></i>
                &nbsp;
                <input type="text"
                    style="outline: none;border: none;background-color: transparent;font-family: inherit;-webkit-user-select: auto;width: 660px;height: 45px;position: relative;top: 0px;"
                    placeholder="添加任务" @keyup.enter="addSonList" v-model="inputVal">
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            searchTerm: '',
            inputVal: '',
            title: '',
            arrList: [],
            num: 0,
            sonArrList: [
            ],
            suoArrList: []
        }

    },
    created() {
        this.render()
        this.xuanran()
        this.getLength()
    },
    methods: {
        seachFun() {
            if (this.searchTerm !== '') {
                this.num = 'a'
                this.title = '所有'
            }
            let arrList = localStorage.getItem('arrList')
            arrList = JSON.parse(arrList)
            this.suoArrList = []
            let res = []
            arrList.forEach((item) => {
                res = [...res, ...item.list]
            })
            res = res.filter((item) => {
                return item.content.includes(this.searchTerm)
            })
            this.suoArrList = res

        },
        shanchu(index) {
            let arrList = localStorage.getItem('arrList')
            arrList = JSON.parse(arrList)
            arrList[this.num].list.splice(index, 1)
            this.sonArrList.splice(index, 1)
            localStorage.setItem('arrList', JSON.stringify(arrList))
        },
        getLength() {
            this.suoArrList = []
            let res = []
            let arrList = localStorage.getItem('arrList')
            arrList = JSON.parse(arrList)
            arrList.forEach((item) => {
                res = [...res, ...item.list]
            })
            this.suoArrList = res
            console.log(this.suoArrList);
        },
        bgFun(index) {
            this.num = index
            this.xuanran()
        },
        xuanran() {
            let arrList = localStorage.getItem('arrList')
            arrList = JSON.parse(arrList)
            this.title = arrList[this.num].content
            this.sonArrList = arrList[this.num].list
        },
        render() {
            let arrList = localStorage.getItem('arrList')
            arrList = JSON.parse(arrList)
            this.arrList = arrList
        },
        addlist() {
            let arrList = localStorage.getItem('arrList')
            arrList = JSON.parse(arrList)
            if (arrList == null || arrList == '') {
                arrList = [{
                    id: 1,
                    content: "待办事项",
                    flog: false,
                    num: 0,
                    list: []
                }]
            } else {
                arrList.push({
                    id: arrList[arrList.length - 1].id + 1,
                    content: "待办事项",
                    flog: false,
                    num: 0,
                    list: []
                })

            }
            localStorage.setItem('arrList', JSON.stringify(arrList))
            this.render()
        },
        dblclickFun(index) {
            // console.log(this.arrList);
            this.arrList[index].flog = !this.arrList[index].flog;
            // localStorage.setItem('arrList', JSON.stringify(this.arrList))
            // this.render()
            // console.log(index);
        },
        blurFun(index) {
            this.arrList[index].flog = !this.arrList[index].flog;
            localStorage.setItem('arrList', JSON.stringify(this.arrList))
            this.xuanran()
            this.render()
        },
        del(index) {
            console.log(111);
            this.arrList.splice(index, 1)
            localStorage.setItem('arrList', JSON.stringify(this.arrList))
            this.num = 0
            this.render()
            this.xuanran()
        },
        abc(n) {
            this.num = n;
            this.title = n == 'a' ? '所有' : n == 'b' ? '今天' : n == 'c' ? '最近七天' : this.title;
            let arrList = localStorage.getItem('arrList')
            arrList = JSON.parse(arrList)
            this.suoArrList = []

            let res = []
            arrList.forEach((item) => {
                res = [...res, ...item.list]
            })
            this.suoArrList = res
        },
        addSonList() {
            if (this.inputVal == '') {
                return
            }
            let arrList = localStorage.getItem('arrList')
            arrList = JSON.parse(arrList)
            if (this.num == 'a' || this.num == 'b' || this.num == 'c') {
                return
            }
            arrList[this.num].list.push({
                content: this.inputVal,
                data: '2023-8-20',
                flog: false
            })
            localStorage.setItem('arrList', JSON.stringify(arrList))
            this.render()
            this.xuanran()
            this.getLength()
            this.inputVal = ''
        }
    },

}
</script>

<style lang="less" scoped>
.ipt {
    width: 108px !important;
    height: 22px !important;
    border-radius: 3px;
    border: 1px solid #ccc;
}

.xvc {
    content: "";
    border-radius: 3px;
    width: 3px;
    height: 14px;
    background-color: #1890ff;
    display: inline-block;
}

.u li:hover {
    background-color: #1890ff1a;
}

.bt {
    border-top: 1px solid #f2f2f2;
}

.asd {
    padding-bottom: .25rem;
    margin-top: .25rem;
}

.u li {
    margin: 2px 0;
    border-radius: 8px;
    color: rgba(var(--alpha-color), .7);
    line-height: 32px;
    height: 32px;
    font-size: 14px;
}

.u {
    width: 184px;
    height: 120px !important;
    padding-top: 4px;
}

.el-icon-search {
    line-height: 30px;
}

.sou {
    background-color: var(--bg-info);
    width: 800px;
    height: 600px;
}

.a {
    height: 30px;
    width: 162px;
}

.a input {
    width: 140px;
    height: 30px;
    border-radius: 6px;
    border: none;
    background: #F0F1F4;

}

.a {
    background: #F0F1F4;
    padding: 1px 11px;
    border-radius: 6px;
    display: flex;
}

.box {
    width: 1000px;
    height: 600px;
    display: flex;
    background: var(--bg-card);
    margin: auto;
    margin-top: 100px;
    display: flex;
}

.home {
    width: 184px;
    height: 570px;
    padding-top: 30px;
    padding-right: .5rem;
    padding-left: .5rem;
    background: #FFFFFF;
}

.box {
    background: #F5F5F5;
    box-shadow: 0 12px 32px #0000007a;
}

.block {
    position: relative;
}

::v-deep .el-date-editor {
    position: absolute;
    top: -10px;
}

::v-deep .el-input__inner {
    border: none !important;
    height: 30px !important;

}

.el-date-editor {
    width: 220px;
    border: none;
}

.el-icon-more {
    font-size: 12px;
}

.el-icon-delete {
    font-size: 12px;
    margin-right: 10px;
    margin-left: 10px;
}

.li {
    background-color: #fff;
    margin-bottom: 10px;
    border-radius: 6px;
    padding-left: 10px;
    display: flex;
    line-height: 40px;
    padding-bottom: 2px;
    width: 725px;
    height: 58px;

}

.cccc {
    padding: 10px 20px 0;
    font-weight: 700;
    font-size: 20px;
}

.el-dropdown-link {
    cursor: pointer;
    color: #409EFF;
}

.el-icon-arrow-down {
    font-size: 12px;
}

.aaaaaaaaaaaa {
    width: 760px;
    height: 590px;
    padding: 10px 20px 0;
}

.cccccccccccccc {
    width: 184px;
    height: 390px;
    padding-right: .5rem;
    padding-left: .5rem;
    background: #FFFFFF;
}

.li_active {
    background-color: #1890ff1a !important;
}

.u {
    padding-right: 0.5rem;
    padding-left: 0.5rem;
    height: 365px !important;
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

.xvc {
    content: "";
    border-radius: 3px;
    width: 3px;
    height: 14px;
    color: #1890ff;
    display: inline-block;
}

.li_active {
    background-color: #1890ff1a !important;
}

.u li:hover {
    background-color: #1890ff1a;
}

.bt {
    border-top: 1px solid #f2f2f2;
}

.asd {
    padding-bottom: .25rem;
    margin-top: .25rem;
}

.u li {
    margin: 2px -8px;
    border-radius: 8px;
    color: rgba(var(--alpha-color), .7);
    line-height: 32px;
    height: 32px;
    font-size: 14px;
    cursor: pointer;
    width: 185px;
}

.u {
    width: 184px;
    height: 120px;
    padding-top: 4px;
}

.el-icon-search {
    line-height: 30px;
}

.sou {
    background-color: var(--bg-info);
    width: 800px;
    height: 600px;
}

.a {
    height: 30px;
    width: 162px;
}

.a input {
    width: 140px;
    height: 30px;
    border-radius: 6px;
    border: none;
    background: #F0F1F4;

}

.a {
    background: #F0F1F4;
    padding: 1px 11px;
    border-radius: 6px;
    display: flex;
}

.box {
    width: 1000px;
    height: 600px;
    display: flex;
    background: #F5F5F5;
    margin: auto;
    margin-top: 100px;
}

.home {
    width: 184px;
    height: 155px;
    padding-top: 30px;
    padding-right: .5rem;
    padding-left: .5rem;

}
</style>