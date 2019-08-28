<template>
    <section class="navbar-section">
        <nav class="navbar-block">
            <div class="navbar-block__logo">
                <div class="logo-wrapper">
                    <div class="logo">
                        <img src="~/static/img/tmp/Rectangle.png" alt="">
                    </div>
                </div>
            </div>
            <div class="navbar-block__element">
                <ul class="nav-panel">
                    <li class="nav-panel__item">
                        <nuxt-link to="/about" class="nav-link">Обо мне</nuxt-link>
                    </li>
                    <li class="nav-panel__item">
                        <nuxt-link to="/portfolio" class="nav-link">Портфолио</nuxt-link>
                    </li>
                    <li class="nav-panel__item">
                        <nuxt-link to="/reviews" class="nav-link">Отзывы</nuxt-link>
                    </li>
                    <li class="nav-panel__item">
                        <nuxt-link to="/contacts" class="nav-link">Связаться со мной</nuxt-link>
                    </li>
                </ul>
            </div>
        </nav>
    </section>
</template>

<style lang="scss">

    .navbar-section{
        display: flex;
        flex-direction: row;
        height: auto;
        .navbar-block{
            width: 100%;
            display: flex;
            flex-direction: row;
            justify-content: center;
            .navbar-block__logo{

                margin-top: 3em;
                max-width: 132px;
                .logo-wrapper{
                    .logo{
                        img{
                            height: 132px;
                            width: 132px;
                        }
                    }
                }
            }
            .navbar-block__element{
                flex-grow: .1;
                display: flex;
                flex-direction: row;
                justify-content: flex-end;
                .nav-panel{
                    padding: 0;
                    margin-top: 1em;
                    align-self: center;
                    display: flex;
                    flex-direction: row;
                    justify-content: center;
                    list-style-type: none;
                    .nav-panel__item{
                        margin-left: 1em;
                        &:first-child{
                            margin-left: 0;
                        }
                        &:last-child{
                            margin-left: 3em;
                        }
                        .nav-link{
                            font-family: 'Russo One', sans-serif;
                            font-style: normal;
                            font-weight: normal;
                            font-size: 20px;
                            line-height: 29px;
                            color:#797FB5;
                            &:hover{
                                color:hotpink;
                            }
                        }
                    }
                }
            }
        }
    }
</style>