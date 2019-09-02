<template>
    <div v-swiper:mySwiper="swiperOption">
        <div class="swiper-wrapper">
            <component v-bind:is="_component"
                       v-for="(_data, key) in this.data_for_component"
                       v-bind:key="key"
                       v-bind:name="_data.first_name"
                       v-bind:text="_data.email"
            />
        </div>
        <div class="swiper-pagination"></div>
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
                    pagination: {
                        el: '.swiper-pagination',
                        dynamicBullets: true
                    },
                    slidesPerView: 3,
                    on: {
                        slideChange() {
                        },
                        tap() {

                        }
                    }
                }
            }
        },
        props:{
            component: Object,
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
    .swiper-pagination{
        width: auto!important;
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translateX(-50%);
    }
    .swiper-wrapper{
        margin-bottom: 100px;
    }
</style>