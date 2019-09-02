<template>
    <div v-swiper:mySwiper="swiperOption">
        <div class="swiper-wrapper" v-bind:class="this.addition_styles">
            <component v-bind:is="_component"
                       v-for="(_data, key) in this.data_for_component"
                       v-bind:key="key"
                       v-bind:name="_data.first_name"
                       v-bind:text="_data.email"
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
                    parallax: true,
                    init: true,
                    autoplay: {
                        delay: 5000,
                    },
                    pagination: {
                        el: '.swiper-pagination',
                        clickable: true,
                        dynamicBullets: true
                    },
                    slidesPerView: 3,
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


<style lang="scss" scoped>

    .my-swiper {
        height: 300px;
        width: 100%;
        .swiper-slide {
            text-align: center;
            font-size: 38px;
            font-weight: 700;
            background-color: #eee;
            display: flex;
            justify-content: center;
            align-items: center;

        }

    }
    /*.swiper-pagination{
        width: auto!important;
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translateX(-50%);
    }*/
    .swiper-wrapper{
        margin-bottom: 100px;
    }
</style>