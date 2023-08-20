<template>
    <div class="cccc">
        <h2 style="display: flex;align-items: center;justify-content: space-between;width: 680px;height: 26px;">{{ list }}
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
        <ul style="width: 760px;height: 520px;margin-top: 12px;">
            <li class="li" v-for="(item, index) in lisasdt" :key="index">
                <input type="Checkbox" v-model="item.type" style="width: 16px;height: 16px;margin-top: 10px;">
                <div style="width: 684px;height: 55px;">
                    <span
                        style="min-height: 21px;height: 21px !important;font-size: 14px;display: block;padding: 5px 11px;line-height: 1.5;width: 97%;border: none;border-radius: var(--el-input-border-radius,var(--el-border-radius-base));color: var(--el-input-text-color,var(--el-text-color-regular));">{{ item.name }}</span>
                    <div class="block">
                        <el-date-picker v-model="item.data" type="date" placeholder="选择日期">
                        </el-date-picker>
                    </div>
                </div>
                <div>
                    <i class="el-icon-more"></i>
                    <i class="el-icon-delete"></i>
                </div>
            </li>
            <li v-for="(item, index) in lisasdt" :key="index">{{ item.paa }}</li>
        </ul>
        <div style="bottom: 16px;background-color: #fff;border-radius: 6px;box-shadow: 0 -6px 4px #0000000a;width: 700px;height: 45px;position: relative;top: -28px;display: flex;align-items: center;">
            <i class="el-icon-plus"></i>
            &nbsp;
            <input type="text" style="outline: none;border: none;background-color: transparent;font-family: inherit;-webkit-user-select: auto;width: 660px;height: 45px;position: relative;top: 0px;" v-model="inouta" @change="inputaa()">
        </div>
    </div>
</template>
<script>
export default {
    props: [
        'dianji'
    ],
    data() {
        return {
            inouta: '',
            list: '',
            value1: '',
            ind: null,
            lisasdt: [
                {
                    name: '12312',
                    data: '2020-01-01',
                    type: false,
                    paa: '123123',
                }
            ],
            asdaa: ['asdasd', 'asdasd']
        }
    },
    mounted() {
        this.$bus.on("eventName", (data) => {
            this.list = data
        })
        // index
        this.$bus.on("index", (data) => {
            this.ind = data
            // this.list = data
        })
    },
    methods: {
        inputaa() {
            // this.list=this.inouta;
            console.log(this.ind);
            // this.asdaa[this.ind].push(this.inouta)
            console.log(this.inouta);
        }
    },
}
</script>
<style lang="less" scoped>
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
    width: 760px;
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
</style>