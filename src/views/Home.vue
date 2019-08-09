<template>
    <div class="home">
        <div class="gallery-wrapper">
            <!--<el-card class="gallery-element" v-for="(o, index) in 10" :key="o" :offset="index > 0 ? 2 : 0">-->
            <!--<div class="gallery-element-top-side">-->
            <!--<img src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png"-->
            <!--class="image">-->
            <!--<h3>Alis</h3>-->
            <!--</div>-->
            <!--<div class="bottom clearfix">-->
            <!--<time class="time">11.03.2001</time>-->
            <!--<el-button type="text" class="button">Operating</el-button>-->
            <!--</div>-->
            <!--</el-card>-->
            <div class="gallery-item">
                <div class="picture">
                    <img class="img-fluid" src="https://picsum.photos/130/130?image=1027">
                </div>
                <div class="title-content">
                    <article class="name">Michele Miller</article>
                    <el-tag class="title">Designer</el-tag>
                </div>
                <el-collapse class="services-wrapper">
                    <el-collapse-item >
                        <template slot="title">
                            <span class="services-title">Services:</span>
                            <i class="header-icon el-icon-magic-stick"></i>
                        </template>
                        <div class="services-content">
                            <ul>
                                <li v-for="skill in skills ">{{skill}},</li>
                            </ul>
                        </div>
                    </el-collapse-item>
                </el-collapse>
                <div class="services-actions">
                    <el-button class="profile" type="primary">Details</el-button>
                    <el-rate
                            v-model="value"
                            :colors="colors">
                    </el-rate>
                </div>
                <ul class="social">
                    <li><a href="https://codepen.io/collection/XdWJOQ/" class="" aria-hidden="true">
                        <font-awesome-icon icon="facebook-f" />
                    </a></li>
                    <li><a href="https://codepen.io/collection/XdWJOQ/" class="fa fa-twitter" aria-hidden="true">
                        <font-awesome-icon icon="circle"/>
                    </a></li>
                    <li><a href="https://codepen.io/collection/XdWJOQ/" class="fa fa-google-plus"
                           aria-hidden="true"></a></li>
                    <li><a href="https://codepen.io/collection/XdWJOQ/" class="fa fa-linkedin" aria-hidden="true"></a>
                    </li>
                </ul>
            </div>

        </div>
    </div>
</template>

<script>
    // @ is an alias to /src
    import HelloWorld from '@/components/HelloWorld.vue'

    export default {
        name: 'home',
        components: {
            HelloWorld
        },
        data() {
            return {
                skills: ['meow', 'meow', 'meow', 'meow', 'meow', 'meow', 'meow',],
                value: null,
                colors: ['#99A9BF', '#F7BA2A', '#FF9900']
            }
        }
    }
</script>

<style scoped lang="scss">
    .gallery-wrapper {
        display: flex;
        flex-wrap: wrap;

        .gallery-item {
            padding: 30px 0 40px;
            margin-bottom: 30px;
            background-color: $gray-background;
            text-align: center;
            overflow: hidden;
            position: relative;
            max-width: 350px;
            min-width: 350px;
            height: auto;
        }

        .gallery-item .picture {
            display: inline-block;
            height: 130px;
            width: 130px;
            margin-bottom: 50px;
            z-index: 1;
            position: relative;
        }

        .gallery-item .picture::before {
            content: "";
            width: 100%;
            height: 0;
            border-radius: 50%;
            background-color: $primary;
            position: absolute;
            bottom: 135%;
            right: 0;
            left: 0;
            opacity: 0.9;
            transform: scale(3);
            transition: all 0.3s linear 0s;
        }

        .gallery-item .picture::before {
            height: 100%;
        }

        .gallery-item .picture::after {
            content: "";
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background-color: $primary;
            position: absolute;
            top: 0;
            left: 0;
            z-index: -1;
        }

        .gallery-item .picture img {
            width: 100%;
            height: auto;
            border-radius: 50%;
            transform: scale(1);
            transition: all 0.9s ease 0s;
        }

        .gallery-item .picture img {
            box-shadow: 0 0 0 14px $gray-background;
            transform: scale(0.7);
        }

        .gallery-item .title {
            display: block;
            font-size: 15px;
            color: #4e5052;
            text-transform: capitalize;
        }

        .gallery-item .social {
            width: 100%;
            padding: 0;
            margin: 0;
            background-color: $primary;
            position: absolute;
            bottom: -100px;
            left: 0;
            transition: all 0.5s ease 0s;
        }

        .gallery-item .social {
            bottom: 0;
        }

        .gallery-item .social li {
            display: inline-block;
        }

        .gallery-item .social li a {
            display: block;
            padding: 10px;
            font-size: 17px;
            color: $white;
            transition: all 0.3s ease 0s;
            text-decoration: none;
        }

        .gallery-item .social li a:hover {
            color: $primary;
            background-color: $gray-background;
        }


        .title-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 0.8rem 0 0.8rem;

            .name {
                font-size: 1.1rem;
                font-weight: bold;
                color: $dark-blue;
            }
            .title {
                font-size: 1.1rem;
                color: $dark-blue;
            }
        }

        .services-wrapper {
            margin-top: 0.8rem;
            .services-title {
                margin-left: 0.5rem;
                font-size: 1rem;
                color: $dark-blue;

         }
            .header-icon {
                margin-left: 0.3rem;
                color: $dark-blue;
            }
            .services-content {
                padding-left: 0.5rem; color: $dark-blue;

                ul {
                    list-style-type: none;
                    margin: 0;
                    padding: 0;
                    overflow: hidden;

                    li {
                        font-size: 1rem;
                        float: left;
                        padding-right: 0.4rem;
                        color: $dark-blue;

                    }
                }
            }
        }
        .services-actions {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 1rem 0 0.5rem;
            .profile {
                margin-left: 0.5rem;
                background-color: $primary;
                &:hover {
                    background-color: #7ba8ff;
                }
            }
        }

    }


</style>
