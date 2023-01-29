<template>
    <div class="article-container">
        <div class="header-box">
            <slot name="title"></slot>
        </div>
        <div class="content-box">
            <slot name="content" msg="hello vue.js" :user="userinfo"></slot>
        </div> 
        <div class="footer-box">
            <slot name="author"></slot>
        </div>



    </div>
</template>

<script>
export default {
    components: {},
    props: {},
    data() {
        return {
            userinfo: {
                uname: 'zs',
                age:20,
            }
        };
    },
    watch: {},
    computed: {},
    methods: {},
    created() { },
    mounted() { }
};
</script>
<style lang="less" scoped>
.header-box {
    background-color: pink;
    text-align: center;
}

.content-box {
    background-color: yellow;
}

.footer-box {
    background-color: green;
}
</style>