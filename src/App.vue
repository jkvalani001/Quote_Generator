<script>
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
import MainContent from './components/MainContent.vue'
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'App',
    components: {
        AppHeader,
        MainContent,
        AppFooter,
    },
    setup() {
        //
    }
})
</script>

<template>
    <AppHeader />
    <MainContent />
    <AppFooter />
</template>

<style scoped>

</style>
