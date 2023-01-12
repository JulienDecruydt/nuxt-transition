<template>
    <div>
        <div class="fixed top-0 left-0 z-10 p-2 bg-white w-full">
            <nuxt-link to="/">Home</nuxt-link>
            <nuxt-link to="/about">about</nuxt-link>
        </div>
        <div>
            <Nuxt />
        </div>
    </div>
</template>

<style>
    body {
        background: rgb(250, 167, 167);
        padding: 0;
        margin: 0;
    }
</style>