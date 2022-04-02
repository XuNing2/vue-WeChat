<template>
    <!--公众号组件-->
    <div :class="{'search-open-contact':!$store.state.headerStatus}" class="official-account">
        <header id="wx-header">
            <div class="center">
                <router-link to="/contact" tag="div" class="iconfont icon-return-arrow">
                    <span>通讯录</span>
                </router-link>
                <span>公众号</span>
            </div>
        </header>
        <!--这里的 search 组件的样式也需要修改一下-->
        <search></search>
        <!--华工app集合-->
        <template v-for="(value,key) in ScutAppsList">
            <div class="weui-cells__title" :key="key">{{key}}</div>
            <div class="weui-cells" :key="key+1">
                <router-link to="/contact/scut_apps/myPass" class="weui-cell">
                    <div class="weui-cell weui-cell_access" v-for="(item,index) in value" :key="index">
                        <div class="weui-cell__hd">
                            <img :src="item.headerUrl" class="home__mini-avatar___1nSrW">
                        </div>
                        <div class="weui-cell__bd">
                            {{item.name}}
                        </div>
                        <div v-if="item.name=='My Pass 我的通行证'"></div>
                    </div>
                </router-link>
            </div>
        </template>
    </div>
</template>
<script>
    import search from "../common/search"
    export default {
        components: {
            search
        },
        data() {
            return {
                pageName: ""
            }
        },
        computed: {
            // 提取公众号首字母 排序，所有公众号被存放在 ScutApps.js 中
            initialList: function () {
                var initialList = [],
                    ScutApps = this.$store.state.ScutApps,
                    max = ScutApps.length
                for (var i = 0; i < max; i++) {
                    if (initialList.indexOf(ScutApps[i].initial) == -1) {
                        initialList.push(ScutApps[i].initial)
                    }
                }
                return initialList.sort()
            },
            // 将公众号按照首字母分类
            ScutAppsList() {
                var ScutAppsList = {},
                    ScutApps = this.$store.state.ScutApps,
                    max = ScutApps.length;
                for (var i = 0; i < this.initialList.length; i++) {
                    var protoTypeName = this.initialList[i]
                    ScutAppsList[protoTypeName] = []
                    for (var j = 0; j < max; j++) {
                        if (ScutApps[j].initial === protoTypeName) {
                            ScutAppsList[protoTypeName].push(ScutApps[j])
                        }
                    }
                }
                return ScutAppsList
            }
        }

    }
</script>
<style>
    .official-account {
        padding-bottom: 20px;
    }

    .official-account .weui-cell_access:active {
        background-color: rgba(177, 177, 177, 0.53)
    }
</style>