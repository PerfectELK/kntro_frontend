<template>
    <main class="main about-main">
        <div class="about-block container-fluid">
            <div class="about-block__inner row">
                <div class="about-text col-5">
                    <div class="about-text__inner">
                        <p>
                            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Id pariatur quam rerum! Ab beatae debitis dolore earum eos harum nam nostrum, obcaecati odio perferendis qui, quod reprehenderit sequi tempora temporibus. Asperiores assumenda atque, cum delectus deleniti dolores enim est et expedita fuga, ipsa ipsam ipsum iusto molestiae mollitia, nobis perferendis placeat quidem quod quos recusandae sit suscipit tempore temporibus tenetur totam voluptates. Aliquid, autem consequuntur doloremque esse itaque nulla quae quasi quidem reiciendis rem tenetur veniam voluptate. Aliquam distinctio ipsum nesciunt nobis officiis? Debitis dolor excepturi illum laboriosam mollitia perspiciatis praesentium quae quisquam voluptatem. Aliquam consequatur ipsum laborum nam quia.
                        </p>
                    </div>
                </div>
                <div class="about-img col-7">
                    <div class="about-img__inner">
                        <img src="~/static/img/tmp/about.png" alt="">
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>


<style lang="scss">
    .about-main{

        .about-block{

            &__inner {
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
                            z-index: 150;
                            font-family: 'Russo One', sans-serif;
                            font-size: calc( (100vw - 480px)/(1920 - 286) * (24 - 18) + 18px);
                            color:#0B156E;
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