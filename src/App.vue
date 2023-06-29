<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
export default {
    data() {
        return {

        }
    },
    components: { AppHeader, AppMain, AppFooter }
}
</script>

<template>
    <!-- Header -->
    <AppHeader />
    <!-- Main -->
    <AppMain />
    <!-- Footer -->
    <AppFooter />
</template>
<!-- Style -->
<style>
/* Css Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
</style>