<template>
    <main class="main about-main">
        <div class="about-block container-fluid">
            <div class="about-block__inner row">
                <div class="about-text col-lg-5 col-xl-5 col-md-12 col-xs-12 col-sm-12 ">
                    <div class="about-text__inner">
                        <p>
                            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Id pariatur quam rerum! Ab beatae debitis dolore earum eos harum nam nostrum, obcaecati odio perferendis qui, quod reprehenderit sequi tempora temporibus. Asperiores assumenda atque, cum delectus deleniti dolores enim est et expedita fuga, ipsa ipsam ipsum iusto molestiae mollitia, nobis perferendis placeat quidem quod quos recusandae sit suscipit tempore temporibus tenetur totam voluptates. Aliquid, autem consequuntur doloremque esse itaque nulla quae quasi quidem reiciendis rem tenetur veniam voluptate. Aliquam distinctio ipsum nesciunt nobis officiis? Debitis dolor excepturi illum laboriosam mollitia perspiciatis praesentium quae quisquam voluptatem. Aliquam consequatur ipsum laborum nam quia.
                        </p>
                    </div>
                </div>
                <div class="about-img col-lg-7 col-xl-7 col-md-12 col-xs-12 col-sm-12">
                    <div class="about-img__inner">
                        <img src="~/static/img/tmp/about.png" alt="">
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>


<style lang="scss">
    $large_dev : 992px;
    .about-main{
        margin-top: auto;
        margin-bottom: auto;
        .about-block{

            &__inner {
                @media screen and (max-width: $large_dev) {
                    flex-direction: column;
                    align-items: center;
                    justify-content: center;
                    margin-top: 2em;
                    .about-text{

                        &__inner{
                            margin: auto;
                            max-width: 600px;
                            p{

                            }
                        }
                    }
                    .about-img{
                        &__inner{
                            max-width: 600px!important;
                            margin: 0 auto;
                            min-width: 281px!important;
                        }
                    }
                }
                .about-text{
                    &__inner{
                        height: 100%;
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        text-align: center;
                        position: relative;
                        p{
                            position: absolute;
                            left: 25%;
                            top:50%;
                            transform: translateY(-50%);
                            min-width:700px;
                            z-index: 95;
                            font-family: 'Russo One', sans-serif;
                            font-size: calc( (100vw - 480px)/(1920 - 286) * (24 - 14) + 14px);
                            color:#0B156E;
                            @media screen and (max-width: 1650px) {
                                left: 10%;
                            }
                            @media screen and (max-width: 1350px) {
                                position: relative;
                                transform: translateX(0);
                                top:0;
                                left: 0;
                                min-width: auto;
                            }
                        }
                    }
                }
                .about-img {
                    .about-img__inner{
                        margin: 0 auto;
                        max-width: 800px;
                        min-width: 500px;
                        img{
                            width:100%;
                        }
                    }
                }
            }
        }
    }
</style>