<template>
    <div class="text-block">
        <input type="text" v-bind:placeholder="this.placeholder" v-bind:class="this.input_class" v-bind:value="this.value" v-on:input="onInput()">
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
            value: String,
            placeholder: String
        },
        methods:{
            onInput(value) {
                this.$emit('input', event.target.value)
            },
        }
    }
</script>

<style lang="scss">
    .text-block{
        max-width: 400px;
        box-sizing: border-box;
        input{
            width:100%;
            height: 40px;
            border: 1.5px solid #0C156F;
            border-radius: 20px;
            background: rgba(255,255,255,0.1);
            outline: none;
            font-size: 22px;
            font-weight: normal;
            font-family: 'Russo One', sans-serif;
            padding-left: 24px;
        }
        input:focus{
            &::placeholder{
                opacity: 1;
            }
        }
        input::placeholder{
            transition: all 0.5s ease-in-out;
            opacity: 0;
        }
    }
</style>