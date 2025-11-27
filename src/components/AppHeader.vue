<script>
import { defineComponent,ref } from 'vue';
export default defineComponent({
    name: 'AppHeader',
    setup(){
        const mockupHeader = ref('Quote Generator');
        return {
            mockupHeader,
        }
    }
})
</script>

<template>
    <header>
        <h1 class="header-title">{{ mockupHeader }}</h1>
    </header>
</template>

<style scoped>
.header-title {
    text-align: center;
    font-size: 2rem;
    margin: 1rem 0;
}
</style>