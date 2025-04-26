<!--
 * @Description: 
 * @Author: Rabbiter
 * @Date: 2023-02-21 18:13:21
-->
<!--
 * @Description: 
 * @Author: Rabbiter
 * @Date: 2023-02-21 18:13:21
-->
<template>
    <div class="dashboard-container">
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
                欢迎使用图书分享系统
            </i>
            <hr />

            <img :src="require('@/assets/index.jpg')" style="width: 78%" />
        </div>
    </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
    name: "Dashboard",
    computed: {
        ...mapGetters(["id", "name", "roles"]),
    },
};
</script>
