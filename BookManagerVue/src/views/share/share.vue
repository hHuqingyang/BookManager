<template>
    <div>
        <!--头部-->
        <header >
            <div
            title="欢迎页面"
            style="
                padding: 50px;
                overflow: hidden;
                color: #409eff;
                font: lighter 16px 'Lucida Sans Unicode';
            "
            data-options="iconCls:'icon-heart',plain:true"
        >
            <i  style="font-size: 32px; font-weight: 600; color: black;">
                欢迎来到图书讨论板块
            </i>
            <hr />

        </div>
            
        </header>

        <!--主体部分-->
        <!--bootstrap将页面分为12格，此处拆分为左4格，右8格-->
        <div class="container">
            <!--使用各组件-->
            <Comment :addComment="addComment"></Comment>
            <!--需使用v-bind绑定属性-->
            <Comments :contents="contents" :deleteComment="deleteComment"></Comments>
        </div>
    </div>
    <!--App -->
</template>

<script>
    // 引入各组件
    import Comment from '../../components/Comment.vue'
    import Comments from '../../components/Comments.vue'

    export default {
        name: 'app',
        // 注册各组件
        components: {
            Comment,
            Comments
        },

        // 传递数据
        data(){
            return {
                contents:[
                    {name: '李明', content: '《西游记》是一本有趣的书，值得观看'},
                    {name: '赵信', content: '《三体》是我看过最好的科幻小说'},
                    {name: '张良', content: '《活着》中老富贵的经历让人不禁落泪'},
                    {name: '洋子', content: '我很喜欢《少女的港湾》描写的校园生活氛围'},
                ]
            }
        },

        // 操作数据的方法
        methods: {
            addComment(comment){
                // 在数组头部插入数据
                this.contents.unshift(comment);
            },
            deleteComment(index){
                // 删除指定下标的数据
                this.contents.splice(index, 1);
            }
        }
    }
</script>

<style>
</style>