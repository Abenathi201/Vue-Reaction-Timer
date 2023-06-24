<template>
    <p class="text"> Reaction Time: {{ score }} m/s </p>
    <p class="rank">{{ rank }}</p>
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
        if(this.score < 250) {
            this.rank = "Well Done Friend!!!!"
        }
        else if(this.score < 400) {
            this.rank = "Not Too Bad Buddy!!!!"
        }
        else{
            this.rank = "BOOO!!! You Suck Guy"
        }
    },
}
</script>

<style>
    .rank{
        font-size: 20px;
        font-weight: bold;
    }
</style>