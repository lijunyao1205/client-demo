<template>
   <div>
       <!--home -->
       <van-list
            v-model="loading"
            :finished="finished"
            finished-text="没有更多了"
            @load="onLoad"
            >
            <van-cell v-for="item in list" :key="item.id" @click="handleClick(item.id)">
                <div class="list">
                    <div class="left">
                        <img :src="item.img" alt="文章图片">
                    </div>
                    <div class="right">
                        <div class="title">{{item.title}}</div>
                        <div class="create-time">{{item.createTime}}</div>
                    </div>                    
                </div>
            </van-cell>
        </van-list>
   </div>
</template>
<script>
import { List, Cell} from 'vant'
export default {
    components:{
        [List.name]:List,
        [Cell.name]:Cell
    },
    data(){
        return {
            'loading': false,
            'finished': false,
            'list': []
        }
    },
    methods:{
        onLoad:function(){
            //用延时模拟异步请求
            setTimeout(()=>{
                this.loading  = false;
                this.finished =  true;
                this.list = [
                    {
                        id: 1,
                        title: '我是标题',
                        summary: '我是简介',
                        content: '我是内容',
                        img: 'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=2078964100,2396713781&fm=26&gp=0.jpg' ,
                        createTime:'2020-08-10 22:11:22'
                    }
                ];
            },1000);
        },
        handleClick:function(id){
            this.$router.push({
                path: '/detail',
                query: {
                    id
                }
            });
        }
    }
}
</script>
<style scoped>
    .list{
        display: flex;
        flex-direction: row;
        margin: 0 auto;
        /* padding: 2px 2px; */
    }
    .list .left img{
        width:150px;
        height: 100px;
        border-radius: 10px;
    }
    .list .right{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        margin-left: 15px;
    }
    .list .right .title{
        font-size: 18px;        
    }
    .list .right .createTime{
        font-size: 15px;
        color: #9e9e9e;
    }
    
</style>