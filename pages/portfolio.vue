<template>
    <main class="main portfolio-main">
        <div class="portfolio-main__inner">
            <Swipe v-bind:component="comp"
                   v-bind:data_for_component="data_for_component"
                   v-bind:addition_styles="addition_styles"
            />
        </div>
    </main>
</template>


<script>

    import Portfolio from '~/components/sliders/items/Portfolio.vue';
    import Swipe from '~/components/sliders/Swipe.vue';

    export default {
        async asyncData(){
            const response = await fetch('https://reqres.in/api/users?page=1');
            var data_for_component =  await response.json();
            data_for_component = data_for_component['data'];
            return {data_for_component};
        },
        data(){
            return{
                data_for_component: [],
                comp: Portfolio,
                addition_styles:{
                    zoom_side_slides: true,
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
    .portfolio-main{

        margin-bottom: auto;
        margin-top: auto;
    }
</style>