<template>
   <div>
       <!-- detail -->
       <div class="detail">
           <div class="title">{{detail.title}}</div>
           <div class="summary">{{detail.summary}}</div>
           <div class="content">{{detail.content}}</div>
           <div class="create-time">{{detail.createTime}}</div>
       </div>
   </div>
</template>
<script>
export default {
    data(){
        return {
            detail: {
                id: 1,
                title: '我是标题',
                summary: '我是简介',
                content: '我是内容',
                img: 'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=2078964100,2396713781&fm=26&gp=0.jpg' ,
                createTime:'2020-08-10 22:11:22'
            }
        }
    }
}
</script>
<style scoped>
    .detail{
        padding: 20px;
        text-align: left;
    }
    .detail .title{
        font-size: 25px;
        padding-bottom: 20px;
    }
    .detail .summary{
        padding: 20px;
        background: #dcdcdc;
    }
    .detail .content{
        text-indent: 2em;
        line-height: 200%;
        padding: 20px;
    }
    .detail .create-time{
        color: #9c9c9c;
        text-align: right;
    }
</style>