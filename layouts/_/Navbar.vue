<template>
    <section class="navbar-section">
        <nav class="navbar-block">
            <div class="navbar-block__logo" v-if="!this.window_less">
                <div class="logo-wrapper">
                    <div class="logo">
                        <nuxt-link to="/">
                        <img src="~/static/img/tmp/Rectangle.png" alt="">
                        </nuxt-link>
                    </div>
                </div>
            </div>
            <div class="navbar-block__element" v-bind:class="this.classes.navbar">
                <ul class="nav-panel">
                    <li class="nav-panel__item" v-if="this.window_less">
                        <nuxt-link to="/" class="nav-link">
                            <img src="~/static/img/tmp/Rectangle.png" alt="">
                        </nuxt-link>
                    </li>
                    <li class="nav-panel__item">
                        <nuxt-link to="/about" class="nav-link">Обо мне</nuxt-link>
                    </li>
                    <li class="nav-panel__item">
                        <nuxt-link to="/portfolio" class="nav-link">Портфолио</nuxt-link>
                    </li>
                    <li class="nav-panel__item">
                        <nuxt-link to="/reviews" class="nav-link">Отзывы</nuxt-link>
                    </li>
                    <li class="nav-panel__item">
                        <nuxt-link to="/contacts" class="nav-link nav-link-pink">Связаться со мной</nuxt-link>
                    </li>
                </ul>
            </div>
            <Hamburger v-on:hamburgerClicked="clickHamburger"/>
        </nav>
    </section>
</template>

<script>
    import Hamburger from '~/components/hamburger/DotsHamburger.vue'
    export default {
        data(){
          return{
              classes:{
                  navbar:{
                    'navbar-block__element-visible': false,
                  }
              },
              the_window: (typeof window != 'undefined') ? window.innerWidth : null ,
              window_less: '',
          }
        },
        watch:{
          the_window: function(){
              if(window.innerWidth > 992){
                  this.window_less = false
              }else{
                  this.window_less = true;
              }
          }
        },
        mounted(){

            if (window.innerWidth > 992) {
                this.window_less = false
            } else {
                this.window_less = true;
            }

            window.addEventListener('resize',() => {
                this.the_window = window.innerWidth;
            });
        },
        components:{
            Hamburger
        },
        methods:{
            clickHamburger(isOpen){
                this.classes.navbar['navbar-block__element-visible'] = isOpen;
            }
        }
    }
</script>

<style lang="scss">
    $large_dev : 992px;
    .nuxt-link-active{
        color:#0C156F!important;
    }
    .navbar-section{
        display: flex;
        flex-direction: row;
        //justify-content: center;
        margin-left: calc( (100vw - 1000px)/(1920 - 1000) * (250 - 0) + 0px)!important;;
        height: auto;
        .navbar-block{
            //width: 100%;
            display: flex;
            flex-direction: row;
            justify-content: center;
            .navbar-block__logo{

                margin-top: 3em;
                max-width: 132px;
                .logo-wrapper{
                    .logo{
                        a{
                            img{
                                height: 132px;
                                width: 132px;
                            }
                        }

                    }
                }
            }
            .navbar-block__element{
                flex-grow: .1;
                display: flex;
                flex-direction: row;
                justify-content: flex-end;
                position: relative;
                transition: all 0.5s ease-in-out;
                @media screen and (max-width: $large_dev) {
                    position: absolute;
                    top:-1000px;
                    left:50%;
                    transform: translateX(-50%);
                    width: 100%;
                    height: 100vh;
                    justify-content: center!important;
                    z-index: 100;
                    background-color: #fff;
                    &-visible{
                        top:0;
                    }
                    .nav-panel{
                        flex-direction: column!important;
                        justify-content: flex-start!important;
                        align-items: center!important;
                        &__item{
                            margin-left: 0!important;
                            margin-top: 2em;
                            .nav-link{
                                font-size: calc( (100vw - 480px)/(1920 - 480) * (72 - 34) + 34px)!important;
                            }
                        }
                    }
                }
                .nav-panel{
                    padding: 0;
                    margin-top: 1em;
                    align-self: center;
                    display: flex;
                    flex-direction: row;
                    justify-content: center;
                    align-items: center;
                    list-style-type: none;
                    .nav-panel__item{
                        margin-left: 1em;
                        &:first-child{
                            margin-left: 0;
                        }
                        &:last-child{
                            margin-left: 3em;
                        }
                        .nav-link{
                            font-family: 'Russo One', sans-serif;
                            font-style: normal;
                            font-weight: normal;
                            font-size: 20px;
                            line-height: 29px;
                            color:#797FB5;
                            transition: all 0.5s ease-in-out;
                            &:hover{
                                color:hotpink;
                            }
                            &-pink{
                                color:hotpink;
                            }
                        }
                    }
                }
            }
        }
    }
</style>