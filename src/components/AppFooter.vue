<script>
import { defineComponent,ref } from 'vue';
export default defineComponent({
    name: 'AppFooter',
    setup() {
        const footerText = ref("Copyright © 2025 Jainam. All rights reserved.");
        return {
            footerText,
        }
    }
})
</script>

<template>
    <footer>
        <p>{{ footerText }}</p>
    </footer>
</template>

<style scoped>
footer {
    position: fixed;
    bottom: 0%; 
    width: 100%;
    padding: 1rem;
    border-top: 1px solid #eee;
    
    p{
        text-align: center;
        font-size: 0.9rem;
        color: #777;
    }
}
</style>