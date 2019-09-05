<template>
    <div class="button-block">
        <button v-bind:class="this.input_class" v-on:click="onInput()">
            {{ this.name }}
        </button>
    </div>
</template>

<script>
    export default {
        data(){
            return{

            }
        },
        props:{
            input_class: Object,
            name: String,
        },
        methods:{
            onInput() {
                this.$emit('click')
            },
        }
    }
</script>

<style lang="scss">
    .button-block{
        width: 100%;
        box-sizing: border-box;
        button{
            width:100%;
            height: 40px;
            border: 1.5px solid #0C156F;
            border-radius: 20px;
            background: #ffffff;
            outline: none;
            font-size: 22px;
            font-weight: normal;
            font-family: 'Russo One', sans-serif;
        }
    }
</style>