<template>
    <footer class="footer_guide border-1px">
        <a
            href="javascript:;"
            class="guide_item"
            :class="{ on: path == '/msite' }"
            @click="goto('/msite')"
        >
            <span class="item_icon">
                <i class="iconfont icon-waimai"></i>
            </span>
            <span>外卖</span>
        </a>
        <a
            href="javascript:;"
            class="guide_item"
            @click="goto('search')"
            :class="{ on: path == '/search' }"
        >
            <span class="item_icon">
                <i class="iconfont icon-search"></i>
            </span>
            <span>搜索</span>
        </a>
        <a
            href="javascript:;"
            class="guide_item"
            @click="goto('order')"
            :class="{ on: path == '/order' }"
        >
            <span class="item_icon">
                <i class="iconfont icon-dingdan"></i>
            </span>
            <span>订单</span>
        </a>
        <a
            href="javascript:;"
            class="guide_item"
            @click="goto('profile')"
            :class="{ on: path == '/profile' }"
        >
            <span class="item_icon">
                <i class="iconfont icon-geren"></i>
            </span>
            <span>我的</span>
        </a>
    </footer>
</template>

<script>
export default {
    data: function () {
        return {
            path: this.$route.path,
        };
    },
    methods: {
        goto: function (uri) {
            this.$router.replace(uri);
        },
    },
    watch: {
        $route: function () {
            // 改变当前路由组件参数数据时自动调用

            this.path = this.$route.path;
        },
    },
};
</script>

<style lang="stylus" rel="stylesheet/stylus">
.footer_guide // footer
    top-border-1px(#e4e4e4)
    position: fixed
    z-index: 100
    left: 0
    right: 0
    bottom: 0
    background-color: #fff
    width: 100%
    height: 50px
    display: flex
    .header
        background-color: #02a774
        position: fixed
        z-index: 100
        left: 0
        top: 0
        width: 100%
        height: 45px
    .header_search
        position: absolute
        left: 15px
        top: 50%
        transform: translateY(-50%)
        width: 10%
        height: 50%
        .icon-sousuo
            font-size: 25px
            color: #fff
    .header_title
        position: absolute
        top: 50%
        left: 50%
        transform: translate(-50%, -50%)
        width: 50%
        color: #fff
        text-align: center
        .header_title_text
            font-size: 20px
            color: #fff
            display: block
    .header_login
        font-size: 14px
        color: #fff
        position: absolute
        right: 15px
        top: 50%
        transform: translateY(-50%)
        .header_login_text
            color: #fff
    .guide_item
        display: flex
        flex: 1
        text-align: center
        flex-direction: column
        align-items: center
        margin: 5px
        color: #999999
        &.on
            color: #02a774
        span
            font-size: 12px
            margin-top: 2px
            margin-bottom: 2px
            .iconfont
                font-size: 22px
</style>
