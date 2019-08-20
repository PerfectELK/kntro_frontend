<template>
    <nav class="navbar navbar-is-fixed">
        <ul>
            <li>
                <router-link to="/">Главная</router-link>
            </li>
            <li>
                <router-link to="/about">Обо мне</router-link>
            </li>
            <li>
                <router-link to="/portfolio">Портфолио</router-link>
            </li>
            <li>
                <router-link to="/reviews">Отзывы</router-link>
            </li>
            <li>
                <router-link to="/contacts">Контакты</router-link>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
  name: 'navbar'

}
</script>
