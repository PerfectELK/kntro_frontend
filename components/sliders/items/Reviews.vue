<template>
    <div class="swiper-slide" >
        <div class="review-item">
            <div class="review-item__inner">
                <div class="review-name">
                    <div class="review-name__inner">
                        {{ this.name }}
                    </div>
                </div>
                <div class="review-text">
                    <div class="review-text__inner">
                        {{ this.text }}
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
            name:String,
            text:String,
        }
    }
</script>

<style lang="scss">
    .review-item{
        &__inner{
            display: flex;
            flex-direction: column;
            color:#0C156F;
            font-family: 'Russo One', sans-serif;
            font-style: normal;
            font-weight: normal;
            .review-name{
                &__inner{
                    text-align: center;
                    font-size: calc( (100vw - 480px)/(1920 - 286) * (22 - 15) + 15px);
                }
            }
            .review-text{
                margin-top: 2em;
                &__inner{
                    text-align: center;
                    font-size: calc( (100vw - 480px)/(1920 - 286) * (23 - 15) + 15px);
                }
            }
        }
    }
</style>