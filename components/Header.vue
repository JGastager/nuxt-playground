<template>
    <header>
        <h1>Nuxt Playground</h1>
        <nav>
            <ul>
                <li><NuxtLink to="/">Home</NuxtLink></li>
                <li><NuxtLink to="/card">Card</NuxtLink></li>
            </ul>
        </nav>
    </header>
</template>
<script setup>
</script>
<style lang="scss">
    header {
        background-color: color-mix(var(--color-background) 20%, transparent);
        color: var(--color-primary);
        backdrop-filter: blur(20px);
        display: flex;
        justify-content: center;
        align-items: center;
    }
    nav ul {
        display: flex;
        justify-content: center;
        gap: 1rem;
        list-style: none;
        li a {
            color: var(--color-text);
            text-decoration: none;
            transition: color 0.3s;
            &:hover {
                color: var(--color-primary);
            }

            &.router-link-active {
                color: var(--color-primary);
            }
        }
    }
</style>