<template>
    <div id="app">
        <div class="navigation-wrapper">
            <el-menu
                    class="el-menu"
                    mode="horizontal">
                <router-link to="/" tag="img" :src="logoImg" class="logo"></router-link>
                <div class="links">
                    <el-menu-item class="link">Processing Center</el-menu-item>
                    <el-menu-item class="link">Processing Center</el-menu-item>
                    <el-menu-item class="link">Processing Center</el-menu-item>
                </div>
                <aside class="right-nav-part">
                    <a>logout</a>
                </aside>
            </el-menu>
        </div>
        <router-view/>
    </div>
</template>

<script lang="js">
    export default {
        data() {
            return {
                visible: true,
                logoImg: require('./assets/ustore.png')
            };
        }
    };
</script>

<style lang="scss" scoped>
    .navigation-wrapper {
        .el-menu {
            display: flex;
            align-items: center;
            background: linear-gradient(to top, #ffffff -30%, #6699ff 100%);
            .logo {
                width: 5rem;
                height: 5rem;
                cursor: pointer;
                margin-left: 5rem;
            }
            .links {
                margin: 0 auto;
                .link {
                    display: inline-block;
                    color: $text-dark-gray;
                    font-weight: 600;
                }
            }
            .right-nav-part {
                    margin-left: auto;
                a {
                    margin-right: 5rem;
                    cursor: pointer;
                    color: $text-dark-gray;
                    font-weight: 600;
                }
            }
        }
    }
</style>
