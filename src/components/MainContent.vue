<script>
import { defineComponent, onMounted, ref } from 'vue';
export default defineComponent({
    name: 'MainContent',
    setup() {
        const quoteGujarati = ref("");
        const quoteHindi = ref("");
        const quoteEnglish = ref("");
        const author = ref("");
        const randomQuote = async() =>{
            try{
                const response = await fetch('https://raw.githubusercontent.com/jkvalani001/Quote_Generator_API/refs/heads/main/Quotes-Generator.json');
                const data = await response.json();
                const randomIndex = Math.floor(Math.random() * data.length);
                quoteGujarati.value = data[randomIndex].text_gu;
                quoteHindi.value = data[randomIndex].text_hi;
                quoteEnglish.value = data[randomIndex].text_en;
                author.value = data[randomIndex].author;
                console.log(data);
            }
            catch(error){
                console.error("Error fetching quote:", error);
            }
        }

        onMounted(() => {
            randomQuote();
        });

        return {
            quoteGujarati,
            quoteHindi,
            quoteEnglish,
            author,
            randomQuote,
        }
    }
})
</script>

<template>
    <main class="main-content">
        <div>
            <div class="content">
                <h2>{{ quoteGujarati }}</h2>
                <h2>{{ quoteHindi }}</h2>
                <h2>{{ quoteEnglish }}</h2>
                <h4 class="author-text">- {{ author }}</h4>
            </div>
            <button class="random-quote-button" @click="randomQuote">Random Quote</button>
        </div>
    </main>
</template>


<style scoped>
.main-content {
    margin-top: 2rem;
    margin-bottom: 4rem; 
    display: flex;
    justify-content: center;
    min-height: 80vh;
    align-items: center;
}
.content {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    padding: 1rem;
    border: 1px solid #eee;
    height: fit-content;
    width: fit-content;
    text-align: center;
    margin: 0 auto;
}

.author-text {
    margin-top: 0.5rem;
    color: #555;
    text-align: right;
}

.random-quote-button {
    background-color: #9500FF;
    color: #fff;
    border: 1px solid #eee;
    padding: 0.5rem 1rem;
    font-size: 1rem;
    display: block;
    margin-left: auto;
    margin-right: auto;
    cursor: pointer;
    margin-top: 1rem;
    border-radius: 8px;
}
</style>