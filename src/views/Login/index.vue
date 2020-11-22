<template>
    <div id="login">
        <div class="login-wrap">
            <ul class="menu-tab">
                <li :class="{'current':item.current}"  v-for="item in menuTab"  :key="item.id" @click="toggleMenu(item)">{{item.txt}}</li>
            </ul><!-- item.id如果没有,会自动生成-->
        </div>
    </div>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    name:'login',
    data(){
        return {
            menuTab:[
                {txt:'登录',current:false},
                {txt:'注册',current:false}
            ]
        }
    },
    created(){},
    mounted(){},
    methods:{
        //数据驱动试图渲染
        //传统的是js直接操作dom元素
        toggleMenu(data){
            this.menuTab.forEach((element,index) => {
                element.current=false;
            });
            data.current=true;
        }
    }
})
</script>
<style lang="scss" scoped>
#login{
    height: 100vh;
    background-color: #344a5f;
}
.login-wrap {
    width: 300px;
    margin: auto;
}
.menu-tab {
    text-align: center;
    li {
        display: inline-block;
        width: 80px;
        height: 36px;
        font-size: 14px;
        color: #fff;
        border-radius: 2px;
        cursor: pointer;
    }
    .current{
        background-color: rgba(0, 0, 0, .1);
    }
}
</style>