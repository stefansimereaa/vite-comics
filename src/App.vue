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
    <div class="container">
        <!-- Header -->
        <AppHeader />
        <!-- Main -->
        <AppMain />
        <!-- Footer -->
        <AppFooter />
    </div>
</template>
<!-- Style -->
<style>
/* Css Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.container {
    height: 100vh;
    overflow-y: hidden;
}
</style>