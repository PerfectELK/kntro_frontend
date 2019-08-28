<template>
    <main class="main index-main">
        <div class="content-wrapper container-fluid">
            <div class="content row">
                <div class="content-text col">
                    <div class="content-container">
                        <div class="content-text__inner">
                            <h1>
                                Web - Дизайн
                            </h1>
                            <h3>
                                Новиковой Екатерины
                            </h3>
                        </div>
                        <div class="content-text__btn">
                            <button class="button">Связаться со мной</button>
                        </div>
                    </div>
                </div>
                <div class="content-image col">
                    <div class="content-image__inner">
                        <img src="~/static/img/tmp/index.png" alt="">
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
    export default {}
</script>

<style lang="scss">
    .index-main {
        .content-wrapper {
            .content {
                .content-text {
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    .content-container {

                        display: flex;
                        flex-direction: column;
                        .content-text__inner {
                            display: flex;
                            flex-direction: column;
                            h1 {
                                font-family: 'Russo One', sans-serif;
                            }
                            h2 {
                                font-family: 'Russo One', sans-serif;
                            }
                        }
                        .content-text__btn {
                            margin-top: 1em;
                            button {
                                background-color: #FF4F79;
                                color: #ffffff;
                                font-family: 'Russo One', sans-serif;
                                font-size: 17px;
                                border: none;
                                min-height: 55px;
                                padding: 0 23px;
                                border-radius: 20px;
                            }
                        }
                    }

                }
            }
        }
    }
</style>
