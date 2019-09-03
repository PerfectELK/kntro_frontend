<template>
    <div class="menu-icon" v-bind:class="classObject" v-on:click="toggleClass">
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
    </div>
</template>


<script>
    export default {
        data(){
            return{
                classObject:{
                    clicked:false,
                }
            }
        },
        methods:{
            toggleClass(){
                this.classObject.clicked = !this.classObject.clicked;
                this.$emit('hamburgerClicked', this.classObject.clicked)
            }
        },
        mounted(){
            this.$router.beforeEach((to, from, next) => {
                if(window.innerWidth <= 992){
                    this.toggleClass();
                }
                next();
            })
        }
    }
</script>


<style lang="scss">

    $white: hotpink;
    $large_dev : 992px;
    @mixin animation($animation) {
        -webkit-animation: #{$animation};
        -moz-animation: #{$animation};
        -o-animation: #{$animation};
        animation: #{$animation};
    }

    @mixin animation-delay($animation-delay) {
        -webkit-transition-delay: #{$animation-delay};
        -moz-transition-delay: #{$animation-delay};
        -o-transition-delay: #{$animation-delay};
        transition-delay: #{$animation-delay};
    }

    @mixin keyframes($keyframes) {
        @-webkit-keyframes #{$keyframes} { @content; }
        @-moz-keyframes #{$keyframes} { @content; }
        @-o-keyframes #{$keyframes} { @content; }
        @keyframes #{$keyframes} { @content; }
    }

    @mixin transform($transform) {
        -webkit-transform: $transform;
        -moz-transform: $transform;
        -ms-transform: $transform;
        -o-transform: $transform;
        transform: $transform;
    }

    @mixin transition($transition...) {
        -webkit-transition: #{$transition};
        -moz-transition: #{$transition};
        -o-transition: #{$transition};
        transition: #{$transition};
    }

    @mixin transition-delay($transition-delay) {
        -webkit-transition-delay: #{$transition-delay};
        -moz-transition-delay: #{$transition-delay};
        -o-transition-delay: #{$transition-delay};
        transition-delay: #{$transition-delay};
    }

    *, *:before, *:after {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }


    .menu-icon{
        @include transform(translate(-50%, -50%));
        width: 50px;
        height: 50px;
        position: absolute;
        top:50px;
        right: 0;
        display: none;
        z-index: 120;

        @media screen and (max-width: $large_dev){
            display: block;
        }

        .dot {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 10px;
            height: 10px;
            background-color: $white;
            border-radius: 10px;
            @include transform(translate(-50%, -50%));
            @include transition(margin .4s ease .4s, width .4s ease);

            &:nth-of-type(1) {
                margin-top: -20px;
                margin-left: -20px;
                @include transform(translate(-50%, -50%) rotate(45deg));
            }

            &:nth-of-type(2) {
                margin-top: -20px;
                @include transform(translate(-50%, -50%) rotate(-45deg));
            }

            &:nth-of-type(3) {
                margin-top: -20px;
                margin-left: 20px;
            }

            &:nth-of-type(4) {
                margin-left: -20px;
            }

            &:nth-of-type(5) {

            }

            &:nth-of-type(6) {
                margin-left: 20px;
            }

            &:nth-of-type(7) {
                margin-top: 20px;
                margin-left: -20px;
            }

            &:nth-of-type(8) {
                margin-top: 20px;
            }

            &:nth-of-type(9) {
                margin-top: 20px;
                margin-left: 20px;
            }
        }

        &.clicked {
            .dot {
                @include transition(margin .4s ease, width .4s ease .4s);
                margin-left: 0;
                margin-top: 0;

                &:nth-of-type(1) {
                    width: 50px;
                }

                &:nth-of-type(2) {
                    width: 50px;
                }
            }
        }
    }
</style>