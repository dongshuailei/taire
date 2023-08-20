<template>
    <div style="height: 190px;">
        <div class="home">
            <div class="a">
                <input type="text" placeholder="search" style="cursor: pointer;">
                <i class="el-icon-search"
                    style="line-height: 30px;color: var(--el-input-icon-color,var(--el-text-color-placeholder));"></i>
            </div>
            <ul class="u">
                <li :class="item.flag?'li_active':''" v-for="(item, index) in list" :key="index" @click="fun(index)">
                    <span class="xvc" v-show="item.flag"></span>
                    <span style="height: 32px;display: inline-block;">
                        <a v-html="item.img" style="padding-left: 10px;"></a>
                        &nbsp;
                        <span style="width: 130px;display: inline-block;" @click="addname(item.name)">{{ item.name }}</span>
                    </span>
                    <span>{{ 0 }}</span>
                </li>
                <p style="border-color: #E5E5E5;" class="asd bt"></p>
            </ul>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            list: [
                {
                    img:'<svg t="1692261682903" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="4062" width="16" height="16"><path d="M483.34848 495.77984H155.56608V168.01792H483.328v327.76192z m-276.25472-51.52768h224.70656V219.5456H207.09376v224.70656zM878.3872 495.77984H550.6048V168.01792H878.3872v327.76192zM602.112 444.25216h224.72704V219.5456H602.112v224.70656zM484.06528 886.51776H156.28288V558.75584h327.76192v327.76192z m-276.25472-51.52768H432.5376V610.28352H207.81056v224.70656zM879.104 886.51776H551.3216V558.75584h327.7824v327.76192z m-276.25472-51.52768h224.72704V610.28352H602.84928v224.70656z" p-id="4063" fill="#bfbfbf"></path></svg>',
                    name: '所有',
                    flag:true
                },
                {
                    img:'<svg t="1692261720153" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="5391" width="16" height="16"><path d="M832 128h-64V64h-64v64H320V64h-64v64h-64a64.19 64.19 0 0 0-64 64v640a64.19 64.19 0 0 0 64 64h640a64.19 64.19 0 0 0 64-64V192a64.19 64.19 0 0 0-64-64z m0 704H192V256h640z" fill="#bfbfbf" p-id="5392"></path><path d="M256 320h224v192H256z" fill="#bfbfbf" p-id="5393"></path></svg>',
                    name: '今天',
                    flag:false
                },
                {
                    img:'<svg t="1692261755850" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="7470" width="16" height="16"><path d="M827.076923 0H196.923077a131.282051 131.282051 0 0 0-131.282051 131.282051v761.435898a131.282051 131.282051 0 0 0 131.282051 131.282051h212.676923a26.25641 26.25641 0 0 0 26.25641-26.25641 26.25641 26.25641 0 0 0-26.25641-26.256411H196.923077a78.769231 78.769231 0 0 1-78.769231-78.76923V131.282051a78.769231 78.769231 0 0 1 78.769231-78.76923h630.153846a78.769231 78.769231 0 0 1 78.769231 78.76923v341.333334a26.25641 26.25641 0 0 0 26.25641 26.25641 26.25641 26.25641 0 0 0 26.25641-26.25641V131.282051a131.282051 131.282051 0 0 0-131.282051-131.282051z" fill="#bfbfbf" p-id="7471"></path><path d="M748.307692 1024a210.051282 210.051282 0 1 1 210.051282-210.051282 210.051282 210.051282 0 0 1-210.051282 210.051282z m0-378.092308a168.041026 168.041026 0 1 0 168.041026 168.041026 168.30359 168.30359 0 0 0-168.041026-168.041026z" fill="#bfbfbf" p-id="7472"></path><path d="M708.923077 720.475897m21.005128 0l0 0q21.005128 0 21.005128 21.005129l0 115.528205q0 21.005128-21.005128 21.005128l0 0q-21.005128 0-21.005128-21.005128l0-115.528205q0-21.005128 21.005128-21.005129Z" fill="#bfbfbf" p-id="7473"></path><path d="M840.205128 836.004103m0 21.005128l0 0q0 21.005128-21.005128 21.005128l-89.271795 0q-21.005128 0-21.005128-21.005128l0 0q0-21.005128 21.005128-21.005128l89.271795 0q21.005128 0 21.005128 21.005128Z" fill="#bfbfbf" p-id="7474"></path><path d="M501.092375 337.654373m-18.566086-18.566086l0 0q-18.566086-18.566086 0-37.132172l148.528686-148.528686q18.566086-18.566086 37.132172 0l0 0q18.566086 18.566086 0 37.132172l-148.528686 148.528686q-18.566086 18.566086-37.132172 0Z" fill="#bfbfbf" p-id="7475"></path><path d="M538.43472 300.498028m-18.566086 18.566085l0 0q-18.566086 18.566086-37.132171 0l-74.264343-74.264343q-18.566086-18.566086 0-37.132171l0 0q18.566086-18.566086 37.132171 0l74.264343 74.264343q18.566086 18.566086 0 37.132171Z" fill="#bfbfbf" p-id="7476"></path><path d="M249.435897 431.655385m26.256411 0l525.128205 0q26.25641 0 26.25641 26.25641l0 0q0 26.25641-26.25641 26.25641l-525.128205 0q-26.25641 0-26.256411-26.25641l0 0q0-26.25641 26.256411-26.25641Z" fill="#bfbfbf" p-id="7477"></path><path d="M249.435897 589.193846m26.256411 0l262.564102 0q26.25641 0 26.256411 26.25641l0 0q0 26.25641-26.256411 26.256411l-262.564102 0q-26.25641 0-26.256411-26.256411l0 0q0-26.25641 26.256411-26.25641Z" fill="#bfbfbf" p-id="7478"></path><path d="M249.435897 746.732308m26.256411 0l131.282051 0q26.25641 0 26.25641 26.25641l0 0q0 26.25641-26.25641 26.25641l-131.282051 0q-26.25641 0-26.256411-26.25641l0 0q0-26.25641 26.256411-26.25641Z" fill="#bfbfbf" p-id="7479"></path></svg>',
                    name: '最近七天',
                    flag:false
                }
            ]
        }
    },
    methods:{
        addname(a){
            this.$bus.emit("eventName",a)
        },
        fun(sindex){
            this.list.forEach((item,index)=>{
                if(index==sindex){
                    item.flag=true
                }else{
                    item.flag=false
                }
            })
        },
        addNewList(){
            this.list1.push({
                img: '<svg t="1692262794704" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="8765" width="16" height="16"><path d="M0 505.135c0-0.723 0.723-2.168 0.723-2.89 3.613-18.79 13.007-33.243 29.628-42.637 7.227-4.336 15.176-5.782 23.125-6.504H961.13c20.234 0 35.41 8.672 46.973 24.57 8.671 12.285 12.285 25.293 10.84 40.469-2.891 23.124-18.79 43.359-42.637 49.14-6.504 1.445-13.008 2.168-20.234 2.168H58.535c-23.848 0-39.746-11.563-51.308-31.074-3.614-5.781-5.059-12.285-6.504-18.79 0-0.722-0.723-2.167-0.723-2.89v-11.562zM0 205.234c0-0.723 0.723-2.168 0.723-2.891 3.613-18.789 13.007-33.242 29.628-42.637 7.227-4.335 15.176-5.78 23.125-6.503H961.13c20.234 0 35.41 8.671 46.973 24.57 8.671 12.285 12.285 25.293 10.84 40.468-2.891 23.125-18.79 43.36-42.637 49.14-6.504 1.446-13.008 2.169-20.234 2.169H58.535c-23.848 0-39.746-11.563-51.308-31.074-3.614-5.782-5.059-12.285-6.504-18.79 0-1.445-0.723-2.89-0.723-3.613v-10.84zM51.308 862.848c-1.445 0-2.168-0.722-3.613-0.722-16.62-3.614-28.183-13.008-36.855-27.461-6.504-10.84-9.395-22.402-8.672-34.688 2.168-24.57 19.512-46.25 44.804-52.03 5.06-1.446 10.84-1.446 16.622-1.446h899.703c19.512 0 34.687 8.672 46.25 23.848 7.226 10.117 11.562 22.402 11.562 34.687 0 14.453-5.058 27.46-14.453 38.3-9.394 10.84-21.68 17.344-36.132 18.79-0.723 0-1.446 0-2.168 0.722H51.308zM1024 189.335c-0.723-2.168-0.723-5.058-1.445-7.226l1.445 7.226z" p-id="8766" fill="#bfbfbf"></path></svg>',
                name: '待办事项',
                flag:false
            })
        }
    },
    components:{
        
    }
}
</script>
<style lang="less" scoped>
.xvc {
    content: "";
    border-radius: 3px;
    width: 3px;
    height: 14px;
    color: #1890ff;
    display: inline-block;
}
.li_active{
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
    margin: 2px 0;
    border-radius: 8px;
    color: rgba(var(--alpha-color), .7);
    line-height: 32px;
    height: 32px;
    font-size: 14px;
    cursor: pointer;
}

.u {
    width: 184px;
    height: 503px;
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
}

.home {
    width: 184px;
    height: 570px;
    padding-top: 30px;
    padding-right: .5rem;
    padding-left: .5rem;

}
</style>