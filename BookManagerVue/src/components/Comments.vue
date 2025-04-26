<template>
    <div class="col-md-8">
        <h3 class="reply">大家的回复：</h3>
        <h3 v-show="contents.length === 0">暂无回复，点击左侧提交！！！</h3>
        <ul class="list-group">
            <Item v-for="(content, index) in contents" :key="index" :content="content" :deleteComment="deleteComment" :index="index"></Item>
        </ul>
    </div>
    <!--md8 for List end -->
</template>

<script>
    import Item from './Item.vue'

    export default {
        name: 'comments',
        // 声明接收属性，此属性可以在该组件中使用
        props: ['contents', 'deleteComment'], // 只指定属性名

        // 注册组件
        components: {
            Item
        }
    }
</script>

<style>

</style>
