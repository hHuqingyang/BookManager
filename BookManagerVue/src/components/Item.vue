<template>
    <!--注意，需要使用div包裹，否则会报错-->
    <div>
        <li class="list-group-item">
            <div class="handle col-sm-offset-2 col-sm-10">
                <a class="pull-right" @click="deleteItem">删除</a>
            </div>
            <p class="user"><span style="font-size: 18px;">{{content.name}}</span><span style="font-size: 18px;">说:</span>{{content.content}}</p>
        </li>
    </div>
</template>

<script>
    export default{
        name: 'item',
        props: {
            // 指定属性名以及属性值的类型
            content : Object,
            deleteComment : Function,
            index : Number
         },
         methods: {
             deleteItem() {
                 const {content, deleteComment, index} = this;
                 // 使用  反引号 + ${}， ES6模板字符串
                 if(window.confirm(`确定删除${content.name}的评论吗？`)){
                     deleteComment(index);
                 }
             }
         }
    }
</script>

<style>

</style>