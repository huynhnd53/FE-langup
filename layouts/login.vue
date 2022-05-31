<template>
    <v-app>
        <v-main class="contain-layout-auth">
            <Nuxt />
        </v-main>
    </v-app>
</template>

<style lang="scss" scoped>
.contain-layout-auth {
    background: rgb(2, 0, 36);
    background: linear-gradient(90deg, rgba(2, 0, 36, 1) 0%, rgba(74, 175, 148, 1) 26%, rgba(0, 212, 255, 1) 94%);
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    align-items: center;
}
</style>
