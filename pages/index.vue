<template>
    <main class="main index-main">
        <div class="content-wrapper container-fluid">
            <div class="content row">
                <div class="content-text col-lg-5 col-xl-5 col-md-12 col-xs-12 col-sm-12">
                    <div class="content-container" v-if="this.render_content_container">
                        <div class="content-text__inner">
                            <h1>
                                Web - Дизайн
                            </h1>
                            <h3>
                                Новиковой Екатерины
                            </h3>
                        </div>
                        <div class="content-text__btn">
                            <button class="button">Связаться со мной</button>
                        </div>
                    </div>
                </div>
                <div class="content-image col-lg-7 col-xl-7 col-md-12 col-xs-12 col-sm-12">
                    <div class="content-image__inner">
                        <div class="content-container content-container-absolute" v-if="!this.render_content_container">
                            <div class="content-text__inner">
                                <h1>
                                    Web - Дизайн
                                </h1>
                                <h3>
                                    Новиковой Екатерины
                                </h3>
                            </div>
                            <div class="content-text__btn">
                                <button class="button">Связаться со мной</button>
                            </div>
                        </div>
                        <img src="~/static/img/tmp/index.png" alt="">
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
    export default {
        data(){
            return{
                the_window: (typeof window != 'undefined') ? window.innerWidth : null ,
                window_less_large: false,
                window_less_small: false,
                render_content_container:true,
            }
        },
        watch:{
            the_window: function(){
                if(window.innerWidth > 992) {
                    this.window_less_large = false;
                    this.render_content_container = true;
                }else{
                    this.window_less_large = true;
                    this.render_content_container = false;
                }
                if(window.innerWidth < 576){
                    this.window_less_small = true;
                    this.render_content_container = true;
                }else{
                    this.window_less_small = false;
                }
            }
        },
        mounted(){
            if(window.innerWidth > 992) {
                this.window_less_large = false;
                this.render_content_container = true;
            }else{
                this.window_less_large = true;
                this.render_content_container = false;
            }
            if(window.innerWidth < 576){
                this.window_less_small = true;
                this.render_content_container = true;
            }else{
                this.window_less_small = false;
            }
            window.onresize = () => {
                this.the_window = window.innerWidth;
            }
        },
    }
</script>

<style lang="scss">
    $tablets : 768px;
    $large_dev : 992px;
    .index-main {
        margin-top: auto;
        margin-bottom: auto;
        .content-wrapper {
            .content {
                display: flex;
                justify-content: center;
                @media screen and (max-width: $large_dev) {
                    flex-direction: column;
                    align-items: center;
                    .content-image{
                        max-width: none;
                        margin-top: 1.5em;
                        min-width: 281px!important;
                    }
                }
                .content-image{
                    min-width: 480px;
                    max-width: 770px;
                    .content-image__inner{
                        img{
                            width: 100%;
                        }
                    }
                    .content-container {
                        &.content-container-absolute{
                            position: absolute;
                            left: 15px;
                            top:15px;
                        }
                        display: flex;
                        flex-direction: column;
                        .content-text__inner {
                            display: flex;
                            flex-direction: column;
                            h1 {
                                font-family: 'Russo One', sans-serif;
                                font-size: calc( (100vw - 480px)/(1920 - 286) * (72 - 34) + 34px);
                                color:#0C156F;
                            }
                            h3{
                                font-family: 'Russo One', sans-serif;
                                font-size: calc( (100vw - 480px)/(1920 - 480) * (32 - 23) + 23px);
                                color:#0C156F;
                                @media screen and (max-width: $large_dev) {
                                    text-align: center;
                                }
                            }
                        }
                        .content-text__btn {
                            margin-top: 1em;
                            text-align: center;
                            @media screen and (max-width: $large_dev) {
                                text-align: left;
                            }
                            button {
                                background-color: #FF4F79;
                                color: #ffffff;
                                font-family: 'Russo One', sans-serif;
                                font-size: 17px;
                                border: none;
                                min-height: 55px;
                                padding: 0 23px;
                                border-radius: 20px;

                            }
                        }
                    }
                }
                .content-text {
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    .content-container {

                        display: flex;
                        flex-direction: column;
                        .content-text__inner {
                            display: flex;
                            flex-direction: column;
                            h1 {
                                font-family: 'Russo One', sans-serif;
                                font-size: calc( (100vw - 480px)/(1920 - 286) * (72 - 34) + 34px);
                                color:#0C156F;
                            }
                            h3{
                                font-family: 'Russo One', sans-serif;
                                font-size: calc( (100vw - 480px)/(1920 - 480) * (32 - 23) + 23px);
                                color:#0C156F;
                                @media screen and (max-width: $large_dev) {
                                    text-align: center;
                                }
                            }
                        }
                        .content-text__btn {
                            margin-top: 1em;
                            text-align: center;
                            @media screen and (max-width: $large_dev) {
                                text-align: left;
                            }
                            button {
                                background-color: #FF4F79;
                                color: #ffffff;
                                font-family: 'Russo One', sans-serif;
                                font-size: 17px;
                                border: none;
                                min-height: 55px;
                                padding: 0 23px;
                                border-radius: 20px;

                            }
                        }
                    }

                }
            }
        }
    }
</style>
