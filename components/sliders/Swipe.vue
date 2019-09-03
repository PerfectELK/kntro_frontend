<template>
    <div v-swiper:mySwiper="swiperOption">
        <div class="swiper-wrapper" v-bind:class="this.addition_styles">
            <component v-bind:is="_component"
                       v-for="(_data, key) in this.data_for_component"
                       v-bind:key="key"
                       v-bind:__data="_data"
            />
        </div>
        <div class="swiper-pagination swiper-pagination-clickable swiper-pagination-bullets swiper-pagination-bullets-dynamic"></div>
    </div>
</template>

<script>


    export default {
        data () {
            return {
                swiperOption: {
                    loop: true,
                    centeredSlides: true,
                    spaceBetween: 30,
                    slidesPerView: 3,
                    setWrapperSize: true,
                    //     delay: 5000,
                    // },
                    pagination: {
                        el: '.swiper-pagination',
                        clickable: true,
                        dynamicBullets: true
                    },
                    on: {
                        slideChange() {
                        },
                        tap() {

                        }
                    },
                    breakpoints:{
                        645: {
                            slidesPerView: 1,
                        },
                        // when window width is <= 480px
                        978: {
                            slidesPerView: 2,
                        },
                        // when window width is <= 640px
                        1200: {
                            slidesPerView: 3
                        }
                    }
                }
            }
        },
        props:{
            component: Object,
            addition_styles: Object,
            data_for_component: Array,
        },
        mounted() {

        },
        computed:{
            _component(){
                return this.component;
            }
        }
    }
</script>


<style lang="scss">
    .my-swiper {
        height: 300px;
        position: relative;
        .swiper-slide {
            /*text-align: center;
            font-size: 38px;
            font-weight: 700;
            background-color: #eee;
            display: flex;
            justify-content: center;
            align-items: center;
            */
        }

    }
    .swiper-wrapper{
        margin-bottom: 100px;
    }
    .zoom_side_slides{
        .swiper-slide{
            //width: 300px !important;
            //position: relative;
            //width: 400px!important;
            //margin: auto 0;
            //transition: max-width 0.4s ease-in-out;

        }
        .swiper-slide-active{
            //width: 450px;
            //width: 50%;
            .portfolio-item{
                &__inner{
                    .portfolio-photo {
                        &__inner {
                            img{
                                //width: 350px;
                            }
                        }
                    }
                }
            }
            //width: 500px!important;
        }
        /*.swiper-slide-prev{
            transform: scale(0.7);
            transition: transform 0.8s ease-in-out;
        }
        .swiper-slide-next{
            transform: scale(0.7);
            transition: transform 0.8s ease-in-out;
        }*/
    }
</style>