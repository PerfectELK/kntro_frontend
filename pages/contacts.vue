<template>
    <main class="main contacts-main">
        <div class="contacts-block container-fluid">
            <div class="contacts-block__inner row">

                <div class="col contact-form">
                    <div class="contact-form__inner">
                        <div class="contact-form__header">
                            <h2>
                                Связаться со мной
                            </h2>
                        </div>
                        <div class="contact-form__fields">
                            <div class="field-container">
                                <div class="two-inputs">
                                    <TextInput v-model="form.name"></TextInput>
                                    <TextInput v-model="form.email"></TextInput>
                                </div>
                                <div class="one-input">
                                    <Button v-bind:name="form.button" v-on:click="btnClicked()"/>
                                </div>
                            </div>
                        </div>
                        <div class="contact-form__bottom">
                            <p>
                                В скором времени я с вами свяжусь!
                            </p>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </main>
</template>

<script>
    import TextInput from '~/components/inputs/text.vue'
    import Button from '~/components/inputs/button.vue'

    export default {
        data(){
            return{
                form:{
                    name:'',
                    email:'',
                    button: "Отправить"
                }
            }
        },
        components:{
            TextInput,
            Button
        },
        methods:{
            btnClicked(){
                console.log('clicked');
            }
        }
    }
</script>

<style lang="scss">
    $large_dev : 992px;
    $extra_small : 576px;
    .contacts-main{
        margin-top: auto;
        margin-bottom: auto;
        .contacts-block{
            .contacts-block__inner{
                .contact-form{
                    max-width: 700px;
                    margin: auto;
                    transform: translateX(calc(-1*((100vw - 480px)/(1920 - 480) * (150 - 0) + 0px)));
                    &__inner{
                        display: flex;
                        flex-direction: column;
                        .contact-form__header{
                            h2{
                                color: #FF4F79;
                                font-style: normal;
                                font-weight: normal;
                                font-family: 'Russo One', sans-serif;
                                font-size: calc( (100vw - 480px)/(1920 - 480) * (64 - 34) + 34px);
                            }
                        }
                        .contact-form__bottom{
                            margin-top: 1em;
                            p{
                                font-family: 'Russo One', sans-serif;
                                font-style: normal;
                                font-weight: normal;
                                font-size: calc( (100vw - 480px)/(1920 - 480) * (28 - 24) + 24px);
                                line-height: 43px;
                                color: #92A3C4;
                            }
                        }
                    }
                    .contact-form__fields{
                        margin-top: 1em;
                        .field-container{
                            .two-inputs{
                                display: flex;
                                flex-direction: row;
                                justify-content: space-between;
                            }
                            .one-input{
                                margin-top: 1.5em;
                                display: flex;
                            }
                        }
                    }
                }
            }
        }
    }
</style>