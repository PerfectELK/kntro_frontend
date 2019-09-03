<template>
    <div class="swiper-slide" >
        <div class="portfolio-item">
            <div class="portfolio-item__inner">
                <div class="portfolio-photo">
                    <div class="portfolio-photo__inner">
                        <img v-bind:src="this.__data.avatar" alt="photo">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
    export default {
        data(){
            return{

            }
        },
        props:{
            __data:Object
        },
        mounted(){

        }
    }
</script>

<style lang="scss">
    .portfolio-item{
        &__inner{
            display: flex;
            flex-direction: column;
            color:#0C156F;
            font-family: 'Russo One', sans-serif;
            font-style: normal;
            font-weight: normal;
            .portfolio-photo{
                text-align: center;
                &__inner{
                    display: inline-block;
                    text-align: center;
                    img{
                        transition: width 0.4s ease-in-out;
                        width: 230px;
                    }
                }
            }
        }
    }
</style>