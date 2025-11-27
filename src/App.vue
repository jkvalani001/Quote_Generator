<script>
import Header from '@/components/Header.vue';
import Content from '@/components/Content.vue';
import Footer from '@/components/Footer.vue';
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'App',
    components: {
        Header,
        Content,
        Footer,
    },
    setup() {
        //
    }
})
</script>

<template>
    <Header />
    <Content />
    <Footer />
</template>

<style scoped>

</style>
