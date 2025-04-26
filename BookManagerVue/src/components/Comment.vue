<template>
    <div class="col-md-4">
        <form action="form-horizontal">
            <div class="form-group">
                <label>用户名</label>
                <input type="text" class="form-control" placeholder="用户名" v-model="name">
            </div>
            <div class="form-group">
                <label>分享内容</label>
                <textarea type="text" class="form-control" placeholder="分享内容" v-model="content"></textarea>
            </div>
            <div class="form-group">
                <div class="col-sm-offset-2 col-sm-10">
                    <el-button v-waves class="filter-item" style="font-size: 20px" type="primary" @click="add">提交</el-button>
                    
                </div>
            </div>
        </form>
    </div>
    <!--Comment -->
</template>

<script>
    export default{
        name: 'comment',
        data(){
            return {
                name : '',
                content : ''
            }
        },
        props:{
            // 定义属性类型、属性值类型、必须性
            addComment: {
                type: Function,
                required: true
            }
        },
        methods: {
            add(){
                // step1：进行合法性检验
                const name = this.name.trim();
                const content = this.content.trim();
                if(!name || !content){
                    alert("输入内容不能为空");
                    return;
                }

                // step2：将name,content封装成一个comment（吐槽）对象
                const comment = {name, content};

                console.log(comment);
                // step3: 将comment 加入到 comments（吐槽区）
                this.addComment(comment);

                // step4：清空输入框
                this.name = '';
                this.content = '';
            }
        }
    }
</script>

<style>

</style>