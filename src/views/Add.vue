<template>
   <div>
       <!-- add -->
       <van-uploader
        :max-count="1"
        v-model="fileList"
        :after-read="afterRead"/>
        <van-cell-group>
            <van-field v-model="title" label="标题" type="text" placeholder="请输入标题"/>
            <van-field v-model="summary" label="简介" type="text" placeholder="请输入简介"/>
            <van-field v-model="content" label="内容" type="textarea" placeholder="请输入内容" rows="3" autosize/>            
        </van-cell-group>
        <van-button @click="handleAdd" type="primary" class="add-button">提交</van-button>
   </div>
</template>
<script>
import { Uploader, CellGroup, Field, Button } from 'vant'
export default {
    components:{
        [Uploader.name]:Uploader,
        [CellGroup.name]:CellGroup,
        [Field.name]:Field,
        [Button.name]:Button
    },
    data(){
        return {
            "fileList":[],
            "title":'',
            "summary":'',
            "content":'',
            "img":''
        }
    },
    methods:{
        afterRead:function(info){
            //console.log(info);
            this.img = info.content;//赋值文件内容
        },
        handleAdd:function(){
            //组装数据信息
            const data = {
                title: this.title,
                summary: this.summary,
                content: this.content,
                img: this.img
            };
            console.log(JSON.stringify(data))

        }
    }
}
</script>
<style scoped>
    .add-button{
        position: absolute;
        left: 0px;
        bottom:80px;
        width:100%;
    }
</style>