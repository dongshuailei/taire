<template>
    <div class="aaaaaaaaaaaa">
        <h2 style="display: flex;align-items: center;justify-content: space-between;width: 680px;height: 26px;">{{ lisasdt.name ? lisasdt.name : '' }}
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
            <!-- {{lisasdt.list}} -->
            <li class="li" v-for="(item, index) in lisasdt.list" :key="index">
                <input type="Checkbox" v-model="item.type" style="width: 16px;height: 16px;margin-top: 10px;">
                <div style="width: 664px;height: 55px;">
                    <span
                        style="min-height: 21px;height: 21px !important;font-size: 14px;display: block;padding: 5px 11px;line-height: 1.5;width: 97%;border: none;border-radius: var(--el-input-border-radius,var(--el-border-radius-base));color: var(--el-input-text-color,var(--el-text-color-regular));">{{ item.content }}</span>
                    <div class="block">
                        <el-date-picker v-model="item.data" type="date" placeholder="-">
                        </el-date-picker>
                    </div>
                </div>
                <div>
                    <i class="el-icon-more"></i>
                    <i class="el-icon-delete"></i>
                </div>
            </li>
            
        </ul>
        <div style="bottom: 16px;background-color: #fff;border-radius: 6px;box-shadow: 0 -6px 4px #0000000a;width: 700px;height: 45px;position: relative;top: 5px;display: flex;align-items: center;justify-content: center;">
            <i class="el-icon-plus"></i>
            &nbsp;
            <input type="text" style="outline: none;border: none;background-color: transparent;font-family: inherit;-webkit-user-select: auto;width: 660px;height: 45px;position: relative;top: 0px;" v-model="inouta" @keyup.enter="inputaa()" placeholder="添加任务">
        </div>
    </div>
</template>
<script>
export default{
    data(){
        return{
            lisasdt: {
                flag: false,
                name:'',
                list:[{
                    content:'阿拉蕾',
                    data:'',
                }]
            },
            inouta: '',
        }
    },
    props:['num'],
    created(){
     this.getList()

    },
    methods:{
        getList(n){
            let user= localStorage.getItem('user')
            if(user=='' || user==null){
                return false
            }
            let data= JSON.parse(user)[n?n:0]
            this.lisasdt=data
            //  console.log(this.lisasdt,123);
            //  console.log(this.num,123);
        },
        inputaa(){
            let user= localStorage.getItem('user')
            let data= JSON.parse(user)
            console.log(data);
            data[this.num].list.push({
                content:this.inouta,
                data:'',
                type:false
            })
            localStorage.setItem('user',JSON.stringify(data))
            // console.log(this.num,123);
            this.getList(this.num)
            this.inouta=''
        //    console.log(111);
        }
    },
    watch:{
        num:{
        deep:true,//true为进行深度监听,false为不进行深度监听
       handler(newVal){
          this.getList(newVal)
        // console.log(newVal);

     } }

    }
}   
</script>
<style lang="less" scoped>
.block{
    position: relative;
}
::v-deep .el-date-editor {
    position: absolute;
    top: -10px;
}
::v-deep .el-input__inner{
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
    width: 735px;
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
.aaaaaaaaaaaa{
    width: 760px;
    height: 590px;
    padding: 10px 20px 0;
}
</style>