<template>
    <main class="main reviews-main">
        <div class="reviews-main__inner">
            <Swipe v-bind:component="comp"
                   v-bind:data_for_component="data_for_component"
                   v-bind:addition_styles="addition_styles"
            />
        </div>
    </main>
</template>


<script>

    import Reviews from '~/components/sliders/items/Reviews.vue';
    import Swipe from '~/components/sliders/Swipe.vue';

    export default {
        async asyncData(){
            const response = await fetch('https://reqres.in/api/users?page=2');
            var data_for_component =  await response.json();
            data_for_component = data_for_component['data'];
            return {data_for_component};
        },
        data(){
          return{
              data_for_component: [],
              comp: Reviews,
              addition_styles:{
                  zoom_side_slides: false,
              }
          }
        },
        components:{
            Swipe: Swipe,
        },
        mounted(){
        },
    }
</script>


<style lang="scss">
 .reviews-main{
     margin-top: auto;
     margin-bottom: auto;
     &__inner{
         padding-left: 20px;
         padding-right: 20px;
         .review-item{
             &__inner{
                display: flex;
                 flex-direction: column;
             }
         }
     }
 }
</style>