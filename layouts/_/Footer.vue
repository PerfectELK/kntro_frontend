<template>
    <section class="footer-section">
        <div class="circle right-left"></div>
        <div class="circle right-right"></div>
        <div class="circle bottom-left"></div>
        <div class="circle bottom-right"></div>
    </section>
</template>


<style lang="scss">
    .footer-section{
        .circle{
            position: fixed;
            border-radius: 50%;
            &.right-left{
                z-index: -2;
                top: calc( -1 * ((100vw - 1280px)/(1920 - 1280) * (150 - 570) + 570px));;
                right: calc( -1 * ((100vw - 480px)/(1920 - 480) * (800 - 1250) + 1250px));
                width: 1500px;
                height: 1500px;
                background-color: #92A3C3;
            }
            &.right-right{
                z-index: -1;
                top:calc( -1 * ((100vw - 1280px)/(1920 - 1280) * (150 - 570) + 570px));;
                right: calc( -1 * ((100vw - 480px)/(1920 - 480) * (870 - 1320) + 1320px));
                width: 1500px;
                height: 1500px;
                background-color: #D6E4FF;
            }
            &.bottom-left{
                z-index: -1;
                bottom: -1200px;
                left: calc( -1 * ((100vw - 480px)/(1920 - 480) * (800 - 1150) + 1150px));
                width: 1500px;
                height: 1500px;
                background-color: #D6E4FF;
            }
            &.bottom-right{
                z-index: -2;
                bottom: -1180px;
                left: calc( -1 * ((100vw - 480px)/(1920 - 480) * (730 - 1080) + 1080px));
                width: 1500px;
                height: 1500px;
                background-color: #92A3C3;
            }
        }
    }
</style>