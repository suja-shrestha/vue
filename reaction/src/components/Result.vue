<template>
    <div class="result-container">
        <p>Reaction time - {{ score }} ms</p>
        <p class="rank">{{ rank }}</p>
    </div>
</template>
<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if (this.score < 200) {
            this.rank = 'Fucking Fast'
        } else if (this.score < 250) {
            this.rank = 'Fast'
        } else if (this.score < 300) {
            this.rank = 'Hmmm It is Okay'
        } else {
            this.rank = 'Are You Even Trying?'
        }
    }
}
</script>
<style>
.result-container {
    height: 100px; /* Adjust the height as needed */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.rank {
    font-size: 20px;
    color: red;
    font-weight: bold;
    text-align: center;
    margin-top: 10px;
}
</style>