<script setup>
import './header.scss'

</script>

<template>
    <header class="header">
        <div class="header__container container">
            <RouterLink to="/" target="_blank"><h1 class="header__logo logo">Boutique</h1></RouterLink>
            <nav class="header__menu">
                <ul class="header__list">
                    <li class="header__item"><RouterLink class="header__link" to="/" target="_blank">Home</RouterLink></li>
                    <li class="header__item"><RouterLink class="header__link" to="/about" target="_blank">About Us</RouterLink></li>
                    <li class="header__item"><a class="header__link">Blog</a></li>
                    <li class="header__item"><a class="header__link">Catalog</a></li>
                </ul>
            </nav>
        </div>
    </header>
</template>
